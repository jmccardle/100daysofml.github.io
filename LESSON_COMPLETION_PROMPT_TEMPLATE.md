# Lesson Completion Prompt Template

Use this prompt for completing individual lessons in the 100 Days of ML course.

---

## YOUR TASK

Complete **Lesson {LESSON_NUMBER}** for the 100 Days of Machine Learning course.

## REPOSITORY INFORMATION

- **Repository**: `/home/user/100daysofml.github.io` (or clone from the repo URL if not present)
- **Branch naming**: `claude/lesson-{LESSON_NUMBER}-{SESSION_ID}`
  - Example: `claude/lesson-42-011CUwSifyFmLGvzrWcck2RR`
  - CRITICAL: Branch must start with 'claude/' and include session ID for push to succeed
- **Main branch**: `main` (use as base and PR target)

## STEP-BY-STEP INSTRUCTIONS

### 1. Research Phase

**A. Locate the lesson file:**
- Lessons 1-35: Located in `content/Week_0X/Lesson_XX.ipynb` (where X matches the week)
  - Week 1: Lessons 1-5
  - Week 2: Lessons 6-10
  - Week 3: Lessons 11-15
  - Week 4: Lessons 16-20
  - Week 5: Lessons 21-25
  - Week 6: Lessons 26-30
  - Week 7: Lessons 31-35
- Lessons 36-100: May need to be created in new week directories (Week_08 through Week_21)

**B. Read the week overview:**
- Find `content/Week_XX/{week_number}_Overview.md`
- This contains the lesson topic, learning objectives, and daily breakdown
- Extract the specific topic and goals for your lesson number

**C. Study existing complete lessons:**
- Read 2-3 complete lessons from the same week (if available)
- Read 2-3 complete lessons from other weeks as reference
- Note the structure, style, depth, and format patterns

**D. Check for existing content:**
- If the lesson file exists, read it completely
- Look for any markdown content, instructions, or incomplete code
- Check if there's a corresponding solution file (e.g., `Lesson_XXsolution.ipynb`)

### 2. Analysis Phase

Determine what the lesson needs based on:
- **Topic from overview**: What subject matter should be covered?
- **Week context**: What was taught before? What comes after?
- **Learning progression**: Appropriate difficulty for day X of 100
- **Existing content**: Is there a template/outline to build from?

### 3. Lesson Structure Requirements

Every complete lesson MUST include:

**A. Introduction Section** (Markdown)
- Brief overview of the topic (2-3 paragraphs)
- Why this topic matters in ML
- Learning objectives (3-5 bullet points)

**B. Theory Section** (Markdown + LaTeX)
- Core concepts explained clearly
- Mathematical formulas using LaTeX (e.g., `$$E = mc^2$$` or `$\beta_0 + \beta_1 x$`)
- Diagrams or explanations of algorithms
- Real-world applications

**C. Python Implementation** (Code Cells)
- Import necessary libraries (numpy, pandas, matplotlib, seaborn, sklearn, etc.)
- Step-by-step code examples with explanations
- CRITICAL: All code cells MUST be executed with visible outputs
- Use realistic datasets (built-in sklearn datasets, generated data, or CSV files if present)
- Include print statements showing intermediate results

**D. Visualization Section** (Code Cells)
- At least 1-2 matplotlib/seaborn visualizations
- Plots must be executed and display outputs
- Clear titles, labels, and legends

**E. Hands-On Activity** (Code Cells + Markdown)
- Practical exercise applying the concepts
- Can be a guided example with step-by-step solution
- Show complete working code with outputs

**F. Key Takeaways** (Markdown)
- Summary of main points (3-5 bullets)
- What students should now be able to do

**G. Further Resources** (Markdown)
- 3-5 links to documentation, tutorials, or papers
- Optional reading suggestions

### 4. Code Quality Standards

**Required:**
- All imports at the top of the first code cell
- Clear variable names following Python conventions
- Comments explaining complex logic
- Error-free execution (no tracebacks in outputs)
- Reproducible results (use `random_state=42` for random operations)
- Follow PEP 8 style guidelines

**Code Cell Output Requirements:**
- Must show actual execution results
- Print statements showing data shapes, statistics, model metrics
- Visualizations rendered as images
- No empty code cells without outputs

### 5. Style Guidelines

**Match existing lessons:**
- Consistent markdown formatting (headers, lists, code blocks)
- Similar tone: educational, clear, encouraging
- Math notation style consistent with other lessons
- Code commenting style matches the repository

**Length:**
- Typical lessons are 300-800 lines in notebook JSON
- 15-30 cells (mix of markdown and code)
- Enough depth for 1-2 hours of learning

### 6. Validation Steps

