---
title: Scaling background images
slug: Web/CSS/CSS_Backgrounds_and_Borders/Resizing_background_images
original_slug: Web/CSS/CSS_Backgrounds_and_Borders/Scaling_background_images
---

{{CSSRef}}

CSS 属性{{ cssxref("background-size") }} 可以用于调整背景图片的宽和高，因背景图片布局的默认行为是根据其原尺寸平铺，所以{{ cssxref("background-size") }}可修改其默认行为。你可以根据需要放大或缩小图片。

## Tiling a large image

Let's consider a large image, a 2982x2808 Firefox logo image. We want (for some reason likely involving horrifyingly bad site design) to tile four copies of this image into a 300x300-pixel element. To do this, we can use a fixed `background-size` value of 150 pixels.

### HTML

```html
<div class="tiledBackground">
</div>
```

### CSS

```css
.tiledBackground {
  background-image: url(firefox_logo.png);
  background-size: 150px;
  width: 300px;
  height: 300px;
  border: 2px solid;
  color: pink;
}
```

### Result

{{EmbedLiveSample("Tiling_a_large_image", 340, 340)}}

## Stretching an image

You can also specify both the horizontal and vertical sizes of the image, like this:

```css
background-size: 300px 150px;
```

The result looks like this:

![](ss2.png)

## Scaling an image up

On the other end of the spectrum, you can scale an image up in the background. Here we scale a 32x32 pixel favicon to 300x300 pixels:

![](ss3.png)

```css
.square2 {
  background-image: url(favicon.png);
  background-size: 300px;
  width: 300px;
  height: 300px;
  border: 2px solid;
  text-shadow: white 0px 0px 2px;
  font-size: 16px;
}
```

As you can see, the CSS is actually essentially identical, save the name of the image file.

## Special values: "contain" and "cover"

Besides {{cssxref("&lt;length&gt;")}} values, the {{ cssxref("background-size") }} CSS property offers two special size values, `contain` and `cover`. Let's take a look at these.

### `contain`

The `contain` value specifies that, regardless of the size of the containing box, the background image should be scaled so that each side is as large as possible while not exceeding the length of the corresponding side of the container. Try resizing the example below to see this in action.

#### HTML

```html
<div class="bgSizeContain">
  <p>Try resizing this element!</p>
</div>
```

#### CSS

```css
.bgSizeContain {
  background-image: url(firefox_logo.png);
  background-size: contain;
  width: 160px;
  height: 160px;
  border: 2px solid;
  color: pink;
  resize: both;
  overflow: scroll;
}
```

#### Result

{{ EmbedLiveSample('contain', 250, 250) }}

### `cover`

The `cover` value specifies that the background image should be sized so that it is as small as possible while ensuring that both dimensions are greater than or equal to the corresponding size of the container. Try resizing the example below to see this in action.

#### HTML

```html
<div class="bgSizeCover">
  <p>Try resizing this element!</p>
</div>
```

#### CSS

```css
.bgSizeCover {
  background-image: url(firefox_logo.png);
  background-size: cover;
  width: 160px;
  height: 160px;
  border: 2px solid;
  color: pink;
  resize: both;
  overflow: scroll;
}
```

#### Result

{{ EmbedLiveSample('cover', 250, 250) }}

## See also

- {{ cssxref("background-size") }}
- {{ cssxref("background") }}
- [Scaling of SVG backgrounds](/zh-CN/docs/Web/CSS/Scaling_of_SVG_backgrounds)
