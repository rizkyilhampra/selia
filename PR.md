# Fix Docs Layout Spacing and Responsiveness

## Summary

Improves the documentation layout by adding proper horizontal spacing between the sidebar, main content, and table of contents (TOC). The changes introduce responsive gap utilities and padding adjustments to ensure comfortable reading across all screen sizes.

**Before:** The sidebar, content, and TOC were directly adjacent with no horizontal spacing, relying only on a visual border separator at the `xl` breakpoint.

**After:** Proper breathing room with responsive gaps (1.5rem on mobile, 2rem on desktop) and appropriate padding for better visual hierarchy and readability.

## Changes

### Modified Files
- `app/routes/docs.tsx`

### Key Updates

1. **Root Container Gap** (line 63)
   - Added `gap-6 lg:gap-8` to the main flex container
   - Creates 1.5rem gap on mobile/tablet, 2rem gap on desktop
   - Applies spacing between sidebar and main content

2. **Main Content Padding** (line 97)
   - Updated gap from `gap-6` to `gap-6 lg:gap-8` for content-TOC spacing
   - Added `px-4 lg:px-0` for responsive horizontal padding
   - Ensures 1rem padding on mobile, container-managed padding on desktop

## Responsive Behavior

| Breakpoint | Sidebar-Content Gap | Content-TOC Gap | Main Padding |
|-----------|---------------------|-----------------|--------------|
| Mobile (< 1024px) | 1.5rem | 1.5rem | 1rem horizontal |
| Desktop (≥ 1024px) | 2rem | 2rem | Container-managed |

## Design Rationale

- **Improved Visual Hierarchy:** Clear separation between navigation (sidebar), content, and supplementary info (TOC)
- **Enhanced Readability:** Content no longer feels cramped against the sidebar
- **Responsive First:** Scales appropriately from mobile to extra-large displays
- **Consistent Spacing:** Uses Tailwind's standard spacing scale (no arbitrary values)
- **Dark Mode Compatible:** No color changes, works in both light and dark modes

## Testing Checklist

- [x] Tested on mobile viewport (< 1024px)
- [x] Tested on desktop viewport (≥ 1024px)
- [x] Verified smooth transitions between breakpoints (768px, 1024px, 1280px)
- [x] Checked sidebar toggle functionality on mobile
- [x] Verified TOC positioning and spacing
- [x] Confirmed no layout shifts or visual glitches
- [x] Prettier formatting applied

## Screenshots

_Add screenshots showing before/after comparison at different breakpoints_

---

This PR aligns with Selia's philosophy of **Opinionated Defaults** by providing polished spacing out of the box, ensuring the documentation feels "orderly and neat" as the name implies.
