## Agent.md
While building the app, focus on the following:

1. no accessibility features
2. no testing tasks
3. no deployment tasks. focus only on local development
4. focus only on design and functionlaity tasks
5. use powerful models like opus 4.6 for ideation/big picture/frontend and smaller models for execution. 
6. Free AI Providers : freebuff/cline/https://opencode.ai/go
7. for cloning any website use : https://github.com/JCodesMore/ai-website-cloner-template

## 🚀 Project Setup Command

create a repo on github. clone it locally . cd into it and then Use the following command to initialize the Next.js project with all required configurations:

```bash
npx create-next-app@latest . --yes --skip-install
```

now do :
```bash
npm i
```

## Planning & Task Management

  - **Prompts:**
    [https://chatgpt.com/share/67c5ee78-0b94-800d-b467-ceecdbf6ce70](https://chatgpt.com/share/67c5ee78-0b94-800d-b467-ceecdbf6ce70)
   
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

  - **Data Exposure:** Check for any sensitive data being exposed in the browser (e.g., API keys, secrets). move the API calls server‑side so keys stay private

### **2. Code Quality & Optimization**

1.  **Run Knip:** Execute the following command to find unused files, dependencies, and exports but ask LLM to investigate further if these are real issues or not
    ```bash
    npm init @knip/config && npm run knip
    npx tsc --noEmit (add "noUnusedLocals": true, "noUnusedParameters": true, in "compilerOptions" inside tsconfig.json)
    ```
2.  **go through all relevant file types and Check for Code Duplication ie follow DRY principle and no bloat in the code**
3.  **without breaking anything suggest a way to optimizse number of api calls**
4.  **Always compress your System Prompt, Make surre you follow optimal settings wrt https://ai.google.dev/api/generate-content#endpoint**
6.  **go through all relevant file types and Check for Code Refactoring:** Identify and implement improvements for code structure, readability, and maintainability.
7.  **UI perf fix : https://pastebin.com/wRxrQ2Zr**
9.  Lighthouse Report Analyse : ```node -e "const d=require('./lighthouse.json');const r=d.lighthouseResult||d;const a=r.audits;const scores=Object.fromEntries(Object.entries(r.categories).map(([k,v])=>[k,Math.round(v.score*100)]));const failed=Object.values(a).filter(a=>a.score!==null&&a.score<1).map(a=>({id:a.id,score:a.score,display:a.displayValue})).sort((a,b)=>a.score-b.score);const lcp=a['lcp-breakdown-insight']?.details?.items?.[1];const errors=a['errors-in-console']?.details?.items?.map(i=>i.description);const vitals={lcp:a['largest-contentful-paint']?.displayValue,tbt:a['total-blocking-time']?.displayValue,cls:a['cumulative-layout-shift']?.displayValue,fcp:a['first-contentful-paint']?.displayValue,si:a['speed-index']?.displayValue};const bootup=a['bootup-time']?.details?.items?.sort((a,b)=>b.total-a.total).slice(0,8).map(i=>({url:i.url.split('/').pop(),total:Math.round(i.total),scripting:Math.round(i.scripting)}));const thread=a['mainthread-work-breakdown']?.details?.items?.map(i=>({group:i.groupLabel,ms:Math.round(i.duration)})).sort((a,b)=>b.ms-a.ms);const added={requestedUrl:r.requestedUrl,finalUrl:r.finalUrl,fetchTime:r.fetchTime,performanceScore:r.categories.performance.score,coreWebVitals:{FCP_ms:a['first-contentful-paint']?.numericValue,LCP_ms:a['largest-contentful-paint']?.numericValue,TBT_ms:a['total-blocking-time']?.numericValue,CLS:a['cumulative-layout-shift']?.numericValue,SpeedIndex_ms:a['speed-index']?.numericValue,TTI_ms:a['interactive']?.numericValue},server:{TTFB_ms:a['server-response-time']?.numericValue||null},opportunities:{unusedJavaScript_bytes:a['unused-javascript']?.details?.overallSavingsBytes||0,unusedJavaScript_files:(a['unused-javascript']?.details?.items||[]).map(i=>i.url),unusedCSS_bytes:a['unused-css-rules']?.details?.overallSavingsBytes||0}};console.log(JSON.stringify({...added,scores,vitals,failed,lcp,bootup,thread,errors},null,2));"```
-----

## SEO

1. audit the project from a SEO pov and make the project seo friendly


## Launch video

1. setup https://www.remotion.dev/docs/ai/skills
2. "now create a launch video for this project using remotion. go through this project and familiarize urself. use same
  visual tone and project aesthetics for the video as well. dont forget to use frontend-skill"

## Focus on
1. Enhanced empty state
2. Retention Features incl PNs
3. Tooltips for feature discovery
4. Gamification
-----

## Notes to self
1. improve prompts for creating prd/brd/tasklist. prrof read each after genration. make sure thery are legible and mece. make sure the task make sense when moving from one task to other
2. always use a strong coding/planning model
