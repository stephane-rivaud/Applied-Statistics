# Applied Statistics Course - Development Repository

> 🔒 **Private Development Repository**
> This is the complete development environment containing all course materials, solutions, development files, and workflow documentation.

## 🎯 Overview

This repository contains a 6-lesson university-level Applied Statistics course covering:
- Statistical modeling and exploratory data analysis
- Estimation methods (MLE, Method of Moments, Fisher Information)
- Estimator properties (bias, variance, MSE, confidence intervals)
- Hypothesis testing (foundations and applications)
- Final coding project

**Repository**: `Applied-Statistics-Private` (PRIVATE)
**Branch**: `dev` (primary development branch)

## 📁 Repository Structure

```
├── README.md                          # This file
├── syllabus.md                        # Course syllabus (instructor version)
├── style-guide.md                     # LaTeX and code style conventions
├── requirements.txt                   # Python dependencies
│
├── GIT_SETUP_GUIDE.md                 # Git workflow setup documentation
├── WORKFLOW_QUICK_REFERENCE.md        # Daily Git workflow commands
├── BRANCH_CLEANUP_PROCEDURE.md        # Branch maintenance guide
├── DOCUMENTATION_ADAPTATION_PLAN.md   # This documentation plan
│
├── docs/                              # Development documentation
│   ├── jupyter-mcp-*.md              # MCP integration docs
│   └── ...
│
├── lessons/                           # Early course lessons (00–03 released)
│   ├── 00-welcome-introduction/
│   │   ├── material.md               # Lesson content
│   │   └── slides/                   # LaTeX Beamer slides
│   ├── 01-statistical-modeling/
│   │   ├── material.md
│   │   └── slides/
│   ├── 02-statistical-learning/
│   └── 03-estimator-properties/
│       ├── material.md
│       ├── exercises/                # Exercise descriptions
│       ├── notebooks/                # Supporting notebooks
│       └── slides/
│
├── labs/                              # Lab sessions (01–06 released)
│   ├── 01-random-variables/
│   │   └── assignment.ipynb          # Student notebook
│   ├── 02-maximum-likelihood-estimation/
│   │   ├── assignment.ipynb
│   │   └── lifetimes.txt
│   ├── 03-inference-estimators/
│   │   └── assignment.ipynb
│   ├── 04-gaussian-confidence-intervals/
│   │   ├── assignment.ipynb
│   │   └── dataset-recommendations.md
│   ├── 05-non-parametric-estimation/
│   │   └── assignment.ipynb
│   └── 06-model-fitting/
│       └── assignment.ipynb
│
├── projects/                         # Capstone workspaces
│   └── birds-biodiversity/          # Final project assets (see docs below)
│
├── shared/                            # Shared resources
│   ├── data/                         # Sample datasets
│   │   ├── heights_weights_sample.csv
│   │   ├── ab_test_clicks.csv
│   │   └── manufacturing_defects.csv
│   └── utils/                        # Python utilities
│       ├── __init__.py
│       └── io.py
│
├── scripts/                           # Build and generation scripts
│   ├── sanitize_tex.py               # LaTeX preprocessing
│   └── data_generation/              # Synthetic data generators
│       └── synth_bikeshare_generator.py
│
├── presentation/                      # Course overview slides
│   ├── course_overview.tex
│   └── Makefile
│
└── figures/                          # Generated figures
```

## 🌿 Branch Structure

This repository uses a three-branch workflow:

| Branch | Purpose | Remote | Visibility |
|--------|---------|--------|------------|
| **`dev`** | **Full development** (YOU ARE HERE) | `private/dev` | Private |
| `main` | Source file coordination | `private/main` | Private |
| `public-main` | Student-facing materials | `public/public-main` | **PUBLIC** |

### Branch Contents

**`dev` (this branch):**
- ✅ Everything: sources, solutions, prompts, workflow docs
- ✅ Development files and AI assistant prompts
- ✅ Complete lab solutions
- ✅ All internal documentation

**`main` branch:**
- ✅ LaTeX sources and Python scripts
- ✅ Exercise descriptions
- ✅ Build system
- ❌ No solutions or development files

**`public-main` branch:**
- ✅ Student materials only
- ✅ Lab assignments (no solutions)
- ✅ Lesson PDFs
- ❌ No LaTeX sources
- ❌ No solutions or development files

## 🔧 Development Setup

### Python Environment

