# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)
- **Họ và tên:** Nguyễn Văn Thành Khôi
- **MSSV: 125001564**
- **Tên đề tài Website: Giới thiệu món ăn Việt**
- **Công cụ AI đã sử dụng: GitHub Copilot, ChatGPT**
## 1. Yêu cầu ban đầu (System/Initial Prompt)
> 
## Project: Vietnamese Food Discovery Website
You are a senior front-end developer and UI/UX designer. Build a complete, responsive Vietnamese food discovery website that helps visitors explore Vietnamese cuisine and discover nearby restaurants.
The website should look modern, elegant, welcoming, and visually appealing without being unnecessarily complicated. Prioritize a clean user experience, useful functionality, readable code, and maintainability.
**Important: Implement the actual website in the current workspace. Do not just provide explanations, mockups, or isolated code snippets.**
## 1. Technology Stack
Use the following technologies:
- HTML5 with semantic elements.
- CSS3 with CSS custom properties, Flexbox, and CSS Grid.
- Vanilla JavaScript (ES6+).
- Animate.css for selected entrance animations.
- AOS (Animate On Scroll) for scroll-triggered animations.
Do not use React, Vue, Angular, TypeScript, or a complicated build system. The project should run without installing Node.js packages or configuring a bundler.
Use CDN links for Animate.css and AOS where appropriate.
## 2. Visual Design and Branding
Create a modern, minimal food-discovery website with a warm Vietnamese culinary identity.
### Design direction
- Clean layout with generous whitespace.
- Large, appealing food photography.
- Rounded cards, subtle shadows, and consistent spacing.
- Elegant typography and clear visual hierarchy.
- Smooth hover transitions and subtle animations.
- A responsive navigation bar that works on desktop and mobile.
- Avoid excessive gradients, decorative elements, animations, and unnecessary UI components.
### Suggested color palette
Define all reusable design values in `:root`:
- Primary color: deep forest green, such as `#245C45`.
- Secondary color: warm terracotta, such as `#D96C4F`.
- Background color: warm cream, such as `#FFF9F1`.
- Surface color: white, such as `#FFFFFF`.
- Main text: dark charcoal, such as `#292D2A`.
- Muted text: soft gray.
- Accent color: warm golden yellow.
Also define CSS variables for typography, spacing, border radii, shadows, transitions, and container widths.
Use a consistent design system throughout the website.
## 3. Website Structure
Create the following sections in `index.html`.
### A. Header and navigation
Use semantic `<header>` and `<nav>` elements.
Include:
- A simple text or illustrated-style brand logo.
- Brand name: "Vị Việt".
- Navigation links: Trang chủ, Khám phá món ngon, Quán ăn gần bạn, Giới thiệu.
- A prominent CTA button labeled "Khám phá ngay".
- A mobile-friendly navigation menu.
The header should be clean and remain easy to navigate on smaller screens.
### B. Hero section
Create an attractive hero section that immediately explains the website's purpose.
Suggested Vietnamese heading:
"Khám phá hương vị Việt, tìm quán ngon quanh bạn."
Supporting text:
"Từ món ăn đường phố dân dã đến những đặc sản vùng miền, tìm cảm hứng cho bữa ăn tiếp theo của bạn."
Include:
- A primary button: "Khám phá món ngon".
- A secondary button: "Tìm quán gần tôi".
- A large, high-quality Vietnamese food image or an attractive food-image composition.
- Subtle entrance animations using Animate.css.
The buttons must navigate to their corresponding sections or trigger their intended actions.
### C. Vietnamese food discovery section
Use a semantic `<section>` with the ID `food-discovery`.
Section heading:
"Ngon từ Bắc chí Nam"
Supporting text:
"Khám phá những món ăn làm nên bản sắc ẩm thực Việt Nam."
Create a responsive grid of food cards featuring Vietnamese dishes, including examples such as:
- Phở bò.
- Bánh mì.
- Bún chả.
- Bún bò Huế.
- Cơm tấm.
- Mì Quảng.
- Bánh xèo.
- Gỏi cuốn.
- Chè ba màu.

Each card should contain:
- A food photograph.
- The Vietnamese dish name.
- A short, appealing description.
- Its region of origin where appropriate.
- Relevant category tags, such as "Miền Bắc", "Miền Trung", "Miền Nam", or "Món chay".
- An optional indicative price range in Vietnamese đồng.
- A button to discover more about the dish.

