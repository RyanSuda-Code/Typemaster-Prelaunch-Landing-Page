### 📘 What I Learned 

- Use a `position: relative` parent and a `position: absolute` child with `inset: 0` to create a perfect color overlay.
- Avoid repeating width and height — the overlay automatically matches the parent’s size.
- Do not use `z-index: -1` because it causes stacking and layout issues; keep the image in normal flow.
- Use `overflow: hidden` and matching `border-radius` so the overlay clips correctly and follows the image’s shape.
- This method is clean, responsive, and easier to maintain for future layout changes.
- This project uses the HTML <picture> element to load different images based on screen size.
- Loads only the needed image (better performance)

### 📁 Code Example (Image With Color Overlay)


<div class="image-container1">
  <div class="image-sleeve"></div>
</div>

```css
.image-container1 {
  background: url(./assets/desktop/image-phone-and-keyboard.jpg) no-repeat center/cover;
  width: 255px;
  height: 480px;
  border-radius: 15px;
  position: relative;
  overflow: hidden;
}

.image-sleeve {
  background-color: rgba(241, 103, 24, 0.5);
  position: absolute;
  inset: 0;
  border-radius: 15px;
}

```html
<picture>
  <source media="(max-width: 768px)" srcset="image-mobile.jpg">
  <source media="(max-width: 1024px)" srcset="image-tablet.jpg">
  <img src="image-desktop.jpg" alt="Feature image">
</picture>