```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

**Required packages**: NumPy, Pandas, Matplotlib, SciPy, Scikit-learn, Jupyter, Seaborn

### LaTeX/Beamer Setup

For generating slide PDFs:

```bash
# macOS
brew install --cask mactex

# Ubuntu/Debian
sudo apt-get install texlive-full

# Or install BasicTeX/TinyTeX for a minimal setup
```

**Required LaTeX packages**: Beamer, TikZ, listings, hyperref, amsmath

### VS Code Extensions (Recommended)

- **LaTeX Workshop** - LaTeX editing and compilation
- **Python** - Python development
- **Jupyter** - Notebook support
- **Markdown All in One** - Markdown editing
- **Git Graph** - Visualize branch structure

## 📝 Development Workflow

### Daily Workflow

```bash
# 1. Always work in dev branch
git checkout dev

# 2. Make changes
# ... edit files ...

# 3. Commit changes
git add .
git commit -m "Descriptive message"

# 4. Push to private repository
git push private dev
```

### Creating a New Lesson

1. **Create lesson directory structure**:
   ```bash
   mkdir -p lessons/0X-topic-name/{slides,exercises,notebooks,data}
   ```

2. **Create core files**:
   - `material.md` - Lesson content
   - `slides/main.tex` - Beamer presentation
   - `exercises/*.md` - Exercise descriptions

3. **Develop with AI assistance** (optional):
   - Create `*_prompt.md` files for AI assistant instructions
   - These stay in `dev` branch only!

4. **Create solutions**:
   - Add solution notebooks to `notebooks/` or `labs/Solutions/`
   - Never commit these to `public-main`!

5. **Generate PDFs**:
   ```bash
   cd lessons/0X-topic-name/slides
   make  # or pdflatex main.tex
   ```

### Final Project Workspace

- Dataset: `projects/birds-biodiversity/data/raw/Observations 2012-2025.xlsx`
- Student brief: `projects/birds-biodiversity/docs/final_project_assignment.md`
- Students are expected to craft their own analysis notebook(s); no template notebook is provided on this branch.

### Updating Existing Materials

```bash
# Edit in dev branch
git checkout dev
# ... make changes ...
git commit -m "Update lesson 03: add bootstrap examples"
git push private dev

# If updating sources, cherry-pick to main
git checkout main
git cherry-pick <commit-hash>
git push private main
```

## 🚀 Publishing to Students

### Step 1: Prepare Content

Ensure content is ready:
- [ ] Lesson material is complete
- [ ] PDFs are generated and look correct
- [ ] Lab assignments have no solution code
- [ ] All data files are included

### Step 2: Cherry-pick to public-main

```bash
# Switch to public branch
git checkout public-main

# Find the commit to publish
git log dev --oneline | head -20

# Cherry-pick selected commit
git cherry-pick <commit-hash>

# Or manually copy files if needed
# ... copy specific files ...

# Push to public repository
git push public public-main
```

### Step 3: Verify Publication

```bash
# Check what students see
git checkout public-main
find . -name "*.ipynb" | grep -i solution  # Should return nothing!
cat README.md  # Should be student-facing version
```

## 🔒 Git Workflow Details

See detailed documentation:
- **[GIT_SETUP_GUIDE.md](GIT_SETUP_GUIDE.md)** - Initial setup and configuration
- **[WORKFLOW_QUICK_REFERENCE.md](WORKFLOW_QUICK_REFERENCE.md)** - Daily commands
- **[BRANCH_CLEANUP_PROCEDURE.md](BRANCH_CLEANUP_PROCEDURE.md)** - Branch maintenance

### Quick Commands

```bash
# Check current branch
git branch

# Check branch tracking
git branch -vv

# Push to private
git push private dev      # from dev branch
git push private main     # from main branch

# Push to public
git push public public-main  # from public-main branch

# Cherry-pick from dev to main
git checkout main
git cherry-pick <hash>

# Cherry-pick from main to public
git checkout public-main
git cherry-pick <hash>
```

## 📚 Course Content Status

| Lesson | Material | Slides | Lab | Status |
|--------|----------|--------|-----|--------|
| 00 | ✅ | ✅ | - | Complete |
| 01 | ✅ | ✅ | ✅ | Complete |
| 02 | ✅ | ✅ | ✅ | Complete |
| 03 | ✅ | ✅ | ✅ | Complete |
| 04 | ✅ | ✅ | ✅ | In Progress |
| 05 | ✅ | ✅ | ✅ | In Progress |
| 06 | ✅ | - | - | Complete |

## 🧪 Lab Sessions

### Structure

- **Subjects** (`labs/Subjects/`): Student-facing assignments
- **Solutions** (`labs/Solutions/`): Complete solutions (private!)

### Creating New Labs

1. Create assignment notebook in `labs/Subjects/`
2. Create solution notebook in `labs/Solutions/`
3. Test both notebooks thoroughly
4. Only publish the subject notebook to `public-main`

### Lab Topics

1. Random Variables - Distributions and simulation
2. Maximum Likelihood Estimation - Parameter estimation
3. Inference Estimators - Properties and comparison
4. Model Fitting - Regression and evaluation
5. Non-Parametric Estimation - Bootstrap methods
6. Binary Classification - Logistic regression
7. Gaussian Confidence Intervals - Interval estimation
8. Hypothesis Testing - Statistical tests
9. Project - Final data analysis project

## 📖 References & Resources

### Textbooks

- **All of Statistics** by Larry Wasserman (Parts I & II) - [Link](https://www.stat.cmu.edu/~brian/valerie/617-2022/0%20-%20books/2004%20-%20wasserman%20-%20all%20of%20statistics.pdf)
- **A Modern Introduction to Probability and Statistics** by Dekking et al. - [Link](https://cis.temple.edu/~latecki/Courses/CIS2033-Spring13/Modern_intro_probability_statistics_Dekking05.pdf)

### Online Resources

- Statistical Learning Course - Stanford
- Think Stats - Allen Downey
- OpenIntro Statistics

### Tools & Libraries

- **NumPy** - Numerical computing
- **Pandas** - Data manipulation
- **Matplotlib/Seaborn** - Visualization
- **SciPy** - Statistical functions
- **Scikit-learn** - Machine learning

## 🛠️ Build System

### Compiling Slides

```bash
# Single lesson
cd lessons/03-estimator-properties/slides
pdflatex main.tex

# Or use make if Makefile exists
make

# All lessons
for lesson in lessons/*/slides; do
    (cd "$lesson" && pdflatex main.tex)
