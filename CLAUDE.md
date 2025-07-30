# StudyQuest Development Rules & Design System

## Project Context
StudyQuest is an AI-powered learning platform for Danish university students. This is a **wireframe prototype** focused on navigation and layout structure, not full functionality.

## Core Mission
Transform boring academic materials into interactive learning experiences through AI-generated courses, quizzes, and progress tracking.

## Target Audience
- Primary: Danish university students across multiple disciplines
- Platform: Desktop web application (no mobile optimization in MVP)

---

## 🔄 Documentation Rules

### IMPORTANT: Project State Management
**When making any changes to the project, you MUST update `project_overview.md` to reflect:**
- New files created or removed
- Navigation flow changes
- Implementation status updates
- New features added or bugs fixed
- Demo data modifications
- Known issues discovered or resolved

**The `project_overview.md` file should always represent the current state of the project.**

---

## Design System

### Color Palette (Notion-Inspired Clean Aesthetic)
```css
/* Primary Backgrounds */
--bg-primary: #ffffff;        /* Pure white - main page background */
--bg-secondary: #f7f7f5;      /* Light warm gray - cards, sidebars */
--bg-elevated: #ffffff;       /* White - modals, dropdowns */

/* Text Colors */
--text-primary: #2f3437;      /* Dark charcoal - headlines, primary text */
--text-secondary: #787774;    /* Medium gray - descriptions, labels */
--text-muted: #a6a6a3;        /* Light gray - placeholders, disabled text */

/* Border & Divider Colors */
--border-light: #e9e9e7;      /* Light borders, dividers */
--border-medium: #d3d3d0;     /* Medium borders, form inputs */
--border-focus: #2f3437;      /* Focus states, active elements */

/* Accent Colors (Soft Pastels) */
--accent-blue: #d49313;       /* Primary actions, links (golden amber) */
--accent-green: #24a148;      /* Success states, completed items */
--accent-purple: #8a3ffc;     /* Creative/design elements */
--accent-orange: #ff832b;     /* Warnings, highlights */
--accent-red: #da1e28;        /* Errors, destructive actions */

/* Interactive States */
--hover-light: #f4f4f4;       /* Light hover backgrounds */
--hover-medium: #e8e8e8;      /* Medium hover backgrounds */
--shadow-subtle: 0 1px 3px rgba(0,0,0,0.1);     /* Card shadows */
--shadow-elevated: 0 4px 12px rgba(0,0,0,0.15); /* Modal shadows */
```

### Typography Rules
- **Font Family**: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif
- **Large Headings**: 28-32px, font-weight: 700, color: var(--text-primary)
- **Medium Headings**: 20-24px, font-weight: 600, color: var(--text-primary)
- **Body Text**: 14-16px, font-weight: 400, color: var(--text-secondary)
- **Small Text**: 12-14px, font-weight: 400, color: var(--text-muted)
- **Interactive Text**: 14-16px, font-weight: 500, color: var(--text-primary)
- **Line Height**: 1.5 for body text, 1.2 for headings

### Spacing System
- **Container Max-Width**: 1200px (standard), 1000px (narrow pages)
- **Card Padding**: 24px standard, 32px for large cards
- **Grid Gap**: 16px between cards (tighter, more modern)
- **Section Spacing**: 48px between major sections
- **Header Padding**: 16px vertical, 32px horizontal
- **Modal Padding**: 40px all sides
- **Border Radius**: 8px for cards, 6px for buttons, 12px for large elements

---

## Component Design Patterns

### Header Structure (Always Consistent)
```html
<header class="header">
    <div class="logo" onclick="goHome()">StudyQuest</div>
    <!-- Search bar for logged-in pages only -->
    <!-- Profile section OR auth buttons -->
</header>
```

### Card Design Rules
- **Background**: var(--bg-elevated) (pure white)
- **Border**: 1px solid var(--border-light)
- **Border Radius**: 8px consistent
- **Shadow**: var(--shadow-subtle) for elevation
- **Hover Effect**: box-shadow elevation and subtle scale (transform: translateY(-1px))
- **Cursor**: pointer for clickable cards
- **Padding**: 24px standard, 32px for content-heavy cards

### Modal Design Pattern
```html
<div class="modal-overlay" onclick="closeModal(event, 'modalId')">
    <div class="modal-content">
        <button class="modal-close" onclick="closeModal(null, 'modalId')">&times;</button>
        <h2 class="modal-title">Title</h2>
        <!-- Content here -->
    </div>
</div>
```

### Button Hierarchy (Notion-Inspired)
1. **Primary**: var(--accent-blue) background, white text, subtle shadow - main actions
2. **Secondary**: white background, var(--border-medium) border, var(--text-primary) text - secondary actions  
3. **Ghost**: transparent background, var(--text-secondary) text, hover background - tertiary actions
4. **Destructive**: var(--accent-red) background, white text - dangerous actions
- **Border Radius**: 6px for all buttons
- **Padding**: 8px 16px for standard, 12px 24px for large buttons

