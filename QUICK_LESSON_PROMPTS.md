# Quick Lesson Completion Prompts

Copy-paste these prompts for parallel lesson completion. Each prompt is self-contained.

---

## LESSON 12 - Splitting Data

```
Complete Lesson 12 for 100 Days of ML

Repository: /home/user/100daysofml.github.io (or clone if needed)
Branch: claude/lesson-12-{YOUR_SESSION_ID}
Target: content/Week_03/Lesson_12.ipynb

Task:
1. Read content/Week_03/03_Overview.md for lesson context
2. Read existing content/Week_03/Lesson_12.ipynb and content/Week_03/Lesson_12solution.ipynb
3. Study complete lessons: Lesson_11.ipynb, Lesson_13.ipynb for style reference
4. Complete Lesson 12 covering:
   - Theory of train/test splitting and why it matters
   - train_test_split from sklearn with examples
   - Different splitting strategies (random, stratified, time-based)
   - Cross-validation introduction
   - Code examples with executed outputs showing data shapes and distributions
   - Visualizations of data splits
5. Ensure all code cells are executed with visible outputs
6. Run "Restart & Run All" to validate
7. Commit: "Complete Lesson 12: Splitting Data into Training and Test Sets"
8. Push to claude/lesson-12-{SESSION_ID}
9. Create PR: "Complete Lesson 12: Splitting Data"

See LESSON_COMPLETION_PROMPT_TEMPLATE.md for full requirements.
```

---

## LESSON 18 - Visualization Techniques

```
Complete Lesson 18 for 100 Days of ML

Repository: /home/user/100daysofml.github.io (or clone if needed)
Branch: claude/lesson-18-{YOUR_SESSION_ID}
Target: content/Week_04/Lesson_18.ipynb

Task:
1. Read content/Week_04/04_Overview.md for lesson context
2. Read existing content/Week_04/Lesson_18.ipynb
3. Study complete lessons: Lesson_16.ipynb, Lesson_17.ipynb, Lesson_20.ipynb for style reference
4. Complete Lesson 18 covering:
   - Theory of data distribution visualization
   - Histograms, box plots, violin plots, density plots
   - Matplotlib and seaborn implementations with executed examples
   - When to use each visualization type
   - Multi-variable distribution plots (pair plots, joint plots)
   - Multiple visualizations with executed outputs
5. Ensure all code cells are executed with visible outputs (many plots!)
6. Run "Restart & Run All" to validate
7. Commit: "Complete Lesson 18: Visualization Techniques for Data Distribution"
8. Push to claude/lesson-18-{SESSION_ID}
9. Create PR: "Complete Lesson 18: Visualization Techniques"

See LESSON_COMPLETION_PROMPT_TEMPLATE.md for full requirements.
```

---

## LESSON 19 - Correlation Analysis

```
Complete Lesson 19 for 100 Days of ML

Repository: /home/user/100daysofml.github.io (or clone if needed)
Branch: claude/lesson-19-{YOUR_SESSION_ID}
Target: content/Week_04/Lesson_19.ipynb

Task:
1. Read content/Week_04/04_Overview.md for lesson context
2. Read existing content/Week_04/Lesson_19.ipynb
3. Study complete lessons: Lesson_16.ipynb, Lesson_17.ipynb, Lesson_18.ipynb for style reference
4. Complete Lesson 19 covering:
   - Theory of correlation (Pearson, Spearman, Kendall)
   - Mathematical formulas with LaTeX
   - Computing correlations with pandas and scipy
   - Correlation matrices and heatmaps
   - Scatter plots and regression lines
   - Interpreting correlation vs causation
   - Code examples with executed outputs and visualizations
5. Ensure all code cells are executed with visible outputs
6. Run "Restart & Run All" to validate
7. Commit: "Complete Lesson 19: Correlation Analysis using Python"
8. Push to claude/lesson-19-{SESSION_ID}
9. Create PR: "Complete Lesson 19: Correlation Analysis"

See LESSON_COMPLETION_PROMPT_TEMPLATE.md for full requirements.
```

---

## TEMPLATE FOR FUTURE LESSONS (36-100)

```
Complete Lesson {NUMBER} for 100 Days of ML

Repository: /home/user/100daysofml.github.io (or clone if needed)
Branch: claude/lesson-{NUMBER}-{YOUR_SESSION_ID}
Target: content/Week_{XX}/Lesson_{NUMBER}.ipynb

Task:
1. Identify the week (calculate: week = ceiling(NUMBER/5), e.g., lesson 42 = week 9)
2. Check if content/Week_{XX} directory exists, create if needed
3. Look for overview file or curriculum documentation to understand the topic
4. If no overview exists, research appropriate ML curriculum for day {NUMBER}:
   - Days 36-40: Clustering (K-Means, Hierarchical, DBSCAN)
   - Days 41-45: Dimensionality Reduction (PCA, t-SNE, UMAP)
   - Days 46-50: Neural Network Basics
   - Days 51-55: Deep Learning Frameworks (TensorFlow/PyTorch intro)
   - Days 56-60: CNNs and Computer Vision
   - Days 61-65: RNNs and NLP Basics
   - Days 66-70: Advanced NLP (Transformers, BERT)
   - Days 71-75: Recommender Systems
   - Days 76-80: Reinforcement Learning Intro
   - Days 81-85: MLOps and Model Deployment
   - Days 86-90: ML in Production
   - Days 91-95: Ethics, Bias, Fairness
   - Days 96-100: Capstone Project
5. Study 3-4 existing complete lessons for structure and style
6. Create complete lesson with theory, code (executed!), visualizations, exercises
7. Update _toc.yml if creating new week section
8. Run "Restart & Run All" to validate
9. Commit: "Complete Lesson {NUMBER}: {TOPIC}"
10. Push to claude/lesson-{NUMBER}-{SESSION_ID}
11. Create PR: "Complete Lesson {NUMBER}: {TOPIC}"

See LESSON_COMPLETION_PROMPT_TEMPLATE.md for full requirements.
```

---

## IMPORTANT REMINDERS

1. **Session ID**: Replace {YOUR_SESSION_ID} with your actual session ID (visible in your interface)
2. **Branch naming**: MUST start with 'claude/' or push will fail with 403 error
3. **Execution**: ALL code cells must have outputs - this is the #1 requirement
4. **Validation**: Run "Restart & Run All" in Jupyter before committing
5. **Network retry**: If push fails, retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s)

## PARALLEL EXECUTION EXAMPLE

To complete all 3 current incomplete lessons in parallel, run these three prompts simultaneously in separate Claude instances:

1. Instance 1: Copy "LESSON 12" prompt → Execute
2. Instance 2: Copy "LESSON 18" prompt → Execute
3. Instance 3: Copy "LESSON 19" prompt → Execute

Each will create its own branch and PR independently.

For future lessons (36-100), use the template and fill in the NUMBER parameter.

---

## VERIFICATION CHECKLIST

After completion, each lesson should have:
- ✅ Executed Jupyter notebook with outputs
- ✅ Git branch pushed (claude/lesson-XX-{SESSION_ID})
- ✅ Pull request created
- ✅ No errors when running "Restart & Run All"
- ✅ Matches style/structure of existing lessons
