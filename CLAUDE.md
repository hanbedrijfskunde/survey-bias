# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

An interactive educational quiz about identifying biases in survey questions, based on the Choi & Pak (2005) catalog of questionnaire biases. Available in Dutch (root `index.html`) and English (`en/index.html`).

## Architecture

This is a **static single-file HTML application** with no build system, no package manager, and no dependencies. Each language version is a self-contained HTML file with embedded CSS and JavaScript.

**Key structure within each `index.html`:**
- CSS (with variables, responsive breakpoints, print styles, animations)
- HTML (intro screen → question screen → results screen)
- JavaScript: `FULL_QUIZ_DATA` array (27 question objects) + `SurveyBiasQuiz` ES6 class

**Quiz data format:**
```javascript
{
  questionA: "Biased version",
  questionB: "Improved version",
  options: ["Bias Type 1", "Bias Type 2", "Bias Type 3"],
  correctAnswer: "Bias Type 1",
  explanation: "Why this is the correct bias type..."
}
```

**Core class methods:** `startQuiz()`, `showQuestion()`, `selectAnswer()`, `showResults()`, `downloadResults()` (PDF via print dialog), `sampleQuestions()`, `getQuestionCountFromURL()` (reads `?questions=N` URL parameter).

## Development

- **Dev server:** VS Code Live Server on port 5501
- **No build/test/lint commands** — open the HTML files directly or serve them statically
- **Deployment:** Static file hosting (e.g., GitHub Pages)

## Working with This Codebase

- Both language versions must be kept in sync when changing functionality or structure
- The Dutch version (`/index.html`) is the primary version; English (`/en/index.html`) is secondary
- The results screen includes a comprehensive embedded bias reference guide organized by three categories: Question Design, Questionnaire Design, and Questionnaire Administration
- The planned roadmap is in `.development-docs/prd.md` — consult it for context on feature work
