# Testing Library Snippets (WIP)

[![Version](https://img.shields.io/visual-studio-marketplace/v/deinsoftware.testing-library-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deinsoftware.testing-library-snippets)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/deinsoftware.testing-library-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deinsoftware.testing-library-snippets)
[![Ratings](https://img.shields.io/visual-studio-marketplace/stars/deinsoftware.testing-library-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deinsoftware.testing-library-snippets)
[![license](https://img.shields.io/github/license/deinsoftware/vscode-testing-library-snippets)](LICENSE.md)
[![Open in VS Code](https://img.shields.io/static/v1?logo=visualstudiocode&label=&message=Open%20in%20Visual%20Studio%20Code&labelColor=2c2c32&color=007acc&logoColor=007acc)](https://open.vscode.dev/deinsoftware/vscode-testing-library-snippets)

![Testing Library](https://raw.githubusercontent.com/deinsoftware/vscode-testing-library-snippets/main/.github/social/preview.png)

The quick and easy way to create and use Testing Library with [VS Code](https://code.visualstudio.com/).

> We also **recommend** installing his complement extension [Vitest Snippets](https://marketplace.visualstudio.com/items?itemName=deinsoftware.vitest-snippets)

## Menu

- [Installation](#installation)
  - [Quick Launch](#quick-launch)
  - [Extension Manager](#extension-manager)
  - [Marketplace](#marketplace)
- [Supported Languages](#supported-languages)
- [Cheat Sheet](#cheat-sheet)
- [Snippets](#snippets)
  - [Import](#import)
  - [User Event](#user-event)
  - [Queries](#queries)
  - [Regex](#regex)
- [Keyboard](#keyboard)
- [Settings](#settings)
- [About](#about)

---

## Installation

### Quick Launch

Open the quick launch with <kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>P</kbd> (Win/Linux) or <kbd>cmd</kbd>+<kbd>shift</kbd>+<kbd>P</kbd> (macOS).

Paste the following command and press `Enter`:

```shell
ext install deinsoftware.testing-library-snippets
```

### Extension Manager

Open the extension manager with <kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>X</kbd> (Win/Linux) or <kbd>cmd</kbd>+<kbd>shift</kbd>+<kbd>X</kbd> (macOS), search for `Testing Library Snippets` and click on `[Install]` button.

### Marketplace

[Testing Library Snippets](https://marketplace.visualstudio.com/items?itemName=deinsoftware.testing-library-snippets)

⇧ [Back to menu](#menu)

---

## Supported Languages

| Language         | Extension |
| ---------------- | --------- |
| JavaScript       | `.js`     |
| TypeScript       | `.ts`     |
| JavaScript React | `.jsx`    |
| TypeScript React | `.tsx`    |
| Vue              | `.vue`    |

⇧ [Back to menu](#menu)

---

## Cheat Sheet

| Search Variants  | Result                                        |
| ---------------- | --------------------------------------------- |
| `getBy...`       | `Element` or `Error`                          |
| `getAllBy...`    | `Element[]` or `Error`                        |
| `queryBy...`     | `Element` or `null`                           |
| `queryAllBy...`  | `Element[]` or `null`                         |
| `findBy...`      | `Promise<Element>` or `Promise<rejection>`    |
| `findAllBy...`   | `Promise<Element[]>` or `Promise<rejection>`  |

| Search Types          | Result                                        |
| --------------------- | --------------------------------------------- |
| `...Role`             | `<div aria="role">` or [Aria Roles](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#roles)  |
| `...LabelText`        | `<label for="Text">`                          |
| `...PlaceHolderText`  | `<input placeholder="Text">`                  |
| `...Text`             | `<a href="/page">Text</a>`                    |
| `...DisplayValue`     | `<input value="Text">`                        |
| `...AltText`          | `<img alt="Text">`                            |
| `...Title`            | `<span title="Text">` or `<title>`            |
| `...TestId`           | `<input data-testid="Id">`                    |

⇧ [Back to menu](#menu)

---

## Snippets

Below is a list of all available snippets and the triggers of each one. The `░` means the `TAB` jump position and `█` the final cursor position.

### Import

|  Trigger | Result                                                              |
| -------: | ------------------------------------------------------------------- |
|   `itl→` | `import { render, screen } from '@testing-library/░<react\|vue>'█`  |
|   `itr→` | `import { render, screen } from '@testing-library/react'█`          |
|   `itv→` | `import { render, screen } from '@testing-library/vue'█`            |
|  `itrh→` | `import { renderHook } from '@testing-library/react'█`              |
|  `itue→` | `import user from '@testing-library/user-event'█`                   |

### User Event

|  Trigger | Result                                                                 |
| -------: | ---------------------------------------------------------------------- |
|  `beus→` | <code>beforeEach(() => {<br/>&nbsp;&nbsp;user.setup()<br/>})█</code>   |

### Queries

|  Trigger  | Result                                                           |
| --------: | ---------------------------------------------------------------- |
|   `gbr→`  | `screen.getByRole('░id')█`                                       |
|  `gbro→`  | `screen.getByRole('░id', {░})█`                                  |
|  `gbrc→`  | `screen.getByRole('checkbox')█`                                  |
| `gbrcc→`  | `screen.getByRole('checkbox', { checked: ░<true\|false>} })█`    |
|  `gbrh→`  | `screen.getByRole('heading')█`                                   |
| `gbrhl→`  | `screen.getByRole('heading', { level: ░<1\|2\|3\|4\|5\|6>} })█`  |
|  `gabr→`  | `screen.getAllByRole('░id')█`                                    |
| `gabro→`  | `screen.getAllByRole('░id', {░})█`                               |
|   `gbt→`  | `screen.getByText(░)█`                                           |
|  `gbtf→`  | `screen.getByText('░Text Match')█`                               |
|  `gbti→`  | `screen.getByText('░text match', {ignore: false})█`              |
|  `gbts→`  | `screen.getByText('░ext Matc', {exact: false})█`                 |
| `gbtsi→`  | `screen.getByText('░ext matc', {exact: false, ignore: false})█`  |
| `gbtsw→`  | `screen.getByText((content) => content.startsWith('░Text'))█`    |
| `gbtesw→` | <code>screen.getByText((content, element) => {<br/>&nbsp;&nbsp;return element.tagName.toLowerCase() === '░div' && content.startsWith('░Text')<br/>})█</code>   |
| `gbtew→`  | `screen.getByText((content) => content.endsWith('░Match'))█`     |
| `gbteew→` | <code>screen.getByText((content, element) => {<br/>&nbsp;&nbsp;return element.tagName.toLowerCase() === '░div' && content.endsWith('░Match')<br/>})█</code>    |

### Debug

|  Trigger | Result                               |
| -------: | ------------------------------------ |
|    `sd→` | `screen.debug()█`                    |
|  `sltp→` | `screen.logTestingPlaygroundURL()█`  |

### Regex

It can be used as a text matcher or `name` property on queries.

| Trigger | Description                 | Result              |
| ------: | --------------------------- | ------------------- |
|   `rf→` | full text match             | `/^░Text Match$/█`  |
|  `rfi→` | full text match ignore case | `/^░text match$/i█` |
|   `rs→` | substring match             | `/░ext Matc/█`      |
|  `rsi→` | substring match ignore case | `/░ext matc/i█`     |
|  `rsw→` | start with                  | `/^░Text/█`         |
| `rswi→` | start with ignore case      | `/^░text/i█`        |
|  `rew→` | end with                    | `/░Match$/█`        |
| `rewi→` | end with ignore case        | `/░match$/i█`       |

⇧ [Back to menu](#menu)

---

## Keyboard

Remember to complement the snippets with these keyboard shortcuts that can be used without needing to move the cursor to the start or to the end.

| Action            | Win/Linux          | macOS             |
| ----------------- | -----------------: | ----------------: |
| Insert line above | `ctrl+shift+enter` | `cmd+shift+enter` |
| Insert line below | `ctrl+enter`       | `cmd+enter`       |

⇧ [Back to menu](#menu)

---

## Settings

The `editor.snippetSuggestions` setting in vscode `settings.json` will show snippets on top of the suggestion list.

```json
"editor.snippetSuggestions": "top"
```

⇧ [Back to menu](#menu)

---

## About

### Fork

- [vscode-jest-snippets](https://github.com/andys8/vscode-jest-snippets) - Jest snippets extension for VS Code

### Built With

- [VS Code](https://code.visualstudio.com/) - Code editing redefined.
- [Figma](https://www.figma.com/) - The collaborative interface design tool.
- [SWPM](https://www.npmjs.com/package/swpm) - One Package Manager to command them all.

### Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

### Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [Const & Props Snippets](https://github.com/deinsoftware/vscode-testing-library-snippets/tags) on GitHub.

### Authors

- **Camilo Martinez** [[Equiman](http://github.com/equiman)]

See also the list of [contributors](https://github.com/deinsoftware/vscode-testing-library-snippets/contributors) who participated in this project.

### Sponsors

If this project helps you, consider buying me a cup of coffee.

[![GitHub Sponsors](https://img.shields.io/badge/-GitHub%20Sponsors-gray?style=flat&labelColor=171515&logo=github&logoColor=white&link=https://github.com/sponsors/deinsoftware)](https://github.com/sponsors/deinsoftware)
[![paypal](https://img.shields.io/badge/-PayPal-gray?style=flat&labelColor=00457C&logo=paypal&logoColor=white&link=https://paypal.me/equiman/3)](https://paypal.me/equiman/3)

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

⇧ [Back to menu](#menu)
