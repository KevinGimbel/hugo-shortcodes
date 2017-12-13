# caniuse
> A shortcode for including CanIUse.com embeds on your website

## Setup

First copy the `caniuse.html` file to your themes shortcodes directory. This is either `layouts/shortcodes` or `themes/{your-theme}/layouts/shortcodes`.

Then add the following code to your `footer.html` or anywhere you define your websites footer content.

```html
{{ if ($.Page.Scratch.Get "include_caniuse") "true" }}
<script async src="//cdn.jsdelivr.net/caniuse-embed/1.1.0/caniuse-embed.min.js"></script>
{{ end }}
```

This will load the caniuse embed script everytime a caniuse shortcode has been used. This shortcode uses the excellent [caniuse embed script](https://github.com/ireade/caniuse-embed/) by [Ire Aderinokun](https://github.com/ireade).

## Usage

The caniuse shortcode takes the following arguments.

| Argument | Default Value | Values | Description |
|----------|---------------|--------|-------------|
| `feature` | - | String | The feature to inclide, e.g. `css-variables`, `css-grid`, etc. |
| `periods` | `future_1,current,past_1,past_2` | String | How many past / future browsers to display. See periods below |

List of **periods**  which can be used:
- `future_3`
- `future_2`
- `future_1`
- `current`
- `past_1`
- `past_2`
- `past_3`
- `past_4`
- `past_5`


### Example Usage

**Minimal options**

```html
{{% caniuse feature="css-variables" %}}
```

**All options**

```html
{{% caniuse feature="css-grid" periods="current,past_1,past_2" %}}
```

### Live Example

The caniuse shortcode is used on my private site, for example in the article ["CSS Custom Properties and a new look"](https://www.kevingimbel.com/css-custom-properties-and-a-new-look/).
