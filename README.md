# dprint-style

Packaged Pig Fang's [malva](https://github.com/g-plane/malva) to be distributed via node package manager,
similar to `@dprint/*` npm packages.

It formats CSS, SCSS, Sass and Less.

## Configuration

Put config under `"malva"` key in your `dprint.json`.

Sourced from [Malva docs](https://malva.netlify.app/print.html).

- `printWidth` (default: `80`) - Lines should stay under this width limit, though very long single words may exceed it.
- `useTabs` (default: `false`) - Choose between spaces or tabs for indentation.
- `indentWidth` (default: `2`) - Size of indentation. When `useTabs` is enabled, this option may be disregarded, since only one tab will be inserted.
- `lineBreak` (default: `"lf"`) - Select line break style: `"lf"` (LF) or `"crlf"` (CRLF).
- `hexCase` (default: `"lower"`) - Options: `"lower"`, `"upper"`, or `"ignore"` for hex color case conversion.
- `hexColorLength` (default: `null`) - Options: `null` (keep as-is), `"short"`, or `"long"` for hex color formatting.
- `quotes` (default: `"alwaysDouble"`) - Options include `"alwaysDouble"`, `"alwaysSingle"`, `"preferDouble"`, and `"preferSingle"` for string quotes.
- `declarationOrder` (default: `null`) - Sorting strategies: `"alphabetical"`, `"smacss"`, or `"concentric"`; `null` disables sorting.
- `declarationOrderGroupBy` (default: `"nonDeclaration"`) - Determines grouping boundaries: `"nonDeclaration"` or `"nonDeclarationAndEmptyLine"`.
- `operatorLinebreak` (default: `"after"`) - Line break placement relative to operators: `"before"` or `"after"`.
- `blockSelectorLinebreak` (default: `"consistent"`) - Selector formatting: `"always"`, `"consistent"`, or `"wrap"` after commas.
- `singleLineBlockThreshold` (default: `null`) - Integer value for single-line block eligibility; useful for atomic CSS.
- `linebreakInPseudoParens` (default: `false`) - Insert line breaks within pseudo-class/element parentheses when lines exceed width.
- `formatComments` (default: `false`) - Control whether whitespace should be inserted at the beginning and end of comments.
- `alignComments` (default: `true`) - Adjust multi-line comment indentation alignment.
- `omitNumberLeadingZero` (default: `false`) - Remove leading zeros before decimal points (`0.5px` → `.5px`).
- `trailingComma` (default: `false`) - Add trailing commas to Sass/Less lists and parameters.
- `keyframeSelectorNotation` (default: `null`) - Use `"keyword"` (from/to), `"percentage"`, or `null` (keep as-is).
- `attrValueQuotes` (default: `"always"`) - Add quotes to unquoted attribute values: `"always"` or `"ignore"`.
- `preferSingleLine` (default: `false`) - Consolidate multi-line items to single lines when possible.
- `singleLineTopLevelDeclarations` (default: `false`) - Force top-level declarations onto single lines (removes trailing semicolons).
- `selectorOverrideCommentDirective` (default: `"malva-selector-override"`) - Comment syntax for overriding individual selector formatting without affecting entire rules.
- `ignoreCommentDirective` (default: `"malva-ignore"`) - Comment syntax for excluding specific statements from formatting.
- `ignoreFileCommentDirective` (default: `"malva-ignore-file"`) - Comment syntax to skip formatting an entire file.

## Upgrade

```sh
VERSION=0.15.0

wget https://plugins.dprint.dev/g-plane/malva-v${VERSION}.wasm -O plugin.wasm

# update package.json version
```

## Publishing


```sh
git tag v0.15.0
git push origin v0.15.0

bun publish
```