Implement functional category filters and a search field so users can find dishes by name, region, or category.
Include a "Gợi ý món ngẫu nhiên" button that recommends a dish from the available dataset.
Use a JavaScript data array to manage food information instead of duplicating HTML for every card.
### D. Nearby restaurant discovery section
Use a semantic `<section>` with the ID `nearby-restaurants`.
Section heading:
"Quán ngon quanh bạn"
Supporting text:
"Tìm những địa điểm ăn uống gần bạn và khám phá hương vị địa phương."
This is one of the website's most important features.
Implement the following functionality:
1. Add a button labeled "Tìm quán gần tôi".
2. Request the visitor's location using the browser Geolocation API only after the visitor clicks the button.
3. Display a clear explanation of why location permission is requested.
4. Use the OpenStreetMap Overpass API to retrieve nearby restaurant information around the user's coordinates, without requiring a paid API key.
5. Search within a reasonable default radius, such as 5 kilometers.
6. Prioritize restaurants with Vietnamese cuisine information when available.
7. Sort restaurant results by calculated distance from the user's location.
8. Display restaurant information in responsive cards.
9. Provide loading, empty-result, permission-denied, unsupported-browser, and API-error states.
10. Provide a manual fallback allowing users to select a demonstration city, such as Hà Nội, TP. Hồ Chí Minh, or Đà Nẵng, when location access is unavailable.
Each restaurant card should show the information actually available from the data source:
- Restaurant name.
- Address, when available.
- Cuisine information, when available.
- Distance from the selected location.
- Website or phone number, when available.
- A link to view the location on OpenStreetMap.
Do not fabricate restaurant names, ratings, opening hours, reviews, addresses, or prices.
Calculate distances accurately using the Haversine formula when coordinates are available.
If a public API request fails or returns no useful results, display a friendly error or empty state. An optional local demonstration dataset may be provided, but clearly label its entries as sample data rather than real, verified recommendations.
Explain that geolocation requires permission and normally works in HTTPS or localhost contexts. Do not store the visitor's coordinates persistently.
Handle public API rate limits, network failures, and incomplete OpenStreetMap data gracefully. Keep the restaurant data-fetching logic separate from the UI rendering logic so a different data provider can be integrated later.
### E. Food recommendation experience
Add a lightweight recommendation component that helps visitors decide what to eat.
Provide selectable preferences, such as:
- Miền Bắc, miền Trung, or miền Nam.
- Món chay or món mặn.
- Món nước or món khô.
- Spicy food or non-spicy food.
Use these preferences to filter the local food dataset and display suitable recommendations.
Keep the interaction simple. Avoid introducing user accounts, complicated recommendation algorithms, or unnecessary backend infrastructure.
### F. About section
Use a semantic `<section>` with the ID `about`.
Explain that "Vị Việt" helps people discover Vietnamese dishes, learn about regional culinary culture, and find restaurants around their location.
Use concise Vietnamese copy and a clean layout.
### G. Footer
Use a semantic `<footer>`.
Include:
- Brand name and short description.
- Navigation links.
- Contact information placeholders that are clearly identified as placeholders.
- Copyright notice with the current year generated by JavaScript.
Keep the footer simple and consistent with the overall design.
## 4. Code Organization
Create the following files:
- `index.html`: Semantic page structure and CDN imports.
- `style.css`: All styles, CSS variables, responsive layouts, and animations.
- `script.js`: Food data, search and filter logic, food recommendations, geolocation, restaurant API requests, distance calculations, error handling, and UI interactions.
- `README.md`: Project overview, features, how to run the website, external API dependencies, and known limitations.
Use clear function names, modular JavaScript functions, and comments for non-obvious logic.
Avoid unnecessary code duplication, excessive dependencies, inline styling, and overly complicated abstractions.
Do not expose API keys or other secrets. No backend should be required for the initial version.
## 5. Final Quality Requirements
Before considering the project complete:
- Ensure all navigation links and CTA buttons work.
- Verify that the food search and category filters actually filter results.
- Verify that the random food recommendation button works.
- Check geolocation success and failure handling.
- Check API loading, empty-result, and error states.
- Verify that restaurant distances are calculated from available coordinates.
- Check the layout at mobile, tablet, and desktop widths.
- Confirm that Animate.css and AOS load and initialize properly.
- Check the browser console for avoidable JavaScript errors.
- Ensure all visitor-facing text is natural Vietnamese with proper accents.
- Ensure unavailable information is not fabricated.
- Ensure the README explains how to open the website locally and what is required for real restaurant discovery.
If the workspace already contains project files, inspect them first and preserve useful existing code. Implement the solution in the actual files, then review the completed implementation and fix obvious issues.
**Priority order:** functional correctness, visual quality, responsive design, accessibility, then optional polish.
The final result should feel like a polished Vietnamese food-discovery product: warm, modern, intuitive, lightweight, and genuinely useful.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)
### Lần 1: Dựng khung Semantic HTML & CSS Variable
- **Prompt đã dùng:**
> 
## Semantic HTML and Accessibility
Use appropriate HTML5 elements, including:
- `<header>`
- `<nav>`
- `<main>`
- `<section>`
- `<article>`
- `<footer>`
Use headings in a logical hierarchy, descriptive image alt text, accessible form labels, meaningful link text, and native buttons for actions.
Provide visible `:focus-visible` styles and keyboard accessibility.
Use ARIA attributes only where appropriate. Announce loading and search-result updates using an accessible status region.
Respect `prefers-reduced-motion` so visitors can reduce animations.
## CSS and Responsive Layout
Use CSS Grid and Flexbox to create responsive layouts.
The website must work well on:
- Desktop computers.
- Tablets.
- Mobile phones.
Use mobile-first CSS where practical.
Include:
- Consistent spacing and typography.
- Reusable card styles.
- Responsive navigation.
- Responsive images.
- Clear hover and focus states.
- Smooth but restrained transitions.
- Useful breakpoints for different screen sizes.
Avoid horizontal overflow, overlapping elements, and fixed widths that break on mobile.
- **Kết quả AI tạo ra:** GitHub Copilot đã tạo các tệp ban đầu cho website, bao gồm tệp HTML và tệp TypeScript. Phần khung ban đầu được thiết lập để phát triển website giới thiệu món ăn Việt Nam, với định hướng khám phá món ăn và tìm kiếm nhà hàng gần vị trí người dùng.
- **Nhận xét & Tinh chỉnh của SV:** Tuy nhiên, kết quả ban đầu chưa hoàn thiện về cấu trúc dự án. Các tệp giao diện như style.css và thư mục assets/ chứa hình ảnh, logo chưa được tạo đầy đủ.

