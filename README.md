# 🍄 Mario CSS Pixel Art

A learning exercise recreating 8-bit Mario using pure HTML and CSS — no images, no canvas, no JavaScript. Built with **Flexbox**.

![Mario Pixel Art](./screenshot.png)

---

## 📁 Project Structure

```
mario-pixel-art/
├── index.html   
├── style.css   
├── screenshot.png       # Preview image (see below)
└── README.md
```

---

## 🧠 How It Works

Each "pixel" is a plain `<div>` with a fixed width and height. Colors are applied via CSS classes:

| Class | Color | Represents |
|-------|-------|------------|
| `.r`  | `#c03800` | Red (hat, overalls) |
| `.y`  | `#c8a840` | Yellow (skin) |
| `.g`  | `#6c7800` | Green (shoes) |
| `.d`  | `#804000` | Dark brown (outlines) |
| `.a`  | gold | Overall buttons |
| `._`  | transparent | Empty space |

---

### Flexbox version

The sprite is a **column flex container**. Each row inside it is a **row flex container** holding 13 pixel divs.

```css
.sprite {
  display: flex;
  flex-direction: column;
}

.row {
  display: flex;
  flex-direction: row;
}

.p {
  width: 16px;
  height: 16px;
}
```

```html
<div class="sprite">
  <div class="row">
    <div class="p _"></div>
    <div class="p r"></div>
    <!-- ...11 pixels per row -->
  </div>
  <!-- ...16 rows total -->
</div>
```

**Key concept:** You control the layout by grouping children into row wrappers yourself.

---


## 🐛 Debugging Tip

To visualise the pixel grid while editing, add an outline to `.p`:

```css
.p {
  outline: 1px solid rgba(255, 255, 255, 0.3);
}
```

> Use `outline` instead of `border` — border adds to the element's box size and shifts pixels around, while outline sits outside the box and is completely non-destructive.

Remove the line when you're done.

---
