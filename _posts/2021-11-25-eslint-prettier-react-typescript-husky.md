---
layout: post
title: "Add Eslint & Prettier to React App"
description: "Code quality tools make easy code-styling consistency in your team. Eslint, Prettier with Husky and lint-staged are perfect match for TypeScript / JavaScript apps."
category: React
tags: [eslint, typescript, react, prettier, husky, lint-staged]
---
{% include JB/setup %}

Code quality tools make easy code-styling consistency in your team. Eslint, Prettier with Husky and lint-staged are perfect match for TypeScript / JavaScript apps.

However, adding custom eslint config with prettier to existing React codebase sometimes become confusing. But having it worth the effort.

<center>
  <img alt="Photo by Yan Ots on Unsplash" src="https://miro.medium.com/max/1400/0*7tePhONBcqUCG5_w">
  <small>Photo by Yan Ots on Unsplash</small>
</center>

Here are some notes of my own experience. I’ll try to achieve eslint assistance at-least what’s provided in CRA.

1. First, install eslint and plugins.

```bash
$ npm i -D eslint eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-jsx-a11y @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

2. Install prettier & friends.

```bash
$ npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```

3. Drop .eslintrc.js to your project root with contents:

<iframe src="https://dbtek.medium.com/media/fa2a5a3210bc8fbfb7ae9b63b366c345" allowfullscreen="" frameborder="0" height="742" width="680" scrolling="auto"></iframe>

4. Add prettier config.

<iframe src="https://dbtek.medium.com/media/a31c36e5052646c7fe296ed42671c4fd" allowfullscreen="" frameborder="0" height="170" width="680" scrolling="auto"></iframe>

Congrats. You are done!

### Bonus: Git Hooks with Husky & Lint Staged
```bash
$ npx mrm@2 lint-staged
```

Update lint-staged command as following:

```json
  "lint-staged": {
    "*.{ts,tsx}": "eslint --cache --fix"
  }
```

You should commit .husky/ & package.json changes.

### Bonus: VS Code Integration (with fix on save)

First, install [vscode-eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) extension.
Open settings.json (comb. ⌘ +⇧ + P or Ctrl + ⇧ + P).
Add following configuration:

```json
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
```

Make sure, editor.formatOnSave is not on to avoid conflicts.
