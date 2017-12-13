# codepen
> A shortcode for including CodePen embeds on your website

## Setup

First copy the `codepen.html` file to your themes shortcodes directory. This is either `layouts/shortcodes` or `themes/{your-theme}/layouts/shortcodes`.

Then add the following code to your `footer.html` or anywhere you define your websites footer content.

```html
{{ if ($.Page.Scratch.Get "include_codepen") "true" }}
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>
{{ end }}
```

This will load the CodePen embed script everytime a CodePen shortcode has been used.

## Usage

The CodePen shortcode takes the following arguments.

| Argument | Default Value | Values | Description |
|----------|---------------|--------|-------------|
| `height` | 256 | Number | Height of the embedded iFrame |
| `theme` | `dark` | String | The theme which will be used |
| `result` | `html,result` | Comma separated list. Any of `css`, `js`, `html`, `result`  | The tabs which will be shown in the embed by default |
| `user` | String |Site Config | The user to which this Pen belongs |
| `editable` | true or false | Site Config | Defines if the CodePen is editable by the user |
| `preview` | true or false | Site Config | Defines if the CodePen has "Run Pen" button or loads by default |
| `slug` | - | CodePen Slug (alphanumeric) | The Slug of the Pen |
| `title` | - | String | The title of the pen, shown if the embed can't be loaded |

`user`, `editable`, and `preview` can be configured in your site config (e.g. `config.yaml` or `config.toml`), as shown in the example below.

```yaml
# hugo config.yml file

params:
  shortcodes:
    codepen:
      user: "kevingimbel"
      editable: true
      preview: true
```

I use [this configuration](https://github.com/kevingimbel/kevingimbel.com/blob/c82aa6a38b170b628435461e85450a031fb4a945/config.yaml#L57-L61) for my website.

### Example Usage

**Minimal options**

```html
{{% codepen slug="78d261a36ecded2b75d5260cb7056fce" title="An example embed" %}}
```

**All options**

```html
{{% codepen slug="78d261a36ecded2b75d5260cb7056fce" title="An example embed" height="300" theme="light" result="css,js" user="ausername" editable="false" preview="false" %}}
```

### Live Example

The CodePen shortcode is used on my private site, for example in the article ["CSS Custom Properties and a new look"](https://www.kevingimbel.com/css-custom-properties-and-a-new-look/).
