# Coding Guidelines

## Typescript

### JSDOC

#### imports

```typescript
// 📦 external dependencies
import { LOG } from '@robert.tools/log';

// 📦 internal dependencies
import { foo } from './index';

// 🧩 types
import type { foo } from './index.d';

// ⚓ CONSTANTS
const FOO = 123;

// 🗃️ export types
export type { FOOBAR } from './index.d';

```

#### method 

```typescript
/**
 * 🎯 description
 * @param {string[]} names ➡️ a names array
 * @returns {boolean} 📤 a result
 */
```

## CHANGELOG

`````markdown
## 1.0.0

Some description.

### 📰 documentation

- add [ADR-001: Base architecture of http lib](docs/adrs/001-adr-architecture.md)

### 🧹 cleanup

- remove old functions like index.mock.ts, index.helper.ts

### ⚙️ chore

- reduce complexity of getResponse and getHttpItem
- 🙈 hide: internalize getHttpItemFromHeader

### ✨ improvements

- re-design typings

### 🐛 bug fixes

- fix bugs with 

### 🗃️ API changes

- add: someFn
``````
