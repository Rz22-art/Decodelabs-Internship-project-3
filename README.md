# 🌿 FRAIS — High-Fidelity UI Design Specification

A premium, modern Organic Food delivery brand identity designed around **Health, Trust, and Speed**. This documentation contains the exact style tokens, dimensions, and interaction maps required to transition the design from Figma into code.

---

## 🎨 1. Global Color Tokens

| Color Role | Hex Code | Opacity | UI Implementation |
| :--- | :--- | :--- | :--- |
| **Primary Green (Health & Trust)** | `#16423C` | `100%` | Splash Screen BG, Primary Titles, Prices |
| **Secondary Accent (Speed & Action)**| `#E88A24` | `100%` | Main Action Buttons, Add-to-Cart Triggers |
| **Soft White / Cream (Organic BG)** | `#F9F9F6` | `100%` | Main App Screen Backgrounds |
| **Charcoal Text (High Contrast)** | `#1A1C1B` | `100%` | Headings, Product Names, Body Copies |
| **Pure White (Surface Base)** | `#FFFFFF` | `100%` | Product Card Background Panels |

---

## ✍️ 2. Typography Scale (Inter / SF Pro)

*   **Brand Logo Title (Splash):** `36px` | **Bold** | **ALL CAPS** | `Letter-spacing: 15%` | `#FFFFFF`
*   **Splash Tagline:** `14px` | **Regular** | `#FFFFFF` | `Opacity: 70%`
*   **Page 2 Layout Headers:** `24px` | **Bold** | `#1A1C1B`
*   **Page 3 Large Details Title:** `40px` | **Bold** | `#1A1C1B`
*   **Page 3 Sub-prices:** `28px` | **Semi-Bold** | `#16423C`
*   **Product Card Titles:** `14px` | **Bold** | `#1A1C1B`
*   **Product Card Prices:** `14px` | **Medium** | `#16423C`

---

## 📐 3. UI Component Specs & Layout Grids

### 📱 Screen 1: Splash Screen
*   **Canvas Base:** Android Medium (`360px` × `640px`)
*   **Background:** `#16423C`
*   **Layout:** Central Group (`FRAIS` + Tagline) aligned perfectly to **Horizontal & Vertical Centers**.
*   **Automatic Routing:** `After delay` -> `2000ms` -> Navigate to **Product List**.

### 🗂️ Screen 2: Product List Page
*   **Layout Grid (Columns):** Count: `2` \| Type: `Stretch` \| Margin: `16px` \| Gutter: `16px`
*   **Page Margins:** Top edge header spacing: `24px` \| Vertical left margin line: `16px`
*   **Product Card Container (White):** 
    *   Width: `156px` \| Height: `210px` \| Corner Radius: `12px`
    *   **Effects (Drop Shadow):** X: `0`, Y: `4` \| Blur: `12` \| Color: `#000000` @ `6% Opacity`
*   **Card Image Vector:** Width: `156px` \| Height: `115px` \| Top-Left & Top-Right Radius: `12px` \| Bottom Radius: `0px`
*   **Card Text Insets:** Left margin spacing inside white container: `12px`
*   **Add Button Circle:** Width: `32px` × Height: `32px` \| BG: `#E88A24` \| Content: Center-aligned bold white `+` sign. Spaced `12px` from bottom/right edges.

### 🔍 Screen 3: Product Details Page
*   **Canvas Scale Up:** Tablet/Desktop Adaptive View (`700px` × `840px`)
*   **Hero Banner Image:** Width: `700px` (Edge-to-edge) \| Height: `350px` \| Flush with top edge.
*   **Back Navigation Circle:** Width: `40px` × Height: `40px` \| BG: `#000000` @ `30% Opacity` (Smoky glass). Spaced `32px` from top/left screen borders.
*   **Typography Margins:** All text items snapped uniformly to the **32px left layout margin** line.
*   **Trust Badge Capsule:** Width: `200px` \| Height: `36px` \| Corner Radius: `100` (Pill shape)
    *   *Styling:* BG Filled with `#16423C` @ `10% Opacity`. Inner Text: `✓ 100% Certified Organic` in `12px` solid `#16423C`.
*   **Primary Action Button:** Width: `636px` \| Height: `64px` \| Corner Radius: `16px`
    *   *Styling:* BG Filled with `#E88A24`. Inner text: `Deliver Instantly` in `20px` Bold White (`#FFFFFF`). Centered horizontally, spaced `40px` up from screen bottom.

---

## ⚡ 4. Advanced Prototyping Interactions (Anti-Flicker Architecture)

To avoid hardware acceleration issues and interface flickering when handling complex multi-state elements, navigate using these separate input-state blueprints:

[ Apple Product Card ] ──── (On Tap / Click) ───> Navigate to [ Product Details (Page 3) ]
### ↩️ Dual-Trigger Back Button Control Flow:
*   **Short Tap Event:** 
    *   Trigger: `Touch up` *(Triggered when cursor/finger lifts off the node)*
    *   Action: `Navigate to` -> **Product List (Page 2)**
*   **Long Press Event:** 
    *   Trigger: `Touch down` *(Triggered the instant pressure is applied to the node)*
    *   Constraint: `3000ms Delay` *(Requires user to maintain pressure for 3 seconds to confirm)*
    *   Action: `Navigate to` -> **Splash Screen (Page 1)**
