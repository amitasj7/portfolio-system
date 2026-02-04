# Future Improvements Implementation Plan

This plan tracks the implementation of features listed in `FUTURE_IMPROVEMENTS.MD`.

## 1. Resume Section (Social Links)
- [x] **Dynamic Admin Panel**: Add categories and primary toggle.
- [x] **Redesigned Social Card**: Split hierarchy (Primary vs Secondary).
- [x] **Header Update**: Replace icons with "Main Links" text and single icon.
- [x] **Popover Menu**: Categorized secondary links.
- [x] **Section Ordering**: Admin control for Category order.
- [x] **Link Ordering**: Admin control for Link order within sections.

## 2. Contact Section
- [ ] **"Reaching out as..." Field**:
    - [ ] Make mandatory.
    - [ ] Update dropdown styling (fix brightness, add glassmorphism).
    - [ ] Open on hover with animation.
- [ ] **Response Highlight**: Highlight response time with animation/icon.
- [ ] **Form Submission**: Show success message for 10s then revert.

## 3. Project Section
- [ ] **Filter Buttons**: Reorder (Featured first, then All). (Already present)
- [x] **Ordering System**:
    - [x] Add `order` field to projects in Admin. (Already present)
    - [x] Implement ordering logic (Public page sorts by order).
    - [x] Admin/Public sort by `order`.

## 4. Timeline Section
- [x] **Layout Redesign**: Alternating sides (Timeline Left/Content Right). (Verified)
- [x] **Spacing**: Fix spacing between company and description. (Verified)
- [x] **Styling**: Improve "Work" and "Education" tags/badges. (Verified)

## 5. Hero & Home Section
- [x] **Scroll Animations**: Fixed Exit Direction to South-East.
- [ ] **3D Button**: Add "Play" button with 5s timer.
- [ ] **Music Integration**: Add music button above 3D button.

## 6. Performance
- [ ] **Render Optimization**: Investigate slow render times.
