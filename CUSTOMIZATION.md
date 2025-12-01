# Customization Guide

This guide explains how to customize the Community Resource Widget for your own needs.

## Quick Start

### 1. Add New Resources

Edit the `resourceData` object in `index.html` to add new organizations:

```javascript
{
  header: "Housing",
  items: [
    {
      title: "Organization Name",
      description: "What they provide and who they serve",
      link: "https://official-website.org",
      linkText: "official-website.org"
    },
    {
      title: "Another Organization",
      description: "Brief description of services",
      link: "https://another-site.org",
      linkText: "another-site.org"
    }
  ]
}
```

### 2. Add a New City

To add Portland, Seattle, Spokane, or any other city:

#### Step 1: Add Data to `resourceData`
```javascript
const resourceData = {
  'newcity': {
    'Housing': {
      // ... category data here
    },
    'Food': {
      // ... category data here
    }
  }
}
```

#### Step 2: Add Tab Button in HTML
Find the tabs section and add:
```html
<button
  class="city-tab"
  data-city="newcity"
  aria-selected="false"
>
  New City
</button>
```

#### Step 3: Add View Pane in HTML
Find the content sections and add:
```html
<div
  class="city-content"
  id="newcity-view"
  role="region"
  aria-labelledby="newcity-tab"
  hidden
>
  <!-- Content will be populated by JavaScript -->
</div>
```

### 3. Customize Colors

Edit the CSS variables at the top of the `<style>` section:

```css
:root {
  --rw-primary-color: #6366f1;      /* Main color */
  --rw-secondary-color: #60a5fa;    /* Accent color */
  --rw-background: #ffffff;         /* Background */
  --rw-surface: #f9fafb;            /* Card background */
  --rw-text-primary: #1f2937;       /* Main text */
  --rw-text-secondary: #6b7280;     /* Secondary text */
  --rw-border: #e5e7eb;             /* Border color */
  --rw-success: #10b981;            /* Success color */
  --rw-danger: #ef4444;             /* Error/danger color */
}
```

Example: Change to a warm color scheme:
```css
:root {
  --rw-primary-color: #d97706;      /* Amber */
  --rw-secondary-color: #f59e0b;    /* Light amber */
  --rw-success: #059669;            /* Teal */
}
```

### 4. Customize Typography

Adjust fonts in the CSS:

```css
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  /* Change to your preferred font */
}

h1, h2, h3 {
  font-family: 'Arial', sans-serif;
  /* Separate heading font */
}
```

## Advanced Customization

### Add New Categories

Modify the `categoriesOrder` array:

```javascript
const categoriesOrder = [
  'Housing',
  'Food',
  'LGBTQ+',
  'Domestic Violence',
  'Child Abuse',
  'Sexual Assault',
  'Mental Health',  // New category
  'Legal Aid'       // New category
];
```

Then add data to your cities in `resourceData`.

### Change Layout Style

The widget uses a glassmorphic design. To use a different style, modify the CSS classes:

#### Option 1: Solid Cards
```css
.category-header {
  background: var(--rw-surface);
  /* Remove or modify backdrop-filter */
}
```

#### Option 2: Dark Mode
```css
:root {
  --rw-background: #1f2937;
  --rw-surface: #374151;
  --rw-text-primary: #f9fafb;
  --rw-text-secondary: #d1d5db;
  --rw-border: #4b5563;
}
```

### Accessibility Customization

#### Increase Font Size
```css
body {
  font-size: 18px; /* Default is 16px */
}
```

#### Increase Contrast
```css
:root {
  --rw-primary-color: #0e1f8f;  /* Darker blue */
  --rw-text-primary: #000000;   /* Pure black */
}
```

#### Disable Animations
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0s !important;
    transition-duration: 0s !important;
  }
}
```

## Configuration Options

### Hide Categories
Comment out or remove from `categoriesOrder`:

```javascript
const categoriesOrder = [
  'Housing',
  'Food',
  // 'Mental Health',  // Hidden category
];
```

### Change Tab Style
Modify the `.city-tab` CSS class:

```css
.city-tab {
  background: linear-gradient(to right, var(--rw-primary-color), var(--rw-secondary-color));
  /* Or use solid color: */
  background: var(--rw-primary-color);
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 8px;
}
```

### Modify Resource Item Layout
Edit the `.resource-item` CSS:

```css
.resource-item {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 20px;
  padding: 16px;
  border: 1px solid var(--rw-border);
}
```

## Responsive Breakpoints

The widget is mobile-first. Adjust breakpoints in CSS:

```css
/* Tablet */
@media (max-width: 768px) {
  .resource-container {
    grid-template-columns: 1fr;
  }
}

/* Large screens */
@media (min-width: 1024px) {
  .resource-container {
    max-width: 1200px;
  }
}
```

## Testing Your Changes

1. **Open in browser** — Save HTML and open locally
2. **Test mobile** — Use browser dev tools (F12) to test at 375px width
3. **Test keyboard** — Tab through all elements
4. **Test screen readers** — Use browser screen reader or NVDA
5. **Check links** — Click each link to verify it works
6. **Validate HTML** — Use [W3C Validator](https://validator.w3.org/)

## Common Customizations

### Remove Email/Phone Links
In resource items, remove or change `linkText` to plain text instead of a link.

### Add Resource Descriptions
Extend the `items` object with additional fields:

```javascript
{
  title: "Organization Name",
  description: "Main description",
  additionalInfo: "Hours, eligibility, etc.",
  link: "https://...",
  linkText: "..."
}
```

Then update the HTML rendering to display `additionalInfo`.

### Embed Size
When embedding with iframe, adjust dimensions:

```html
<iframe
  src="https://your-username.github.io/repo-name/"
  width="100%"
  height="600"  <!-- Change height -->
  frameborder="0"
  title="Community Resources">
</iframe>
```

## Need Help?

- Check [FAQ.md](FAQ.md) for common questions
- Open an [Issue](../../issues/new) for help
- See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines

## Important Notes

- Keep modifications in a single `index.html` file
- Test thoroughly before deploying
- Always maintain accessibility standards
- Keep the MIT License intact
- Keep accurate, current resource information