### Progress Indicator Rules
- **Dashboard Style**: Horizontal bars with percentage text and smooth animations
- **Course Page Style**: Circular borders using conic-gradient with modern styling
- **Colors**: var(--accent-green) for completed, var(--accent-blue) for in-progress, var(--border-light) for remaining
- **States**: 
  - Not started: Light border with var(--border-light)
  - In progress: Partial fill with var(--accent-blue), subtle pulse animation
  - Completed: Full var(--accent-green) with checkmark icon
- **Animations**: Smooth transitions (0.3s ease) for all state changes

---

## Development Rules

### CSS Architecture
- **Single CSS File**: Always use one global stylesheet
- **Class Naming**: Semantic names (.course-card, .lecture-title, .progress-bar)
- **Modifier Classes**: Use descriptive modifiers (.large, .wide, .narrow, .hero)
- **State Classes**: Clear state indication (.completed, .in-progress, .expanded)

### HTML Structure Rules
- **Semantic Elements**: Use proper HTML5 elements (header, main, section, etc.)
- **Accessibility**: Always include form labels, button text, alt attributes
- **Click Handlers**: Use onclick for prototype navigation (will be replaced later)

### JavaScript Patterns
- **Navigation**: Use `window.location.href` for page changes
- **Modal Management**: Handle overlay clicks, escape key, close button
- **Event Prevention**: Use `event.stopPropagation()` for nested clickables
- **Form Handling**: Prevent default submission, navigate instead

### Responsive Design Rules
- **Desktop First**: No mobile optimization in current scope
- **Grid Layouts**: Use `repeat(auto-fill, minmax(Xpx, 1fr))` for card grids
- **Flexible Containers**: Set max-width, center with margin auto
- **Breakpoint**: Consider 1200px as standard container width

---

## Content Guidelines

### Language Rules
- **Primary**: Danish for UI elements (buttons, labels, section titles)
- **Technical Terms**: English acceptable for some technical concepts
- **Placeholders**: Use realistic Danish university examples
- **Consistency**: Maintain consistent terminology throughout

### Danish Context Requirements
- **Universities**: Use real Danish institution names
- **Academic Terms**: Follow Danish higher education terminology  
- **Course Examples**: Realistic course names and descriptions
- **Semester System**: Use Danish "Forår/Efterår" structure

### Form Dropdown Standards
- **Always Include**: "Vælg [option]" as first disabled option
- **University List**: Include major Danish universities (KU, AU, SDU, AAU, DTU, CBS, etc.)
- **Study Fields**: Cover major academic disciplines
- **Final Option**: Always include "Andet" for unlisted options

---

## Wireframe Principles

### Functionality Scope
- **Focus**: Layout, navigation, user flow demonstration
- **NOT Included**: Real backend, data persistence, file processing
- **Interactions**: Basic navigation and modal management only
- **Placeholder Content**: Use demo data for realistic appearance

### User Experience Rules
- **Navigation**: Every link must lead somewhere logical
- **Feedback**: Use placeholder alerts for non-implemented features
- **Consistency**: Same interaction patterns across all pages
- **Clarity**: Clear visual hierarchy and information architecture

### Code Quality Standards
- **Clean Structure**: Logical HTML organization
- **Consistent Styling**: Reuse CSS classes, avoid inline styles
- **Readable Code**: Clear variable names, consistent formatting
- **Documentation**: Comment complex CSS or JavaScript logic

---

## Technical Constraints

### Browser Support
- **Target**: Modern browsers (Chrome, Firefox, Safari, Edge)
- **NOT Supported**: Internet Explorer
- **Features**: Use standard web APIs, avoid experimental features

### Performance Considerations
- **Images**: Use CSS for decorative elements where possible
- **File Size**: Keep CSS organized but don't optimize for size yet
- **Loading**: No lazy loading or advanced optimization needed

### Future-Proofing
- **Scalable Structure**: Design for easy feature addition
- **Clean Separation**: Keep styles, structure, and behavior separate
- **Standard Patterns**: Use conventional web development approaches

---

## Quality Assurance

### Testing Requirements
- **Navigation**: Every link and button must work
- **Modals**: Open/close functionality across all browsers
- **Responsive**: Layout works at different screen sizes
- **Console**: No JavaScript errors
- **Visual**: Consistent appearance across browsers

### Accessibility Baseline
- **Forms**: All inputs have labels
- **Buttons**: Descriptive text content
- **Navigation**: Logical tab order
- **Colors**: Sufficient contrast (handled by grayscale system)

---

## Prohibited Practices

### What NOT to Do
- ❌ Don't implement real backend functionality
- ❌ Don't use external libraries or frameworks
- ❌ Don't create multiple CSS files
- ❌ Don't ignore mobile completely (keep structure flexible)
- ❌ Don't use placeholder text like "Lorem ipsum"
- ❌ Don't hardcode specific user data (use realistic demo data)
- ❌ Don't break the navigation flow
- ❌ Don't forget to update project_overview.md when making changes