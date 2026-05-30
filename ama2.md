# AMA Session Questions and Answers

### 1. Adhikya Edammala: Describe in-the-flow and out-of-the-flow in HTML

* **In-the-flow:** Elements follow the normal document layout.
* **Out-of-the-flow:** Elements are removed from the normal layout using position: absolute, position: fixed.

---

### 2. Allanki VV Manikanta Sai: What are void elements?

Void elements are HTML elements that do not have a closing tag and cannot contain content.

Examples:

```html
<img>
<br>
<hr>
```

---

### 3. Arpit Yadav: What is order in Flexbox?

The order property changes the visual order of flex items without changing the HTML structure.

```css
.item {
  order: 2;
}
```

Lower order values appear first.

---

### 4. Boorle Sowmya Sri Lakshmi: What does row-reverse value of flex-direction do?

It arranges flex items horizontally from right to left instead of the default left to right.


---

### 5. Injamuri Arun Kumar: Difference between rowspan and colspan

* rowspan: Makes a table cell span multiple rows.
* colspan: Makes a table cell span multiple columns.

---

### 6. Kamparapu Lakshman: How do you create a hyperlink in HTML?

Using the anchor tag.

---

### 7. M Harivardhan Reddy: What makes a website responsive?

* Flexible layouts (Flexbox/Grid)
* Relative units (%, rem, vw)
* Media queries

---

### 8. Md Musharaf: Which media query checks the orientation of a device?

```css
@media (orientation: portrait) {

}

@media (orientation: landscape) {

}
```

---

### 9. Naman Sharma: What does target="_blank" do?

It opens the linked page in a new browser tab or window.

---

### 10. Nayunipatruni Harsha Vardhan: Difference between object-fit: cover and contain

**cover**

* Fills the entire container.
* May crop the image.

**contain**

* Shows the entire image.
* May leave empty space.

---

### 11. Parlapalli Sulochana: What is gap in Flexbox and Grid?

gap creates space between items without using margins.

Works in both Flexbox and Grid.

---

### 12. Rongala Vasu: Can we use cover and contain for background images?

Yes, using background-size.

* cover fills the container.
* contain shows the whole image.

---

### 13. Rovinpal Udupi: Tag used to create a dropdown list

```html
<select>
  <option>HTML</option>
  <option>CSS</option>
</select>
```

---

### 14. Tumma Haritha: What is clear in float?

The clear property prevents an element from sitting next to floated elements.

```css
.clearfix {
  clear: both;
}
```
---

### 15. Yash Nitin Raut: Can we write HTML in a case-insensitive way?

Yes. HTML tag names and attributes are generally case-insensitive.
---

