# Homework 1 — R Basics

**Course:** Data Science for Public Policy 2026
**Due:** **Wednesday, 29 April 2026, 12:00 PM (noon)**
**Data file:** `student_reading_scores.csv` (in this folder)

## Goal

Reproduce the eight-step workflow from Lecture 2 on a **new dataset**. The questions are different from the lecture demo, so copy-pasting the lecture code will not quite work — you will need to understand each step and adapt it.

## The dataset

`student_reading_scores.csv` contains reading-assessment results for 40 students across four countries.

| column | type | description |
|---|---|---|
| `student_id` | integer | student identifier |
| `country` | character | `USA`, `Germany`, `Korea`, or `Brazil` |
| `school_type` | character | `Public` or `Private` |
| `study_hours_weekly` | numeric | self-reported weekly study hours |
| `reading_score` | numeric | reading assessment score (300–750 scale) |
| `scholarship` | character | `Yes` or `No` |

A few cells are missing (`NA`). Handle them carefully — the lecture covered this.

## Tasks

### Task 1. Load the data
1. Read the CSV into an object called `students`.
2. Print the dimensions and the first six rows.

### Task 2. Inspect and overall summary
1. Use `str(students)` and `summary(students)` to check structure and quick statistics.
2. Compute the **overall average reading score** (remember that `NA` does not ignore itself).

### Task 3. Compare countries
Use `aggregate()` to compute the **mean `reading_score` by `country`**. Which country has the highest average? Which has the lowest?

### Task 4. Create a new variable
1. Create a new column `high_study` that is `TRUE` when `study_hours_weekly >= 12` and `FALSE` otherwise.
2. Use `aggregate()` to compute the mean `reading_score` for `high_study = TRUE` versus `FALSE`.

### Task 5. Plot
Make a simple bar plot of the **mean `reading_score` by country**. Add a sensible title and y-axis label.

### Task 6. Interpret (written, 3–5 sentences, in English)
In your short report, answer:
- Which country performs best on reading scores, and which performs worst?
- Is there an association between study hours and reading scores in this dataset?
- What is one **policy implication** you would draw? Be careful about what this data does — and does not — tell you.

## What to submit

Two files, named with your name or student ID:

1. **`homework_01_<yourname>.R`** — one R script that runs top-to-bottom without errors and completes Tasks 1–5.
2. **`homework_01_<yourname>.md`** or **`.pdf`** — a short written report (about half a page) for Task 6.

Submission channel will be announced in class / on the course page.

## Grading

| component | weight |
|---|---|
| Correct code (Tasks 1–5) | 60% |
| Written interpretation (Task 6) | 30% |
| Code readability (comments, object names) | 10% |

## Tips

- The commands from Lecture 2 cover every step you need.
- If `mean(...)` returns `NA`, you probably need `na.rm = TRUE`.
- `aggregate(y ~ x, data = df, FUN = mean, na.action = na.omit)` groups `y` by `x`.
- Run **one short block at a time** and check the output before moving on — this is the habit we practiced in class.
- If a line of code does not run, bring the **exact error message** to office hours or class.

## Academic honesty

You may discuss the problem with classmates, but the code and writing you submit must be your own. If you use AI tools, you still need to understand and be able to explain every line of your code.
