---
marp: true
theme: github-theme
paginate: true
header: 'Mastering GitHub Actions'
footer: '© 2025 Innovate Solutions | 23f2004258@ds.study.iitm.ac.in'
---

<!--
theme: github-theme
class:
  - title-slide
-->

<style>
  /* Define the custom 'github-theme' */
  :root {
    --color-background: #0d1117; /* GitHub Dark Background */
    --color-foreground: #c9d1d9; /* GitHub Dark Foreground */
    --color-primary: #58a6ff;   /* GitHub Blue */
    --color-secondary: #a5d6ff; /* Lighter Blue */
    --font-family-sans-serif: 'Segoe UI', 'Roboto', 'Helvetica', sans-serif;
    --font-family-monospace: 'SFMono-Regular', 'Consolas', 'Liberation Mono', monospace;
  }

  section {
    background-color: var(--color-background);
    color: var(--color-foreground);
    font-family: var(--font-family-sans-serif);
    padding: 70px;
  }

  h1, h2, h3 {
    color: var(--color-primary);
    font-family: var(--font-family-sans-serif);
    font-weight: 400;
    border: none;
  }
  
  h1 {
    font-size: 3.2em;
    text-align: left;
  }

  h2 {
    font-size: 2.4em;
    border-bottom: 1px solid #30363d; /* GitHub Divider Color */
    padding-bottom: 12px;
    text-align: left;
  }

  /* Custom styling for the title slide */
  section.title-slide {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    text-align: left;
  }
  
  section.title-slide h1 {
    font-size: 4.2em;
  }
  
  section.title-slide p {
    color: var(--color-secondary);
    font-size: 1.4em;
  }

  code {
    font-family: var(--font-family-monospace);
    background-color: #161b22;
    padding: 3px 6px;
    border-radius: 6px;
    font-size: 0.95em;
  }

  pre code {
    display: block;
    padding: 20px;
    line-height: 1.5;
  }
</style>

# **GitHub Actions**
<p>Automate Your Development Workflow</p>
<br>
<p><strong>Presenter:</strong> Alex Ray</p>
<p><strong>Contact:</strong> 23f2004258@ds.study.iitm.ac.in</p>

---

## **What are GitHub Actions?**

GitHub Actions is a **CI/CD** (Continuous Integration & Continuous Delivery) platform that allows you to automate your build, test, and deployment pipeline.

- **Event-Driven:** Trigger workflows on events like `push` or `pull_request`.
- **Integrated:** Lives right inside your GitHub repository.
- **Community-Powered:** Leverage thousands of actions from the marketplace.

---

<!--
_class:
  - invert
-->

![bg right:50%](https://placehold.co/800x600/0d1117/58a6ff?text=Core+Components)

## **Core Components**

* **Workflow:** An automated process defined in a YAML file.
* **Job:** A set of steps that execute on a runner.
* **Step:** An individual task that can run commands or an action.
* **Action:** A reusable piece of code that performs a complex task.
* **Runner:** A server that runs your workflows.

---

## **Example Workflow**

Here is a basic workflow that runs tests on every push to the `main` branch. This file would be located at `.github/workflows/ci.yml`.

```yaml
name: Node.js CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Use Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '20.x'
    - run: npm ci
    - run: npm test
```

---

## **Get Started**

Ready to automate?

1.  Create a `.github/workflows` directory in your repository.
2.  Add a new `.yml` file (e.g., `main.yml`).
3.  Define your first workflow and push it to GitHub.

**Questions?**
**Email:** 23f2004258@ds.study.iitm.ac.in
