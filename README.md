# Sydney Web Design Landing Page - Maintenance Guide

This guide will help you maintain and customize the Sydney Web Design landing page. It's written for beginners with no prior coding experience.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the company name and navigation menu. To update:

1. Company Name:
```html
<!-- Find this line in the header -->
<a href="/" class="text-2xl font-bold text-blue-600">Sydney Web Design</a>
```
- Replace "Sydney Web Design" with your company name
- The `text-2xl` class controls size
- `text-blue-600` controls the blue color

### Hero Section
Located at the top of the page with the main headline:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6">Best Websites In Sydney</h1>
<p class="text-xl text-gray-600 mb-8">Professional web design services tailored for your success</p>
```

To modify:
- Replace headline text between `<h1>` tags
- Update subheading text between `<p>` tags
- Text sizes use responsive classes:
  - `text-4xl`: mobile size
  - `md:text-5xl`: tablet size
  - `lg:text-6xl`: desktop size

### Features Section
Each feature card follows this structure:

```html
<div class="p-8 rounded-2xl bg-white shadow-lg hover:shadow-xl transition-shadow duration-300">
    <div class="w-16 h-16 bg-blue-100 rounded-lg flex items-center justify-center mb-6">
        <!-- Icon SVG here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Free Hosting</h3>
    <p class="text-gray-600">Reliable and secure hosting included with every website package</p>
</div>
```

To update:
1. Modify feature title between `<h3>` tags
2. Change description between `<p>` tags
3. Key classes:
   - `shadow-lg`: adds shadow effect
   - `hover:shadow-xl`: increases shadow on hover
   - `rounded-2xl`: rounds corners

## Fixing Broken Links

### Navigation Menu Links
Current navigation links in the header:

```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Benefits</a>
    <a href="#faq" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">FAQ</a>
    <a href="#contact" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Contact</a>
</div>
```

To update:
1. Replace `href="#features"` with your section ID or page URL
2. For external links, use complete URLs: `href="https://yoursite.com/page"`
3. For internal pages, use relative paths: `href="/about.html"`

### Call-to-Action Links
Current placeholder links:

```html
<a href="https://twd.com" class="inline-block px-8 py-4 bg-blue-600 text-white font-semibold rounded-lg">
```

Replace `https://twd.com` with your actual contact or signup page URL.

## Linking Privacy and Terms Pages

### Footer Legal Links
Current placeholder links in footer:

```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2">
        <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To add privacy and terms pages:
1. Create `privacy.html` and `terms.html` in your root directory
2. Update the links:
```html
<li><a href="/privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="/terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

Common issues and solutions:

1. **Broken Internal Links**
   - Ensure section IDs match exactly (case-sensitive)
   - Example: `href="#Features"` won't link to `id="features"`

2. **Responsive Design Issues**
   - Check mobile-first classes (without prefix)
   - Then tablet (`md:`) and desktop (`lg:`) variants
   - Example: `text-xl md:text-2xl lg:text-3xl`

3. **CSS Classes Not Working**
   - Verify Tailwind CDN link is present in `<head>`
   - Check for typos in class names
   - Classes are case-sensitive

4. **Links Not Styling Correctly**
   - Ensure all classes from original links are preserved
   - Example hover effect: `hover:text-blue-600 transition-colors duration-300`

Remember to test all changes across different screen sizes using browser developer tools.