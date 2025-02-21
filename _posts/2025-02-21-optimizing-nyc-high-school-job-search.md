---
layout: post
title: Optimizing My NYC High School Job Search with YAML, yq, and Emacs
date:   2025-02-21 08:00:00 -0500
categories: jekyll update
---
As I prepare to return to teaching in a high-performing NYC high school, I’ve been refining my job search workflow using structured data formats and automation tools. This post captures some key takeaways from my exploration of YAML, yq, Emacs customizations, and shell scripting for streamlining my applications and professional network tracking.

### **Structuring Job Search Data with YAML**

To organize information on target schools, I’ve developed a structured YAML format that captures essential details such as school name, address, principal, department leads, mission, and enrollment type. For example:

```yaml
schools:
  - eleanor_roosevelt:
      name: Eleanor Roosevelt High School
      address: 411 E 76th St, New York, NY 10021
      website: https://erhsnyc.org/
      principal: Dimitri Saliani
      math dept lead: TBD
      cs dept lead: TBD
      mission: >
        Eleanor Roosevelt High School aims to provide a rigorous and supportive learning environment...
      values: >
        Academic excellence, integrity, community engagement.
      enrollment type: Screened
      neighborhood: Upper East Side, Manhattan
```

This structure ensures I can systematically compare schools and track updates over time.

### **Manipulating YAML with yq**

To query and transform the data, I’ve been using `yq`, a powerful command-line tool for YAML processing. Some useful commands include:

- Extracting school names:
  ```sh
  yq e '.schools[] | keys' schools.yaml
  ```
- Finding a specific school’s details:
  ```sh
  yq e '.schools[] | select(has("eleanor_roosevelt"))' schools.yaml
  ```
- Updating a school’s name:
  ```sh
  yq e '.schools[].eleanor_roosevelt.name = "New Eleanor Roosevelt HS"' -i schools.yaml
  ```

This approach allows me to quickly filter, modify, and sort schools in my application pipeline.

### **Enhancing YAML Editing in Emacs**

Since I prefer working in Emacs, I’ve been customizing my setup to improve YAML editing:

- Hooking `yaml-ts-mode` to `.yaml` files:
  ```elisp
  (use-package yaml-ts-mode
    :mode "\.yaml$")
  ```
- Integrating `consult` for better search and navigation:
  ```elisp
  (use-package consult
    :bind ("C-s" . consult-line)
    :config
    (setq consult-preview-key 'any))
  ```
- Exploring the potential for a `transient` minibuffer interface to edit YAML entries dynamically.

### **Automating My Application Process with Shell Scripts**

In addition to using YAML and `yq` for managing school data, I’ve developed a shell script to automate the creation of application directories and LaTeX-based cover letters. The script reads information from my `schools.yaml` file, creates a directory for each school, and generates LaTeX cover letters using the `moderncv` template.

Here’s the basic outline of the script:

