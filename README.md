# Testing Library Snippets

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
  - [Wait](#wait)
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

You can write queries with any combination of **Search variants** and **Search types**.

### Search variants

| Variants        | Return if no match | Return if 1 match | Return if 1+ match | Await? |
| --------------- | ------------------ | ----------------- | ------------------ | ------ |
| `getBy`...      | throw              | return            | throw              | No     |
| `getAllBy`...   | throw              | array             | array              | No     |
| `queryBy`...    | `null`             | return            | throw              | No     |
| `queryAllBy`... | `[]`               | array             | array              | No     |
| `findBy`...     | throw              | return            | throw              | Yes    |
| `findAllBy`...  | throw              | array             | array              | Yes    |

### Search types

Sorted by oficial recommended [order of priority](https://testing-library.com/docs/queries/about/#priority).

|   | Types                | finds by...                      | DOM example                           |
| - | -------------------- | -------------------------------- | ------------------------------------- |
| 1 | ...`Role`            | [ARIA role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#roles)                        | `<div role="dialog" />`               |
| 2 | ...`LabelText`       | label or aria-label content      | `<label for="element" />`             |
| 3 | ...`PlaceholderText` | input placeholder value          | `<input placeholder="name" />`        |
| 4 | ...`Text`            | element text content             | `<p>Lorem ipsum</p>`                  |
| 5 | ...`DisplayValue`    | form element current value       | `<input value="Current Value">`       |
| 6 | ...`AltText`         | img alt attribute                | `<img alt="movie poster" />`          |
| 7 | ...`Title`           | title attribute or svg title tag | `<span title="Add" />` or `<title />` |
| 8 | ...`TestId`          | data-testid attribute            | `<div data-testid="some-message" />`  |

> For more information visit the oficial cheat sheet: [DOM](https://testing-library.com/docs/dom-testing-library/cheatsheet) - [React](https://testing-library.com/docs/react-testing-library/cheatsheet) - [Vue](https://testing-library.com/docs/vue-testing-library/cheatsheet)

⇧ [Back to menu](#menu)

---

## Snippets

Below is a list of all available snippets and the triggers of each one. The `░` means the `TAB` jump position and `█` the final cursor position.

### Import

|  Trigger | Result                                                              |
| :------- | ------------------------------------------------------------------- |
| `itl→`   | `import { render, screen } from '@testing-library/░<react\|vue>'█`  |
| `itr→`   | `import { render, screen } from '@testing-library/react'█`          |
| `itv→`   | `import { render, screen } from '@testing-library/vue'█`            |
| `itrh→`  | `import { renderHook } from '@testing-library/react'█`              |
| `itue→`  | `import userEvent from '@testing-library/user-event'█`              |

### User Event

|  Trigger | Result                                                                      |
| :------- | --------------------------------------------------------------------------- |
| `es→`    | `userEvent.setup()█`                                                        |
| `bees→`  | <code>beforeEach(() => {<br/>&nbsp;&nbsp;userEvent.setup()<br/>})█</code>   |
| `ec→`    | `await userEvent.click(░element)█`                                          |
| `edc→`   | `await userEvent.dblClick(░element)█`                                       |
| `et→`    | `await userEvent.type(░element, '░text')█`                                  |
| `ets→`   | ``await userEvent.type(░element, `░text{enter}`)█``                         |
| `ecl→`   | `await userEvent.clear(░element)█`                                          |
| `eso→`   | `await userEvent.selectOptions(░element, ['░value/label'])█`                |
| `edo→`   | `await userEvent.deselectOptions(░element, ['░value/label'])█`              |
| `etb→`   | `await userEvent.tab()█`                                                    |
| `eh→`    | `await userEvent.hover(░element)█`                                          |
| `euh→`   | `await userEvent.unhover(░element)█`                                        |
| `ep→`    | `await userEvent.paste(░element, '░text')█`                                 |

### Queries

All the `░variantBy` cursor start with `getBy` by default, but can be easily changed between `<getBy|getAllBy|queryBy|queryAllBy|findBy|findByAll>` using arrow keys once reach the TAB position.

![Variant Snippets Example](https://raw.githubusercontent.com/deinsoftware/vscode-testing-library-snippets/main/.github/examples/variant-snippets.gif)

#### 1. Role

|  Trigger | Result                                                                                              |
| :------- | --------------------------------------------------------------------------------------------------- |
| `qr→`    | `screen.░variantByRole('░id')█`                                                                     |
| `qro→`   | `screen.░variantByRole('░id', {░})█`                                                                |
| `qron→`  | `screen.░variantByRole('░id', {name: ░})█`                                                          |
| `qrc→`   | `screen.░variantByRole('checkbox')█`                                                                |
| `qrcc→`  | <code>screen.░variantByRole('checkbox', { checked: ░<true&#124;false>} )█</code>                    |
| `qrh→`   | `screen.░variantByRole('heading')█`                                                                 |
| `qrhl→`  | <code>screen.░variantByRole('heading', { level: ░<1&#124;2&#124;3&#124;4&#124;5&#124;6>} )█</code>  |

#### 2. LabelText

|  Trigger | Result                                                                          |
| :------- | ------------------------------------------------------------------------------- |
| `ql→`    | `screen.░variantByLabelText(░)█`                                                |
| `qlf→`   | `screen.░variantByLabelText('░Text Match')█`                                    |
| `qls→`   | `screen.░variantByLabelText('░ext Matc', {exact: false})█`                      |
| `qlq→`   | `screen.░variantByLabelText('░Text Match', {selector: '░query'})█`              |
| `qlsq→`  | `screen.░variantByLabelText('░ext matc', {exact: false, selector: '░query'})█`  |

#### 4. Text

|  Trigger | Result                                                                |
| :------- | --------------------------------------------------------------------- |
| `qt→`    | `screen.░variantByText(░)█`                                           |
| `qtf→`   | `screen.░variantByText('░Text Match')█`                               |
| `qti→`   | `screen.░variantByText('░text match', {ignore: false})█`              |
| `qts→`   | `screen.░variantByText('░ext Matc', {exact: false})█`                 |
| `qtsi→`  | `screen.░variantByText('░ext matc', {exact: false, ignore: false})█`  |
| `qtsw→`  | `screen.░variantByText((content) => content.startsWith('░Text'))█`    |
| `qtesw→` | <code>screen.░variantByText((content, element) => {<br/>&nbsp;&nbsp;const tag = element.tagName.toLowerCase() === '░div'<br/>&nbsp;&nbsp;return tag && content.startsWith('░Text')<br/>})█</code>   |
| `qtew→`  | `screen.░variantByText((content) => content.endsWith('░Match'))█`     |
| `qteew→` | <code>screen.░variantByText((content, element) => {<br/>&nbsp;&nbsp;const tag = element.tagName.toLowerCase() === '░div'<br/>&nbsp;&nbsp;return tag && content.endsWith('░Match')<br/>})█</code>    |

#### 5. PlaceholderText

|  Trigger | Result                                                            |
| :------- | ----------------------------------------------------------------- |
| `qp→`    | `screen.░variantByPlaceholderText(░)█`                            |
| `qpf→`   | `screen.░variantByPlaceholderText('░Text Match')█`                |
| `qps→`   | `screen.░variantByPlaceholderText('░ext Matc', {exact: false})█`  |

#### 6. DisplayValue

|  Trigger | Result                                                         |
| :------- | -------------------------------------------------------------- |
| `qd→`    | `screen.░variantByDisplayValue(░)█`                            |
| `qdf→`   | `screen.░variantByDisplayValue('░Text Match')█`                |
| `qds→`   | `screen.░variantByDisplayValue('░ext Matc', {exact: false})█`  |

#### 7. AltText

|  Trigger | Result                                                    |
| :------- | --------------------------------------------------------- |
| `qa→`    | `screen.░variantByAltText(░)█`                            |
| `qaf→`   | `screen.░variantByAltText('░Text Match')█`                |
| `qas→`   | `screen.░variantByAltText('░ext Matc', {exact: false})█`  |

#### 8. Title

|  Trigger | Result                                                  |
| :------- | ------------------------------------------------------- |
| `qtt→`   | `screen.░variantByTitle(░)█`                            |
| `qttf→`  | `screen.░variantByTitle('░Text Match')█`                |
| `qtts→`  | `screen.░variantByTitle('░ext Matc', {exact: false})█`  |

#### 9. TestId

|  Trigger | Result                                                   |
| :------- | -------------------------------------------------------- |
| `qtid→`  | `screen.░variantByTestId(░)█`                            |
| `qtidf→` | `screen.░variantByTestId('░Text Match')█`                |
| `qtids→` | `screen.░variantByTestId('░ext Matc', {exact: false})█`  |

### Debug

|  Trigger | Result                               |
| :------- | ------------------------------------ |
| `sd→`    | `screen.debug()█`                    |
| `sltp→`  | `screen.logTestingPlaygroundURL()█`  |

### Regex

It can be used as a text matcher or `name` property on queries.

| Trigger | Description                 | Result              |
| :------ | --------------------------- | ------------------- |
| `rf→`   | full text match             | `/^░Text Match$/█`  |
| `rfi→`  | full text match ignore case | `/^░text match$/i█` |
| `rs→`   | substring match             | `/░ext Matc/█`      |
| `rsi→`  | substring match ignore case | `/░ext matc/i█`     |
| `rsw→`  | start with                  | `/^░Text/█`         |
| `rswi→` | start with ignore case      | `/^░text/i█`        |
| `rew→`  | end with                    | `/░Match$/█`        |
| `rewi→` | end with ignore case        | `/░match$/i█`       |

### Wait

|  Trigger | Result                                                                          |
| :------- | ------------------------------------------------------------------------------- |
| `wf→`    | <code>await waitFor(<br/>&nbsp;&nbsp;() => ░<br/>)█</code>                      |
| `wfr→`   | <code>await waitForElementToBeRemoved(<br/>&nbsp;&nbsp;() => ░<br/>)█</code>    |

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
