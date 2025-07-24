### PR List: Future Development & Extensions

#### Tier 1: Core Content Expansion

These PRs focus on making the quiz a more comprehensive learning tool by expanding its coverage of the source material.

*   **`[Content] Add Questions for Remaining "Question Design" Biases`**
    *   **Description:** The current quiz covers 9 of the 21 biases in the "Question Design" category. This PR would involve creating new question pairs for the remaining 12 biases, such as `Overlapping Interval`, `Insensitive Measure`, `Mind-Set`, and `Change of Wording`, using the provided PDF for examples.
    *   **Goal:** Achieve full topic coverage for the first major category of bias.

*   **`[Feature] Create "Scenario-Based" Questions for Administration & Design Biases`**
    *   **Description:** Many biases (e.g., `Interviewer Bias`, `Response Fatigue`, `Skipping Question`) cannot be shown with a simple "Question A vs. Question B" format. This PR would introduce a new question template that describes a *scenario* ("An interviewer knows the study's hypothesis...") and asks the user to identify the resulting bias.
    *   **Goal:** Enable the quiz to test for biases from categories 2 (Questionnaire Design) and 3 (Administration), which are currently completely uncovered.

*   **`[Refactor] Decouple Question Data into an External JSON File`**
    *   **Description:** As the question bank grows, the `FULL_QUIZ_DATA` array inside the `<script>` tag will become difficult to manage. This PR involves moving the entire array into a separate `quiz-data.json` file and using the `fetch()` API to load it when the application starts.
    *   **Goal:** Improve code maintainability by separating data from logic, making it far easier for non-developers to contribute or edit questions.

#### Tier 2: Interactive & Educational Features

These PRs focus on making the quiz more engaging and effective as a learning tool.

*   **`[Feature] Link Feedback to the Reference Guide`**
    *   **Description:** When a user answers a question, the feedback box should contain a link that, when clicked, smoothly scrolls the page down to the corresponding entry in the Survey Bias Reference Guide.
    *   **Goal:** Create a tight feedback loop, allowing users to immediately learn more about the specific bias they just encountered.

*   **`[Feature] Implement Quiz Mode Selector`**
    *   **Description:** Add a dropdown menu to the start of the quiz that allows users to select a quiz "mode."
        *   `Full Quiz (All Categories)`
        *   `Focus on: Question Wording`
        *   `Focus on: Faulty Scales`
        *   `Focus on: Administration Biases`
    *   **Goal:** Allow users to engage in targeted learning and increase the replayability of the quiz.

*   **`[UI/UX] Make Results Sections Collapsible`**
    *   **Description:** Convert the "Detailed Results," "Question Review," and "Reference Guide" sections on the results page into collapsible sections using the `<details>` and `<summary>` HTML tags.
    *   **Goal:** Improve the user experience on the results page by reducing information overload and making it appear cleaner and more organized by default.

#### Tier 3: Technical & Architectural Improvements

These PRs focus on improving the long-term health, maintainability, and quality of the codebase.

*   **`[Refactor] Separate HTML, CSS, and JavaScript into Files`**
    *   **Description:** Move the CSS and JavaScript out of the `<style>` and `<script>` tags and into their own `styles.css` and `script.js` files, linking to them from the HTML.
    *   **Goal:** Follow standard web development best practices for separation of concerns, making the project easier to navigate and maintain.

*   **`[Chore] Implement Unit Tests for Core Logic`**
    *   **Description:** Introduce a testing framework (like Jest or Vitest) and write unit tests for the core quiz logic in the `SurveyBiasQuiz` class. Critical functions to test would include `sampleQuestions()`, `selectAnswer()` (scoring), and `getPerformanceMessage()`.
    *   **Goal:** Increase code robustness and prevent regressions by ensuring that future changes do not break existing functionality.

*   **`[UI/UX] Add a Dark Mode Toggle`**
    *   **Description:** Since the project already uses CSS variables for colors, this PR would involve adding a toggle button that switches the values of these variables to a "dark mode" theme. The user's preference should be saved in `localStorage`.
    *   **Goal:** Enhance user comfort and provide a popular, modern UI feature.