```bash
#!/bin/bash

TEMPLATES_DIR=~/applications/templates
SCHOOLS_DIR=~/applications/schools
YAML_FILE="$(dirname "$0")/../schools.yaml"

SCHOOL_COUNT=$(yq e '.schools | length' "$YAML_FILE")

for ((i = 0; i < SCHOOL_COUNT; i++)); do
    SCHOOL_KEY=$(yq e ".schools[$i] | keys | .[]" "$YAML_FILE")
    
    NAME=$(yq e ".schools[$i].$SCHOOL_KEY.name" "$YAML_FILE")
    PRINCIPAL=$(yq e ".schools[$i].$SCHOOL_KEY.principal" "$YAML_FILE")
    ADDRESS=$(yq e ".schools[$i].$SCHOOL_KEY.address" "$YAML_FILE")
    MISSION=$(yq e ".schools[$i].$SCHOOL_KEY.mission" "$YAML_FILE")
    VALUES=$(yq e ".schools[$i].$SCHOOL_KEY.values" "$YAML_FILE")
    KEYPOINTS=$(yq e ".schools[$i].$SCHOOL_KEY.key_points" "$YAML_FILE")

    echo "Processing school: $NAME"
    echo "Principal: $PRINCIPAL"
    echo "Address: $ADDRESS"
    echo "Mission: $MISSION"
    echo "Values: $VALUES"
    echo "Key Points: $KEYPOINTS"
    echo "----------------------------------------"

    TARGET_DIR="$SCHOOLS_DIR/$SCHOOL_KEY"
    if [ -d "$TARGET_DIR" ]; then
        echo "Directory already exists. Continuing.."
        continue     
    else
        mkdir -p "$TARGET_DIR"
        echo "Created directory: $TARGET_DIR"
    fi

    cp -r "$TEMPLATES_DIR/resume/" "$TARGET_DIR/"
    cp -r "$TEMPLATES_DIR/cover_letter/" "$TARGET_DIR/"
    cp "$TEMPLATES_DIR/teaching_statement.md" "$TARGET_DIR/teaching_statement.md"
    
    COVER_LETTER="$TARGET_DIR/cover_letter/main.tex"
    cat <<EOF > "$COVER_LETTER"
\documentclass[11pt,a4paper,sans]{moderncv}
\moderncvstyle{banking} 
\moderncvcolor{blue}
\usepackage[scale=0.9]{geometry}

% Personal data
\name{Eric}{Allatta}
\phone[mobile]{929-244-0482}
\email{ericallatta@gmail.org}
\social[linkedin]{linkedin.com/in/ericallatta}

\begin{document}

\recipient{$PRINCIPAL}{$NAME \\\\ $ADDRESS}
\date{$(date '+%B %d, %Y')}
\subject{Experienced math and computer science teacher application}
\opening{Dear Principal $PRINCIPAL}
\closing{Sincerely,}
\signature{0.3}{signature.png}   
\enclosure[Attached]{Resume}
\makelettertitle

Dear $PRINCIPAL,
I am writing to express my strong interest in joining $NAME as a Mathematics and Computer Science teacher teacher. I admire $NAME's commitment to $MISSION and $VALUES. After spending a decade in NYC public schools, including nine years as a founding computer science teacher at the Academy for Software Engineering, I am excited to return to a school that values innovation, collaboration, and academic rigor.

I'd like to highlight $KEYPOINTS.

During my time at AFSE, I developed and taught an integrated mathematics-computer science curriculum, using tools like Bootstrap, EarSketch, and Nand2Tetris. My approach led to a significant increase in AP CS enrollment and stronger Algebra Regents performance, demonstrating my ability to foster both rigor and accessibility in diverse classrooms. I also built data systems to support decision-making and guided student-led initiatives, such as data science projects that helped inform instructional strategies.

I thrive in collaborative, inquiry-driven environments and am eager to contribute to $NAME’s continued success in preparing students for a technology-driven world. Whether teaching AP Computer Science, Data Science, Algebra, or integrated CS-math courses, I am committed to helping students develop the skills they need to succeed.

Thank you for considering my application. I look forward to the opportunity to discuss how my experience and vision can contribute to your school. Please feel free to contact me at (929) 244-0482 or ericallatta@gmail.com.

\makeletterclosing

\end{document}

EOF

    echo "Application folder created for $NAME at $TARGET_DIR"
done
```

This script helps automate the process of creating a personalized application folder for each school, including LaTeX-based cover letters. Each directory contains the necessary files like a resume, cover letter, and teaching statement, ready for further customization.

### **Tracking My Professional Network**

In addition to school data, I’ve structured my professional network in YAML. This helps me track former colleagues, their current roles, and how best to reach out for potential opportunities. For example:

```yaml
- Name: Ashley Ferrara
  Current Role: AP at AFSE
  Past Relationship: Close friend, both founders at AFSE
  Best Contact Method: Text or Email
  Specific Ask: Reconnect, gauge hiring needs at AFSE
  Priority: 1
```

By using YAML, I can sort contacts by priority and systematically approach my outreach efforts.

### **Next Steps**

With a structured dataset, efficient query tools, and a well-integrated Emacs setup, I’m in a strong position to manage my job search effectively. My next focus areas include:
- Automating application tracking with YAML and shell scripts.
- Developing Emacs functions to dynamically update my YAML files.
- Refining my networking strategy to maximize outreach efficiency.

This workflow not only streamlines my process but also reduces cognitive load, allowing me to focus on securing the best teaching opportunity in NYC.

If you have experience using YAML and automation tools for job tracking, I’d love to hear your insights!
