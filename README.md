# portfolio
My teaching portfolio

## Site development planning

## **Phase 1: Minimally Viable Portfolio (MVP)**
Goal: Establish credibility and provide essential materials for application submissions.

### **Core Sections**
1. **Home** – Brief introduction and purpose of the portfolio.
2. **Resume/CV** – Downloadable PDF and web version.
3. **Teaching Statement** – Clear articulation of your teaching philosophy.
4. **Evidence of Impact** – A single, compelling page featuring key data or anecdotes that showcase your effectiveness as an educator.
5. **Suggested Materials** – Space for links to additional materials (e.g., student testimonials, sample lesson plan) without overwhelming the visitor.

### **Technical Setup**
- Simple Jekyll-based static site.
- Clean, navigable layout with PDF downloads.

---

## **Phase 2: Expanded, Selective Portfolio**
Goal: Provide a compelling yet streamlined set of materials that offer a fuller picture of your teaching expertise.

### **Core Sections (Expanding on MVP)**
1. **Home** – More detailed bio and teaching philosophy summary.
2. **Resume/CV** – Interactive version with sections for quick browsing.
3. **Teaching Statement** – Possibly adapted for different audiences (math vs. CS).
4. **Selected Evidence of Impact**
   - A refined set of data points (e.g., student outcomes, testimonials).
   - Examples of student work or transformations.
5. **Curriculum & Pedagogical Materials**
   - **Course Overviews**: Descriptions of key courses taught.
   - **One or Two Representative Lesson Plans**: Well-documented examples.
   - **Assessment Philosophy**: How you evaluate and guide student learning.
6. **Computing Tools & Adaptability**
   - Description of the environments you’ve used (Emacs, Jupyter, etc.).
   - A short piece on adapting curriculum to different student needs.

### **Technical Setup**
- Jekyll with some minor interactive elements.
- Possibly a blog section for reflections on teaching methods.

---

## **Phase 3: Fully Developed Portfolio**
Goal: A comprehensive repository supporting candidacy for competitive teaching roles.

### **Core Sections (Full Version)**
1. **Home** – Brief bio with highlights of experience.
2. **Resume/CV** – Expanded version with links to supporting materials.
3. **Teaching Statement** – Revised based on feedback and expanded reflections.
4. **Student Work & Impact**
   - Expanded selection of **student projects**, particularly in data science.
   - Sections on **adaptability** (how you've taught in different environments).
   - **Computing Tools**: Overview of the software and methodologies you’ve employed.
   - **Diversity & Equity in Computing**: Reflections and concrete examples.
5. **Curriculum Documentation**
   - **Multiple Course Syllabi** (Math, CS, Data Science).
   - **Lesson Plan Repository**: Organized by subject or concept.
   - **Project-Based Learning Examples**: Highlighting past student projects.
6. **Technical & Infrastructure Support**
   - **Computer Lab Setup Plan**: How you would design and manage a tech classroom.
   - **CS & Math Integration**: Best practices for blending the two disciplines.
7. **Professional Development & Thought Leadership**
   - Blog or short essays on teaching philosophy.
   - Notes on collaborations, presentations, or department-building work.

### **Technical Setup**
- Jekyll site with structured navigation.
- Improved design for readability and ease of access.
- Possible interactive components (e.g., embedded student work, sample problem sets).

---

### **Next Steps**
- **Phase 1**: Build the site skeleton and upload essential documents.
- **Phase 2**: Curate select materials, ensuring clarity without bloat.
- **Phase 3**: Develop an exhaustive, well-organized repository to showcase depth.

## Directory Structure
.
├── _config.yml
├── index.md                  → Home
├── about.md                  → /about/
├── cv.md                     → /about/cv/
├── curriculum.md             → /curriculum/
├── curriculum/
│   ├── unit-1-functions.md  → /curriculum/unit-1-functions/
│   └── ...
├── projects.md
├── projects/                 → /projects/
│   ├── data-science.md       → /projects/data-science/
│   ├── flag-project.md       → /projects/flag-project/
│   └── ...
├── impact.md                → /impact/
├── evidence.md              → /impact/evidence/
└── contact.md               → /contact/
