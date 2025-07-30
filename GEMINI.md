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

### Color Palette (60-30-10 Grayscale Rule)
```css
/* 60% - Light grays (dominant background colors) */
--bg-primary: #f8f9fa;        /* Main page background */
--bg-secondary: #e9ecef;      /* Cards, headers, modals */

/* 30% - Medium grays (secondary elements) */
--border-primary: #adb5bd;    /* Borders, dividers */
--text-secondary: #666;       /* Secondary text, descriptions */
--bg-tertiary: #dee2e6;       /* Progress bar backgrounds, inactive elements */

/* 10% - Dark gray (accent/focus elements) */
--text-primary: #343a40;      /* Headlines, important text */
--accent-primary: #343a40;    /* Primary buttons, progress fills, active states */
--accent-hover: #495057;      /* Hover states */
```

### Typography Rules
- **Font Family**: Arial, sans-serif (web-safe, clean)
- **Headings**: Always bold, always dark gray (#343a40)
- **Body Text**: Regular weight, medium gray (#666)
- **Interactive Text**: Dark gray (#343a40)
- **Size Hierarchy**: Use consistent font-size classes (.large, .hero, etc.)

### Spacing System
- **Container Max-Width**: 1200px (standard), 1000px (narrow pages)
- **Card Padding**: 20px standard
- **Grid Gap**: 20px between cards
- **Section Spacing**: 40px between major sections
- **Header Padding**: 15px vertical, 30px horizontal
- **Modal Padding**: 40px all sides

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
- **Border**: Always 2px solid #adb5bd
- **Border Radius**: 8px consistent
- **Background**: #e9ecef for primary cards
- **Hover Effect**: border-color change to #343a40
- **Cursor**: pointer for clickable cards

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

### Button Hierarchy (Strict Order)
1. **Primary**: Dark background (#343a40), white text - main actions
2. **Secondary**: Transparent background, gray border (#adb5bd) - secondary actions  
3. **Tertiary**: Medium gray background (#adb5bd) - less important actions

### Progress Indicator Rules
- **Dashboard Style**: Horizontal bars with percentage text
- **Course Page Style**: Circular borders using conic-gradient
- **Colors**: Always #343a40 for progress, #dee2e6 for remaining
- **States**: Not started (thin), In progress (partial thick), Completed (full thick)

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