# Design Guidelines: Dagoretti School Library Management System

## Design Approach

**Selected Approach:** Reference-Based + Design System Hybrid
- Primary inspiration: **Notion** (clean data management) + **Goodreads** (book discovery) + **Linear** (modern dashboard aesthetics)
- Supporting system: **Material Design** principles for data-heavy interfaces
- Justification: Educational platform requiring both visual appeal for student engagement and functional clarity for administrative tasks

## Color Foundation

**School Brand Colors (User-Specified):**
- Primary: Deep Green (#1B5E20, #2E7D32) - navigation, primary actions
- Secondary: Gold/Amber (#F9A825, #FFA000) - accents, highlights, status badges
- Neutral: White (#FFFFFF), Light Gray (#F5F5F5), Dark Gray (#424242)
- Semantic: Success Green, Warning Amber, Error Red for status indicators

## Typography System

**Font Families:**
- Primary: 'Inter' (Google Fonts) - UI elements, body text, data tables
- Display: 'Poppins' (Google Fonts) - headings, dashboard titles, hero text

**Hierarchy:**
- H1 (Dashboard Titles): Poppins 32px/40px, Semi-Bold
- H2 (Section Headers): Poppins 24px/32px, Semi-Bold
- H3 (Card Headers): Inter 18px/24px, Medium
- Body: Inter 16px/24px, Regular
- Small/Meta: Inter 14px/20px, Regular
- Captions: Inter 12px/16px, Regular

## Layout System

**Spacing Units:** Tailwind utilities of **4, 6, 8, 12, 16, 24** (e.g., p-4, gap-6, mb-8, py-12, px-16, mt-24)

**Grid Structure:**
- Admin sidebar: Fixed 256px width (w-64)
- Main content: Fluid with max-w-7xl container
- Card grids: 3-column on desktop (grid-cols-3), 2-column tablet (md:grid-cols-2), 1-column mobile
- Book catalog: 4-column grid on large screens (lg:grid-cols-4)

**Containers:**
- Dashboard sections: max-w-7xl mx-auto px-6
- Forms: max-w-2xl for optimal readability
- Modals: max-w-lg to max-w-4xl depending on content

## Component Library

### Navigation
**Admin Sidebar:**
- Fixed left position, full height
- School logo at top (h-16 with padding)
- Nav items with icons (from Heroicons) + labels
- Active state: subtle accent with gold left border (border-l-4)
- Hover: gentle background lift

**Student Top Nav:**
- Horizontal bar with logo left, search center, profile right
- Sticky positioning (sticky top-0)
- Quick action icons with tooltips

### Cards & Content Blocks

**Book Cards (Primary Component):**
- Aspect ratio 2:3 for book cover images (aspect-[2/3])
- Cover image with overlay on hover
- Title, author below image
- Status badge (rounded-full, px-3, py-1) - Available (green), Borrowed (amber), Overdue (red)
- Rounded corners (rounded-xl)
- Shadow on hover (hover:shadow-xl transition)

**Dashboard Stat Cards:**
- 4-column grid (grid-cols-4 gap-6)
- Large number display (text-4xl font-bold)
- Icon in accent color
- Subtle gradient backgrounds
- Padding: p-6

**Student Profile Cards:**
- Avatar placeholder or uploaded photo (w-16 h-16 rounded-full)
- Name, ID, class info
- Quick stats (books borrowed, active loans)

### Forms & Inputs

**Form Layout:**
- Vertical spacing between fields (space-y-6)
- Labels above inputs (text-sm font-medium mb-2)
- Input fields: rounded-lg, border-2, px-4, py-3
- Focus states with gold ring (focus:ring-2 focus:ring-amber-500)
- Helper text below (text-sm text-gray-600)

**Buttons:**
- Primary: Deep green background, white text, px-6 py-3, rounded-lg
- Secondary: White background, green border, green text
- Danger: Red for delete actions
- Icon buttons: Square (w-10 h-10) with centered icon

### Data Tables

**Structure:**
- Alternating row backgrounds (even:bg-gray-50)
- Header row: font-semibold, border-b-2
- Cell padding: px-6 py-4
- Action column on right with icon buttons
- Sticky header on scroll

### Modals & Overlays

**Modal Dialogs:**
- Centered overlay with backdrop blur
- White card (max-w-2xl) with rounded-xl
- Header with title + close button
- Content section with appropriate padding (p-6)
- Footer with action buttons (justify-end gap-4)

## Image Strategy

### Hero Images (YES - Large hero images included)

**Login/Splash Screen:**
- Full-width background: School building exterior or library interior
- Overlay gradient (green to transparent) for text legibility
- Centered login card with frosted glass effect (backdrop-blur-lg)

**Dashboard Headers:**
- Narrow banner images (h-48) showing library scenes
- Books on shelves, students reading, study spaces
- Subtle parallax scroll effect

### Content Images

**Book Covers:**
- Always display with fallback placeholder for missing covers
- Use actual book cover images via URL or upload
- Placeholder: Gradient with book icon + title text

**Student/Profile Photos:**
- Circular avatars throughout (rounded-full)
- Default: Initials on colored background (hash-based color from name)
- Upload capability for personalization

**Decorative Elements:**
- Abstract book/education themed illustrations for empty states
- Icon illustrations for feature explanations
- Subtle background patterns (faint book spines, academic motifs)

**Where Images Appear:**
- Every book card (catalog, search results, details)
- Student profile pages (avatar)
- Dashboard welcome banners
- Login/splash screens (hero)
- Empty states ("No books found" - illustration)
- Help/tutorial sections (explanatory graphics)
- Reports section (chart visualizations with background accents)

### Image Specifications
- Book covers: 400x600px minimum (2:3 ratio)
- Hero images: 1920x600px (full-width banners)
- Avatars: 200x200px minimum (displayed at various sizes)
- Icons: Use Heroicons library (24x24 or 20x20)
- Decorative: SVG illustrations preferred for scalability

## Special UI Patterns

**Search Interface:**
- Prominent search bar (w-full max-w-2xl)
- Live search with dropdown results
- Filter chips below search (rounded-full badges)
- Grid/List view toggle

**Borrowing Flow:**
- Step indicator at top (1. Select Book → 2. Confirm → 3. Success)
- Large book preview with details
- Due date picker (calendar component)
- Confirmation screen with check icon animation

**Notifications:**
- Toast messages (top-right, slide-in animation)
- Badge counts on navigation items (red dot with number)
- Alert banners for overdue books (amber background)

## Responsive Behavior

- Desktop (1024px+): Full sidebar, multi-column grids
- Tablet (768px-1023px): Collapsed sidebar (icons only), 2-column grids
- Mobile (<768px): Bottom tab bar navigation, single column, stacked cards

## Animation Guidelines

**Minimal, Purposeful Animations:**
- Page transitions: Subtle fade-in (300ms)
- Card hover: Gentle lift (transform translateY(-4px))
- Button interactions: Scale on press (scale-95)
- Modal entry: Fade + scale from center
- Loading states: Skeleton screens (shimmer effect)
- **NO** excessive scroll animations or distracting effects

## Accessibility

- Consistent tab order throughout
- ARIA labels on all interactive elements
- Sufficient contrast ratios (WCAG AA minimum)
- Focus indicators visible on all inputs/buttons
- Screen reader friendly table markup
- Keyboard navigation support for all actions

This design system creates a professional, academic yet modern aesthetic that balances visual appeal with functional clarity - perfect for both students exploring the catalog and librarians managing operations efficiently.