Before committing, verify:
- [ ] Open the notebook in Jupyter and run "Restart & Run All" - all cells execute successfully
- [ ] At least 5-10 code cells with visible outputs
- [ ] At least 1-2 visualizations rendered
- [ ] Mathematical formulas render properly
- [ ] No placeholder text like "TODO" or "Add content here"
- [ ] All learning objectives from the overview are addressed
- [ ] Lesson follows the logical progression from previous days

### 7. Git Workflow

```bash
# 1. Create and checkout branch
git checkout -b claude/lesson-{LESSON_NUMBER}-{SESSION_ID}

# 2. Make your changes (edit/create the notebook)

# 3. Add the file
git add content/Week_XX/Lesson_XX.ipynb

# 4. Commit with descriptive message
git commit -m "Complete Lesson {LESSON_NUMBER}: {LESSON_TOPIC}

- Add comprehensive theory section with LaTeX formulas
- Implement Python examples with executed outputs
- Include visualizations and hands-on exercises
- Add key takeaways and further resources"

# 5. Push to remote (with retry logic for network issues)
git push -u origin claude/lesson-{LESSON_NUMBER}-{SESSION_ID}

# 6. Create pull request
gh pr create \
  --title "Complete Lesson {LESSON_NUMBER}: {LESSON_TOPIC}" \
  --body "$(cat <<'EOF'
## Summary
- Completed Lesson {LESSON_NUMBER} covering {LESSON_TOPIC}
- Added theory, Python implementation, visualizations, and exercises
- All code cells executed with outputs
- Follows existing lesson structure and style

## Changes
- `content/Week_XX/Lesson_XX.ipynb`: Complete lesson implementation

## Checklist
- [x] All code cells execute successfully
- [x] Visualizations rendered
- [x] Math formulas properly formatted
- [x] Follows existing style and structure
- [x] Addresses all learning objectives

## Related
Part of completing the 100 Days of ML curriculum.
EOF
)"
```

### 8. Special Cases

**If the lesson file doesn't exist yet (Lessons 36-100):**
1. Check the overview docs to understand the planned curriculum
2. Determine the correct week directory (Week_08, Week_09, etc.)
3. Create the directory if needed: `mkdir -p content/Week_XX`
4. Create the notebook file: `Lesson_XX.ipynb`
5. Use an existing lesson as a JSON template for the notebook structure
6. Update `_toc.yml` to include the new lesson in the table of contents

**If a solution file exists (e.g., Lesson_12solution.ipynb):**
- Read the solution file to understand the intended approach
- Incorporate the solution content into the main lesson
- The main lesson should be complete, not just a homework assignment

**If the lesson is already partially complete:**
- Read existing content carefully
- Add missing sections (usually executed code cells)
- Don't remove good existing content
- Enhance and execute any incomplete code

## EXAMPLE COMPLETED LESSON REFERENCE

For reference, these lessons are well-structured and complete:
- `content/Week_01/Lesson_01.ipynb` - Good intro lesson structure
- `content/Week_02/Lesson_06.ipynb` - Good math/theory example
- `content/Week_05/Lesson_21.ipynb` - Good ML implementation example
- `content/Week_06/Lesson_26.ipynb` - Good classification example

## PARAMETERS TO FILL IN

When using this prompt, replace:
- `{LESSON_NUMBER}`: The lesson number (e.g., 12, 18, 42, 99)
- `{SESSION_ID}`: Your Claude session ID (visible in your interface)
- `{LESSON_TOPIC}`: The topic from the week overview (e.g., "Splitting Data", "CNNs", "Model Deployment")

## FINAL DELIVERABLE

You should produce:
1. ✅ A complete, executed Jupyter notebook at the correct path
2. ✅ A git commit on the lesson-specific branch
3. ✅ A pushed branch to the remote repository
4. ✅ A pull request ready for review
5. ✅ Confirmation that all validation steps passed

## CONCISE PROMPT FORMAT

For quick use, here's the minimal prompt:

---

**Complete Lesson {LESSON_NUMBER} for 100 Days of ML**

Repository: `/home/user/100daysofml.github.io`
Branch: `claude/lesson-{LESSON_NUMBER}-{SESSION_ID}` (must start with 'claude/')

Steps:
1. Read `content/Week_XX/{week}_Overview.md` to understand the lesson topic
2. Study 2-3 existing complete lessons for structure/style reference
3. Read existing `content/Week_XX/Lesson_{LESSON_NUMBER}.ipynb` if it exists
4. Complete the lesson with:
   - Theory section with LaTeX formulas
   - Python code cells with EXECUTED outputs
   - Visualizations (matplotlib/seaborn)
   - Hands-on exercises with solutions
   - Key takeaways and resources
5. Validate: Run "Restart & Run All" in Jupyter - must execute without errors
6. Commit, push to branch, create PR with title "Complete Lesson {LESSON_NUMBER}: {TOPIC}"

See `/home/user/100daysofml.github.io/LESSON_COMPLETION_PROMPT_TEMPLATE.md` for full details.

---
