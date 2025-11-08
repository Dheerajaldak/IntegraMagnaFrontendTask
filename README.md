# 🌟 Integra Magna - Frontend Developer Technical Assignment

## 🔗 Live Project Link

The live, deployed version of this project can be accessed here:
[https://integramagna-dheeraj.vercel.app/](https://integramagna-dheeraj.vercel.app/)

## 🚀 Project Overview & Approach

This project is a faithful replication of the provided landing page design, built with a strict focus on robust, modern CSS implementation.

### 1. Structure and Layout (Requirement 1, 2, 3)

* **CSS Grid Mastery (Requirement 2):** The entire page layout, including the global container (`.page-container`), header, hero section (`.hero`), and the NFT card display (`.nft-cards-grid`), is structured using **CSS Grid**. Flexbox was only used minimally for simple alignment within grid cells (e.g., aligning navigation links in `.nav`).
* **Responsiveness (Requirement 3):**
    * Media queries handle the transition from desktop (2-column hero) to tablet (1-column hero) and mobile (collapsed header/2x2 card grid).
    * **Fluid Typography:** The `clamp()` function was used for key font sizes (titles, subtitles, navigation) to ensure versatile and highly responsive text scaling across all viewport widths.
* **Design Match (Requirement 1):** The structure, layout, and color palette (`:root` variables) directly replicate the provided design and utilize all attached resources.

### 2. Theming and Interactivity (Requirement 4, Bonus)

* **Dark/Light Mode (Bonus):** Implemented using CSS Variables, which are redefined in the `.dark-theme` class. A JavaScript function (`toggleTheme()`) handles class switching and persists the user's preference using `localStorage`.
* **Smooth Transitions:** A global `--transition-speed` variable ensures smooth visual transitions for color and movement.
* **Hover Interactions (Requirement 4):**
    1.  **Buttons:** The `.btn-signup:hover` and `.btn-login:hover` styles apply background and border color shifts.
    2.  **Cards:** The `.nft-card:hover` utilizes `transform: translateY(-8px) scale(1.02)` for a subtle lifting effect.
* **Keyboard Accessibility (Bonus):** The theme toggle button has `tabindex="0"` and an event listener for `Enter` or `Space` key presses to enable keyboard-only operation.

---

## 🚧 Toughest Moment (Requirement 5)

The class that took the longest to get right was the **`.nft-cards-grid`** layout within the **mobile media query (`@media (max-width: 768px)`)**.

* **Why:** Achieving the specific 2x2 layout (Bear/Lion on Row 1, Cats/Start button on Row 2) required overriding the natural flow of the 4-item grid using explicit grid line numbers, as Flexbox was restricted for the primary layout. This involved setting `grid-column: 2 / 3;` and `grid-row: 2 / 3;` on the `start-button-container` to force it into the bottom-right quadrant. Additionally, ensuring the `start-button-container` aligned vertically with the 'Cats' card required careful balancing using `align-items: flex-start`.

---

## 🐞 Known Issues

* **Image Composition on Tablet (`@media (max-width: 1024px)`):** In the single-column tablet view, the original absolute positioning and large dimensions of the `hand-sculpture` image caused severe content overlap and breaking of the responsive flow. To maintain a clean layout, the `hand-sculpture` is explicitly hidden (`display: none;` is recommended, though the current code uses `width: 0%`) and the `floating-stone` is heavily reduced in size and repositioned within the tablet media query.
* **Text Background Compatibility:** The non-standard property `background-clip: text` is used for the `.title-digital` and `.title-renaissance` elements and requires the `-webkit-` prefix for wider browser compatibility.
