# Migration Guide

## Todos

- [create repository](https://github.com/organizations/robert-tools/repositories/new) in `@robert-tools`
  - **description:** `A component to provide <component>`.
  - **visibility:** public
  - **template:** `robert-tools/sample`
- clone: `git clone git@github.com:robert-tools/<repository>.git`
- **Installation:**  `npm i`
- **Initialize:** run init task: `npm run init` (choose major version for `1.0.0`)
- fixes
  - fix owner: `github.com/robert-tools` to `github.com/willi84`
  - fix changelog:

    ```markdown
    # Changelog

    ## 1.0.0

    ### ⚙️ chore

    - initial setup of the project

    ### ✨ improvements

    - initial implementation of the atom-button component
    ```

- add main change: `src/index.ts` including tests in `src/index.spec.ts`

### component specific changes

- update package.json with correct file entry points

#### 📄 package.json

```json
"main": "./dist/index.js",
"types": "./dist/index.d.ts",
"exports": {
    ".": {
        "default": "./dist/index.js"
    },
    "./index.njk": "./src/index.njk",
    "./index.css": "./src/index.css"
},
"files": [
    "dist",
    "src/index.njk",
    "src/index.css"
],
```

#### 📄 README.md sample

``````markdown
### 📝 Sample usage

#### prerequisites

- define css variables
- safeParam installed (@robert.tools/eleventy-filter-safe-param)

#### Template

Use the button component as shown below:

```html
{{ component("atom/button", {}) }}
```

#### CSS

Use the basic styling

```css
@import '@robert.tools/atom-button/src/index.css';
```

#### TypeScript

Include TypeScript by importing the component

```typescript
import * as AtomButton from '@robert.tools/atom-button';
```
``````

#### 📄 index.spec.ts

Add fake test to avoid linting issues.

```typescript
describe('atom-button', () => {
    it('should render correctly', () => {
        expect(true).toBe(true);
    });
});
```

### common changes

#### 📄 README.md

``````markdown
## ⚖️ Notes

This software is hand-crafted, test-driven and assisted by AI tools. I know each
line of my code. ✌️

| Tool | Comment |
| --- | --- |
| ![assisted by Jest](https://img.shields.io/badge/Jest-TDD-008800?logo=jest) | Test-driven development with Jest |
| ![assisted by robert.tools](https://img.shields.io/badge/robert.tools-ecosystem-008800) | Part of the robert.tools ecosystem |
| ![assisted by GitHub Copilot](https://img.shields.io/badge/GitHub_Copilot-assisted-8A2BE2?logo=githubcopilot) | Code completion |
| ![assisted by OpenAI](https://img.shields.io/badge/OpenAI-assisted-8A2BE2?logo=openai) | chatGPT research |

``````

#### 📄 .markdownlint.json

```json
{
    "no-duplicate-heading": {
        "siblings_only": true
    },
    "MD033": {
        "allowed_elements": ["description"]
    }
}
```
