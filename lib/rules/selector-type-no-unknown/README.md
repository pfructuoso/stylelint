# selector-type-no-unknown

Disallow unknown type selectors.

```css
    unknown {}
/** ↑
 * This type selector */
```

This rule considers tags which are valid custom elements and those defined in the following Specifications to be known: HTML and SVG.

## Options

### `true`

The following patterns are considered warnings:

```css
unknown {}
```

```css
tag {}
```

The following patterns are *not* considered warnings:

```css
input {}
```

```css
ul li {}
```

```css
li > a {}
```

## Optional secondary options

### `ignore: ["default-namespace", "custom-elements"]`

#### `"default-namespace"`

Allow unknown type selectors if they belong to the default namespace.

The following patterns are considered warnings:

```css
namespace|unknown {}
```

The following patterns are *not* considered warnings:

```css
unknown {}
```

#### `"custom-elements"`

Allow custom elements.

The following patterns are considered warnings:

```css
unknown {}
```

```css
x-Foo {}
```

The following patterns are *not* considered warnings:

```css
x-foo {}
```

### `ignoreNamespaces: ["/regex/", "string"]`

Given:

```js
["/^my-/", "custom-namespace"]
```

The following patterns are *not* considered warnings:

```css
custom-namespace|unknown {}
```

```css
my-namespace|unknown {}
```

```css
my-other-namespace|unknown {}
```

### `ignoreTypes: ["/regex/", "string"]`

Given:

```js
["/^my-/", "custom-type"]
```

The following patterns are *not* considered warnings:

```css
custom-type {}
```

```css
my-type {}
```

```css
my-other-type {}
```
