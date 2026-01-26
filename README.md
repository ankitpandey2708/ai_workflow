## Agent.md
While building the app, focus on the following:

1. no accessibility features
2. no testing tasks
3. no deployment tasks. focus only on local development
4. focus only on design and functionlaity tasks


## 🚀 Project Setup Command

Use the following command to initialize the Next.js project with all required configurations:

```bash
npx create-next-app@latest my-app --yes
```

## Planning & Task Management

  - **Prompts:**
    [https://chatgpt.com/share/67c5ee78-0b94-800d-b467-ceecdbf6ce70](https://chatgpt.com/share/67c5ee78-0b94-800d-b467-ceecdbf6ce70)
    ```bash
    do the following :
    1. response should be high quality ,no fluff,   no corporate jargon .practical,actionable and not theoretical
    2. Flesch reading score above 80
    3. make sure MECE is followed.
    ```
  - **Updating `tasks.md`:**
    ```bash
    Go through each story and Find the next story to work on. Review each unfinished story and correct issues if any. Then proceed to create or edit files to complete each story.     After you complete all the tasks in the story, update the file to check off any completed story.
    ```
-----

## Design implementation.

### **Option 1: Claude skills**

1.  https://github.com/anthropics/skills/blob/main/skills/frontend-design/SKILL.md or https://github.com/Dammyjay93/claude-design-skill/blob/main/skill/skill.md

### **Option 2: Design Override (Cosmetic Changes)**

Alternatively, use this prompt to enforce a specific design aesthetic:

> 'Analyze my existing project, then override all CSS and visual styling to match the uploaded **design.md** specifications while preserving all functionality and HTML structure'

  - **Design Guidelines Reference:** [design.md](https://github.com/ankitpandey2708/ai_workflow/blob/main/design.md)

give me a ascii tree of the visual heirachry of summary card assuming dropdown is monthly . now from 1st principles pov review the above tree and point out issues in visual layout
-----


## 🧹 Code Cleanup and Security Audits

**Execute the following steps in the specified order, performing the entire cleanup process at least two times.**

### **1. Security & Data Audit**

  - **Browser Data Storage:** Check for any data being stored in the browser (e.g., Local Storage, Session Storage). **Confirm deletion with me first.**
  - **Data Exposure:** Check for any sensitive data being exposed in the browser (e.g., API keys, secrets). move the API calls server‑side so keys stay private

### **2. Code Quality & Optimization**

1.  **Run Knip:** Execute the following command to find unused files, dependencies, and exports but ask LLM to investigate further if these are real issues or not
    ```bash
    npm init @knip/config && npm run knip
    ```
2.  **Check for Code Duplication ie follow DRY principle and no bloat in the code**
3.  **without breaking anything suggest a way to optimizse number of api calls**
4.  **Check for Code Refactoring:** Identify and implement improvements for code structure, readability, and maintainability.
5.  **audit all the tsx files and check for unnecessary re-renders**
6.  **Run a MECE performance audit across the entire codebase (all file types). Classify every finding into exactly one bucket:  1. List scalability, 2) Compute offload, 3) Input latency, 4) Network/AI latency control, 5) Paint/animation cost, 6) Data access & caching. Exclude already‑implemented optimizations, avoid overlap, and cite file:line for each finding**
-----

## SEO

1. audit the project from a SEO pov and make the project seo friendly
2. **https://github.com/squirrelscan/squirrelscan**
-----

## Notes to self
1. improve prompts for creating prd/brd/tasklist. prrof read each after genration. make sure thery are legible and mece. make sure the task make sense when moving from one task to other
2. always use a strong coding/planning model
