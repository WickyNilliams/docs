---
description: >-
  @atomico/exports aims to be the solution to facilitate the construction of the
  metadata in your package.json necessary for publishing on NPM or at the
  monorepo level with workspaces.
---

# @atomico/exports

Atomico export is a solution that parses the output of compilers like vite, esbuild, typescript, rollup or other bundle tool.

Atomico export is also compatible with uncompiled code (standard Javascript).

<figure><img src="../../.gitbook/assets/atomico-exports.png" alt=""><figcaption></figcaption></figure>

### The objective of Atomico/exports

1. Achieve aesthetic imports at the package level, example:&#x20;

```typescript
import { Button } from "components/dist/button.js"; // ❌
import { Button } from "components/button"; // ✅
```

2\. Create wrappers for React/Preact/Vue of webcomponents created with Atomico

```typescript
import { Button } from "components/button/react"; 
```

### Installation

{% tabs %}
{% tab title="NPM" %}
```bash
npm install -D @atomico/exports
```
{% endtab %}

{% tab title="package.json#scripts" %}
```javascript
{
 /**
  * ⚠️ The --types flag requires the installation of @typescript
  */
 "scripts": {
   "exports": "exports dist/**/* types/**/*"
 }
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
`@atomico/exports` is distributed as ESM, so your `package.json` must define the property `"type":"module"` for its use.
{% endhint %}