### Lần 2: Tích hợp thư viện Animate.css & AOS
- **Prompt đã dùng:**
>
## Animations and Interactions
Integrate Animate.css for selected hero elements, headings, and CTA buttons.
Integrate AOS for selected food cards, restaurant cards, and content sections.
Initialize AOS correctly after the required library has loaded.
Keep animations subtle and avoid animating every element.
Implement meaningful `:hover`, `:focus-visible`, `:active`, and `:disabled` states where appropriate.
All interactive controls must work. Do not create buttons that are merely decorative.

- **Thách thức gặp phải:** Ban đầu dự án có index.ts, nhưng prompt trước chưa khóa đủ chặt việc giữ nguyên TypeScript, nên AI đã tạo script.js thay thế. Nên phải sửa lại theo hướng giữ index.ts, giữ style.css và assets/ và xóa script.js
- **Cách sửa prompt (Debug prompt):**
>
Fix Project Structure: Restore TypeScript Entry Point
The previous changes incorrectly created script.js and removed or replaced the original index.ts.
This is a mistake. Fix the project structure while preserving the existing application and its functionality.
## Strict requirements ##
Restore index.ts as the application's TypeScript entry point.
Do NOT use script.js. Do not create another JavaScript file to replace index.ts.
Preserve style.css as the separate stylesheet.
Preserve the assets/ directory and its existing assets.
Inspect the current project files and configuration before making changes.
Recover the original index.ts implementation from available version history or Git history if possible. If recovery is not possible, reconstruct its functionality using the current project code.
Migrate any useful logic from script.js into index.ts, then remove script.js only after confirming its required functionality has been preserved.
Update HTML imports, TypeScript imports, and build configuration as necessary so the application uses the correct entry point.
Do not rename, delete, or replace other project files unnecessarily.
Do not introduce a new framework, bundler, or package configuration unless the existing project genuinely requires it.
