# Animated FAQ Accordion

### ₊⊹ About

Frequently asked questions section in accordion format, titled “Got Questions?” and featuring three cards.
Each card has an icon, a question, and a + button that changes to an X when the answer is open.
When clicked, the card expands with a smooth animation and highlights the border, displaying the answer directly below.
Only one question is open at a time, which keeps the list organized and easy to read.

https://github.com/user-attachments/assets/6f91ff9e-efdc-4554-922b-b63632fcf8ab

---

### ★ Features

- **Interactive accordion:** Each question is a card that expands when clicked and displays the answer directly below it.

- **One open question at a time:** When you open a card, the others close.

- **Close by clicking again:** Clicking the open card closes it.

- **Button that turns into an X:** The + rotates 45° when the card is open.

- **Icons per question:** lightbulb, rocket, and magic wand, from Font Awesome.

- **Animated expansion:** the answer’s height appears smoothly, without fixed pixel values.

- **Highlighting the active item:** The open card gets a light border, and the icon rotates and enlarges slightly.

- First card opens when the page loads.

- **Accessible:** Uses `<button>` and updates the `aria-expanded` attribute.

- Dark, bluish visual style with a centered layout.

---

### .ᐟ.ᐟ How It Works

- **Structure (HTML):** Each question is an .item with a <button class="question"> (icon, text, and +) and a <div class="answer"> containing the answer text. The selected item is assigned the “active” class.

- **Selection (JS):** The script retrieves all .item elements using querySelectorAll and sets an onclick event on each button.

- **Open/Close Logic:** When clicked, the JS sets the item to “open” if it was already active. It then removes the “active” class from all items and sets `aria-expanded=“false”` on each button. Only if the clicked item was not already open does it receive the ‘active’ class and `aria-expanded=“true”`. This ensures only one item is open at a time, and clicking the open card closes it.

- **Answer expansion (CSS):** The `.answer` is a grid with `grid-template-rows: 0fr`, and in the active item it becomes `1fr`. With `transition: 0.3s`, the height animates smoothly without needing fixed values. The `overflow: hidden` on `<p>` hides the text while it’s closed.

- **Button that turns into an X:** The + icon rotates 45° on the active item (rotate(45deg)), making it look like an X.

- **Highlighting the active item:** The border changes color, and the card icon rotates and scales up slightly (rotate(-12deg) scale(1.1)).

- **Accessibility:** The `aria-expanded` attribute informs screen readers whether each question is open or closed.

---

### ⚙️ Tech Stack

- **HTML5**
- **CSS3**
- **JavaScript (Vanilla)**
- **Font Awesome 6.5.2:** icons for the questions, the “+” button, and the title, loaded via CDN.

---

### 🖿 Project structure

```
animated-faq-accordion/
├── index.html
├── style.css
├── script.js
└── README.md
```

---

### 📖 What i learned

- **Accordion with one item open at a time:** Remove the “active” class from all items before opening the one that was clicked.

- **Toggle open and closed:** Keep track of whether the item was already open so that clicking it again closes it.

- **Animate height with CSS:** use `grid-template-rows` from 0fr to 1fr and let the layout expand without a fixed height.

- **Hide content with `overflow: hidden`:** the text does not appear while the area is closed.

- **CSS transformations:** rotate the + by 45° to turn it into an X and apply a `rotate` with `scale` to the active item’s icon.

- **Class-controlled state:** JavaScript only adds or removes the `active` class, and CSS handles all the styling.

- **Accessibility with ARIA:** Use `<button>` and update `aria-expanded` with `setAttribute`.

- **Combined selectors:** Write rules like `.item.active .answer` to style elements within an active item.

- **Font Awesome via CDN:** Use icons with the `fa-solid` and `fa-regular` classes.
