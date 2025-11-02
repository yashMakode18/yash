# CampusConnect Design Guidelines

## Design Principles
**Approach:** Modern Design System with Campus-Optimized Patterns
- **Clarity First:** Immediate comprehension of issue status and actions
- **Student-Centric:** Approachable, modern interface (not bureaucratic)
- **Data Transparency:** Intuitive progress tracking and analytics
- **Mobile-First:** Primary access via phones on campus

---

## Typography

### Fonts
- **Primary:** Inter (UI, data, body text)
- **Display:** Poppins (headers, campus-friendly feel)

### Scale & Application
```
Hero/Page Headers: text-4xl md:text-5xl font-bold (Poppins)
Section Headers: text-2xl md:text-3xl font-semibold (Poppins)
Card Headers: text-xl font-semibold (Inter)
Body: text-base font-normal (Inter)
Labels/Metadata: text-sm font-medium (Inter)
Captions: text-xs font-normal (Inter)

Issue titles: text-lg font-semibold
Categories: text-sm font-bold uppercase tracking-wide
Status: text-sm font-semibold
Comments: text-base leading-relaxed
```

---

## Layout

### Spacing (Tailwind units: 2, 4, 6, 8, 12, 16, 20, 24)
- Micro (within components): p-2, gap-2
- Component padding: p-4, p-6
- Section spacing: py-8, py-12, py-16
- Card spacing: p-6, gap-4
- Large gaps: gap-8, mb-12, py-20

### Containers
- Full-width: w-full max-w-7xl mx-auto px-6
- Content: max-w-6xl mx-auto
- Forms/Detail: max-w-3xl mx-auto
- Narrow: max-w-2xl

### Grid
- Desktop: 3-4 columns (issue cards), 2 columns (admin panels)
- Tablet: 2 columns (cards), 1 column (forms)
- Mobile: Single column

### Viewport Heights
- Hero: 50vh-60vh (show content preview)
- Dashboards: Natural height
- Issue feed: Infinite scroll, natural card heights

---

## Components

### Navigation
**Top Nav:** Fixed, h-16 (mobile) / h-20 (desktop), backdrop blur, logo left, links center, profile/notifications right, subtle shadow
**Mobile Bottom Nav:** Fixed bottom, h-16, 4-5 icons + labels (Heroicons outline)

### Issue Reporting Form
- Multi-step with progress bar (h-1 animated fill)
- Step 1: Photo dropzone (min-h-64, dashed border)
- Step 2: Description (textarea h-32)
- Step 3: Location (searchable dropdown)
- Container: max-w-2xl
- Buttons: Full width mobile, px-8 py-3 desktop
- Photo previews: grid-cols-2 md:grid-cols-3, aspect-square

### Issue Cards (Feed)
```
Layout: Horizontal (desktop), vertical (mobile)
Photo: w-full md:w-48 aspect-video object-cover
Padding: p-4 md:p-6
Border: rounded-lg
Shadow: hover:shadow-lg transition
Status badge: absolute top-4 right-4
Upvote button: fixed bottom-right
```

### Issue Detail
- Hero image: w-full max-h-96 object-cover
- Content: max-w-4xl container
- Desktop: 2/3 content + 1/3 sticky sidebar (top-24)
- Comments: Full width below content

### Status Badge
`rounded-full px-4 py-1.5 text-sm font-semibold` + icon

### Upvote Button
`w-12 h-12 rounded-lg` with text-lg font-bold counter, arrow icon, animated on click

### Admin Dashboard
**Sidebar:** Fixed w-64 (desktop), collapsible (mobile), logo h-16 px-6, nav items px-6 py-3, active state with border-l-4
**Stats Cards:** grid-cols-1 md:grid-cols-2 lg:grid-cols-4, p-6 rounded-xl, number text-3xl font-bold, icon h-10 w-10
**Issue Table:** Sortable headers, row h-16, hover states, ellipsis menu, filters flex gap-4, pagination flex justify-between
**Category Pills:** Horizontal scroll (mobile), grid-cols-5 (desktop), px-4 py-2 rounded-full, active filled, count badge

### Analytics
- Charts: grid-cols-1 lg:grid-cols-2 gap-8, p-6 rounded-xl
- Title: text-lg font-semibold mb-6
- Chart area: min-h-64 to min-h-80
- Legend: flex gap-4 text-sm

### Comments
```
Thread: p-4 border-l-2 ml-12 (threaded)
Avatar: h-10 w-10 rounded-full
Metadata: flex gap-2 text-xs
Text: mt-2 text-base leading-relaxed
Input: min-h-24 rounded-lg p-4, character counter, submit px-6 py-2
```

### Notifications
- Badge: h-2 w-2 rounded-full, absolute -top-1 -right-1
- Dropdown: w-96 max-h-96 overflow-y-auto, items p-4 border-b, icon h-8 w-8, timestamp text-xs

### Profile Card
`h-24 w-24 rounded-full` avatar, name text-2xl font-bold, role badge rounded-full px-3 py-1 text-sm, stats grid-cols-3 gap-4

---

## Icons (Heroicons)

### Categories
Electrical: bolt | Hostel: home | Classroom: academic-cap | Lab: beaker | Cleanliness: sparkles

### Status
Pending: clock | In Progress: arrow-path | Resolved: check-circle

### Actions
Upvote: arrow-up | Comment: chat-bubble-left | Share: share | Filter: funnel

### Navigation
Dashboard: squares-2x2 | Issues: exclamation-triangle | Analytics: chart-bar | Profile: user-circle

### Sizing
Small: h-4 w-4 | Standard: h-5 w-5 / h-6 w-6 | Large: h-8 w-8 | Hero: h-12 w-12 to h-16 w-16

---

## Images

**Hero:** Campus aerial/iconic building, golden hour, students, 50vh-60vh, subtle overlay
**Issue Photos:** aspect-video (thumbnails), max-h-96 (detail), grid-cols-2 md:grid-cols-3 (gallery)
**Empty States:** Friendly illustrations (not photos)
**Avatars:** Circular, initial-based defaults

---

## Animation (Minimal Only)

**Allowed:** Button hover (transition-colors duration-200), card hover shadow (transition-shadow), status changes (transition-all duration-300), upvote count-up, notification pulse
**Forbidden:** Page transitions, scroll animations, parallax, background animations

---

## Responsive Breakpoints

**Mobile (base):** Single column, stacked, bottom nav
**md (768px+):** 2 columns cards, sidebar nav
**lg (1024px+):** 3 columns grid, full admin layout
**xl (1280px+):** Max widths, optimized spacing

**Key Patterns:** Hamburger→horizontal nav, vertical→horizontal cards, tabs→persistent sidebar, full width→centered forms, single→multi-column stats

---

## Accessibility (WCAG AA)

- **Forms:** Labels above (text-sm font-medium), inputs h-12 min, errors below with icon, asterisk + aria-required
- **Focus:** Visible ring-2 on all interactive elements
- **Touch:** 44x44px minimum targets
- **Keyboard:** Full navigation support
- **Screen readers:** Proper ARIA labels
- **Contrast:** Meet WCAG AA minimum

---

**Implementation:** Use Tailwind CSS classes as specified. All measurements in Tailwind units for consistency.