done
```

### Generating Figures

```bash
# Run figure generation scripts
cd lessons/02-statistical-learning/slides/figure_scripts
python statistical_learning.py
```

### Data Generation

```bash
# Generate synthetic datasets
cd scripts/data_generation
python synth_bikeshare_generator.py
```

## 📋 TODO & Roadmap

### Short-term
- [ ] Complete lesson 04 lab solutions
- [ ] Complete lesson 05 lab solutions
- [ ] Finalize grading rubrics
- [ ] Update all PDFs

### Medium-term
- [ ] Add more practice problems
- [ ] Create video tutorials
- [ ] Improve figure quality
- [ ] Add interactive visualizations

### Long-term
- [ ] Add advanced topics (optional modules)
- [ ] Create autograding scripts
- [ ] Develop online platform
- [ ] Translate materials

## 🐛 Known Issues

- Some LaTeX slides need math rendering fixes
- Figure scripts need cleanup
- Some data files could be larger/more realistic

## 💡 Development Tips

1. **Always commit to `dev` first** - Never work directly in `main` or `public-main`
2. **Test notebooks thoroughly** - Run all cells before publishing
3. **Check PDFs** - Always review generated PDFs before releasing
4. **Use descriptive commit messages** - Helps with cherry-picking
5. **Keep solutions private** - Double-check before pushing to public
6. **Document as you go** - Update README when adding features
7. **Use AI assistants wisely** - Keep prompts in dev branch only

## 📞 Maintenance

### Regular Tasks

- **Weekly**: Update course schedule, publish new materials
- **After each lesson**: Review student questions, update materials
- **End of semester**: Archive, gather feedback, plan improvements

### Backup Strategy

- Private repository on GitHub (backed up)
- Local development machine (backed up separately)
- Consider additional backup location for critical files

## 🔐 Security & Privacy

- **Never** commit solutions to public repository
- **Never** commit student data or grades
- **Never** commit API keys or credentials
- Review all commits to `public-main` carefully
- Use `.gitignore` appropriately

---

**Repository**: https://github.com/stephane-rivaud/Applied-Statistics-Private
**Public Repository**: https://github.com/stephane-rivaud/Applied-Statistics
**Last Updated**: October 11, 2025
