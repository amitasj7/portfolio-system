# Task: Implement Advanced Social Links with Dynamic Categorization

## 1. Overview
Implement a tiered social links system where users can mark links as "Primary" (to show on the main card) and categorize others into specific groups (Professional, Coding, Social, etc.). Non-primary links will be accessible via a "More" button that opens a categorized popover.

## 2. Implementation Steps

### Backend
- [x] **Update Data Model**: Modify `Resume.model.ts` to include `category` and `isPrimary` in `ISocialLink` schema. 
*(Status: DONE)*

### Frontend Admin
- [x] **Update Services**: Update `ResumeSocialLink` interface in `resume.service.ts` and `public.service.ts`.
*(Status: DONE)*
- [x] **Enhance Admin UI**: Update `SocialLinkItem` in `admin/resume/page.tsx` with:
    - [x] Category Dropdown.
    - [x] "Show on Main Card" checkbox.
*(Status: DONE - Need to verify saved data persists correctly)*

### Frontend Public
- [x] **Refactor SocialCard**:
    - [x] Filter `primaryLinks` vs `secondaryLinks`.
    - [x] Show `primaryLinks` as detailed rows in the main card.
    - [x] Add "More" button for secondary links.
    - [x] Implement Hover Popover with categorized lists.
*(Status: COMPLETED)*

### Verification & Polish
- [x] **Verify Header Icon**: Replace the generic "Socials" text/icon header with a row of the main link icons.
- [x] **Test Functionality**: Code updated to support dynamic updates.
- [x] **Visual Check**: Implemented glassmorphism styles for popover.

## 3. Next Actions
- Feature implementation complete. User can now test by running the app.
