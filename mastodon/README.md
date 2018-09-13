# mastodon
> A shortcode for including Mastodon statuses on your website

## Setup

First copy the `mastodon.html` file to your themes shortcodes directory. This is either `layouts/shortcodes` or `themes/{your-theme}/layouts/shortcodes`.

Then add the following code to your `footer.html` or anywhere you define your websites footer content.

```html
{{ if ($.Page.Scratch.Get "include_mastodon") "true" }}
<script src="https://mastodon.social/embed.js" async="async"></script>
{{ end }}
```
**Note: You can change the instance from which the embed.js is loaded or re-host it on your own servers!**


## Usage

The Mastodon shortcode takes the following arguments.

| Argument | Default Value | Values | Description |
|-----------|--------------|--------|-------------|
|`status`| - | String | Status ID taken from the URL of a toot. |
|`width`| 400 | Number | The width of the embeded iframe|
|`height`| 333 | Number | The height of the embeded iframe|

### Example Usage

### Live Example
A live example can be [seen on my website](https://www.kevingimbel.com/mastodon-embed-shortcode-for-hugo/)

**Minimal options**

```html
{{% mastodon status="https://mastodon.social/@kevingimbel/100700713283716694" %}}
```

**All options**

```html
{{% mastodon status="https://mastodon.social/@kevingimbel/100700713283716694" width="600" height="300" %}}
```