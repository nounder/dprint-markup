Packaged Pig Fang's [markup_fmt](https://github.com/g-plane/markup_fmt) to be distributed via node package manager,
similar to `@dprint/*` npm packages.

## Configuration

Configure markup_fmt in your `dprint.json` file under the `"markup"` key. For complete documentation with examples, visit [https://markup-fmt.netlify.app/](https://markup-fmt.netlify.app/) or [https://dprint.dev/plugins/markup_fmt/config/](https://dprint.dev/plugins/markup_fmt/config/).

Configuration options extracted from [config.rs](https://github.com/g-plane/markup_fmt/blob/main/dprint_plugin/src/config.rs).

### Layout Options

- **`printWidth`** (default: `80`) - Lines should stay under this width limit, though very long single words may exceed it.
- **`useTabs`** (default: `false`) - Choose between spaces or tabs for indentation.
- **`indentWidth`** (default: `2`) - Size of indentation. When `useTabs` is enabled, this option may be disregarded, since only one tab will be inserted.
- **`lineBreak`** (default: `"lf"`) - Select line break style: `"lf"` (LF) or `"crlf"` (CRLF).

### Attribute & Element Options

- **`closingBracketSameLine`** (default: `false`) - Place closing bracket on same line as last attribute.
- **`closingTagLineBreakForEmpty`** (default: `"fit"`) - Line break behavior for empty element closing tags. Options: `"always"`, `"fit"`, or `"never"`.
- **`maxAttrsPerLine`** (default: `null`) - Maximum number of attributes allowed per line.
- **`preferAttrsSingleLine`** (default: `false`) - Prefer keeping all attributes on a single line when possible.
- **`singleAttrSameLine`** (default: `true`) - Keep single attribute on same line as opening tag.

### Self-Closing Tags

- **`html.normal.selfClosing`** (default: `null`) - Self-closing behavior for normal HTML elements. Options: `"always"`, `"never"`, or `null`.
- **`html.void.selfClosing`** (default: `null`) - Self-closing behavior for void HTML elements (e.g., `<br>`, `<img>`). Options: `"always"`, `"never"`, or `null`.
- **`component.selfClosing`** (default: `null`) - Self-closing behavior for component elements. Options: `"always"`, `"never"`, or `null`.
- **`svg.selfClosing`** (default: `null`) - Self-closing behavior for SVG elements. Options: `"always"`, `"never"`, or `null`.
- **`mathml.selfClosing`** (default: `null`) - Self-closing behavior for MathML elements. Options: `"always"`, `"never"`, or `null`.

### Indentation

- **`scriptIndent`** (default: `false`) - Indent content inside `<script>` tags.
- **`html.scriptIndent`** (default: `null`) - HTML-specific override for script tag indentation.
- **`vue.scriptIndent`** (default: `null`) - Vue-specific override for script tag indentation.
- **`svelte.scriptIndent`** (default: `null`) - Svelte-specific override for script tag indentation.
- **`astro.scriptIndent`** (default: `null`) - Astro-specific override for script tag indentation.
- **`styleIndent`** (default: `false`) - Indent content inside `<style>` tags.
- **`html.styleIndent`** (default: `null`) - HTML-specific override for style tag indentation.
- **`vue.styleIndent`** (default: `null`) - Vue-specific override for style tag indentation.
- **`svelte.styleIndent`** (default: `null`) - Svelte-specific override for style tag indentation.
- **`astro.styleIndent`** (default: `null`) - Astro-specific override for style tag indentation.

### Vue Options

- **`vBindStyle`** (default: `null`) - Vue v-bind directive style. Options: `"short"` (`:`) or `"long"` (`v-bind:`).
- **`vOnStyle`** (default: `null`) - Vue v-on directive style. Options: `"short"` (`@`) or `"long"` (`v-on:`).
- **`vForDelimiterStyle`** (default: `null`) - Vue v-for delimiter style. Options: `"in"` or `"of"`.
- **`vSlotStyle`** (default: `null`) - Vue v-slot directive style. Options: `"short"` (`#`), `"long"`, or `"v-slot"`.
- **`component.vSlotStyle`** (default: `null`) - Component-specific v-slot style override.
- **`default.vSlotStyle`** (default: `null`) - Default slot style override.
- **`named.vSlotStyle`** (default: `null`) - Named slot style override.
- **`vBindSameNameShortHand`** (default: `null`) - Use shorthand syntax for same-name v-bind (e.g., `:value` instead of `:value="value"`).
- **`vueComponentCase`** (default: `"ignore"`) - Component name casing convention. Options: `"ignore"`, `"pascalCase"`, or `"kebabCase"`.

### Svelte Options

- **`strictSvelteAttr`** (default: `false`) - Apply strict formatting rules for Svelte attributes.
- **`svelteAttrShorthand`** (default: `null`) - Use Svelte attribute shorthand syntax when possible.
- **`svelteDirectiveShorthand`** (default: `null`) - Use Svelte directive shorthand syntax when possible.

### Astro Options

- **`astroAttrShorthand`** (default: `null`) - Use Astro attribute shorthand syntax when possible.

### Angular Options

- **`angularNextControlFlowSameLine`** (default: `true`) - Place Angular control flow syntax on the same line.

### Other Options

- **`quotes`** (default: `"double"`) - Quote style for attribute values. Options: `"double"` or `"single"`.
- **`formatComments`** (default: `false`) - Enable formatting of HTML comments.
- **`whitespaceSensitivity`** (default: `"css"`) - Whitespace handling mode. Options: `"css"`, `"strict"`, or `"ignore"`.
- **`component.whitespaceSensitivity`** (default: `null`) - Component-specific whitespace handling override.
- **`doctypeKeywordCase`** (default: `"upper"`) - Casing for DOCTYPE keyword. Options: `"ignore"`, `"upper"`, or `"lower"`.
- **`scriptFormatter`** (default: `"dprint"`) - Formatter to use for script content. Options: `"dprint"` or `"biome"`.
- **`ignoreCommentDirective`** (default: `"markup-fmt-ignore"`) - Comment directive to ignore formatting for the next element.
- **`ignoreFileCommentDirective`** (default: `"dprint-ignore-file"`) - Comment directive to ignore formatting for the entire file.

## Upgrade

```sh
VERSION=0.24.0

wget https://plugins.dprint.dev/g-plane/markup_fmt-v$VERSION.wasm -O plugin.wasm

# update package.json version
```

## Publishing


```sh
git tag v0.24.0
git push origin v0.24.0

bun publish
```
