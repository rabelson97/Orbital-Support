# Design Document

## Overview

The Orbital landing page and support page redesign will create a cohesive, premium web presence that reflects the app's cosmic theme and sophisticated planet-generation mechanics. The design emphasizes the unique value proposition of transforming focus sessions into an interstellar journey while maintaining technical simplicity through static HTML and Tailwind CSS.

## Architecture

### Technical Stack
- **Frontend**: Single-file HTML5 with Tailwind CSS via CDN
- **Styling**: Utility-first CSS with custom CSS variables for brand colors
- **Deployment**: GitHub Pages (static hosting)
- **Performance**: Inline critical CSS, preloaded assets, optimized images

### Design System
- **Color Palette**: 
  - **Dark Mode**: Deep space theme matching app screenshots
    - Primary: `#1e1b4b` (deep space blue)
    - Secondary: `#312e81` (cosmic purple)
    - Accent: `#6366f1` (nebula blue)
    - Background gradients: `from-slate-900 via-purple-900 to-slate-900`
  - **Light Mode**: Soft cosmic theme
    - Primary: `#f8fafc` (light gray)
    - Secondary: `#e2e8f0` (soft gray)
    - Accent: `#8b5cf6` (soft purple)
    - Background: `from-gray-50 via-purple-50 to-gray-50`
- **Typography**: System font stack (`-apple-system, BlinkMacSystemFont, sans-serif`)
- **Spacing**: Generous whitespace with Tailwind's spacing scale
- **Motion**: Subtle animations respecting `prefers-reduced-motion` with CSS gradient fallback for starfield on low-power devices

## Components and Interfaces

### Landing Page Components

#### 1. Navigation Header
```html
<nav class="sticky top-0 z-50 backdrop-blur-md bg-slate-900/80 border-b border-purple-800/20">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-16">
      <div class="text-xl font-bold text-white">Orbital</div>
      <div class="hidden md:flex space-x-8">
        <a href="..." class="text-gray-300 hover:text-white transition-colors">Support</a>
        <a href="..." class="text-gray-300 hover:text-white transition-colors">Privacy</a>
        <a href="..." class="text-gray-300 hover:text-white transition-colors">Terms</a>
      </div>
    </div>
  </div>
</nav>
```

#### 2. Hero Section
- **Layout**: Two-column on desktop (60/40 split), stacked on mobile
- **Left Column**: Headline, subcopy, store badges, secondary CTA
- **Right Column**: Phone mockup with solar system screenshot
- **Background**: Animated starfield with CSS keyframes (CSS gradient fallback for low-power devices)
- **Phone Mockup**: Pure CSS (280px × 560px, 2rem border-radius) with subtle glow and float animation
- **Assets**: 
  - Solar system screenshot: `assets/solar-system.png` optimized as WebP with JPEG fallback
  - Alt text: "Orbital app solar system view showing colorful generated planets in cosmic space"
  - Store badges: Official SVG assets following [Google Play Brand Guidelines](https://play.google.com/intl/en_us/badges/) and [Apple Marketing Resources](https://developer.apple.com/app-store/marketing/guidelines/)

#### 3. Feature Cards
```html
<div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
  <div class="bg-gradient-to-br from-purple-900/50 to-blue-900/50 p-6 rounded-2xl backdrop-blur-sm border border-purple-700/30 hover:scale-105 transition-transform">
    <div class="text-3xl mb-4">🪐</div>
    <h3 class="text-xl font-semibold text-white mb-2">Planet Generation</h3>
    <p class="text-gray-300">Watch unique worlds build step-by-step during your focus sessions</p>
  </div>
</div>
```

#### 4. FAQ Accordion
- **Interaction**: JavaScript-free CSS-only accordion using `:target` pseudo-class
- **Styling**: Consistent with card design, smooth transitions
- **Content**: 3-4 key questions about mechanics, privacy, pricing

#### 5. Footer
- **Layout**: Simple two-column with copyright and links
- **Styling**: Minimal, consistent with navigation

### Support Page Enhancements

#### 1. Table of Contents Sidebar
```html
<aside class="hidden lg:block fixed left-4 top-1/2 transform -translate-y-1/2 w-64">
  <nav class="bg-slate-800/50 backdrop-blur-md rounded-xl p-4 border border-purple-700/30">
    <ul class="space-y-2">
      <li><a href="#contact" class="block py-2 px-3 rounded-lg hover:bg-purple-700/30 transition-colors target:bg-purple-700/50">Contact</a></li>
      <li><a href="#faq" class="block py-2 px-3 rounded-lg hover:bg-purple-700/30 transition-colors target:bg-purple-700/50">FAQ</a></li>
      <li><a href="#privacy" class="block py-2 px-3 rounded-lg hover:bg-purple-700/30 transition-colors target:bg-purple-700/50">Privacy Policy</a></li>
      <li><a href="#terms" class="block py-2 px-3 rounded-lg hover:bg-purple-700/30 transition-colors target:bg-purple-700/50">Terms of Use</a></li>
    </ul>
  </nav>
</aside>
```
- **Highlight on Scroll**: Uses CSS `:target` pseudo-class for JavaScript-free section highlighting
- **Accessibility**: All links have visible focus states in both dark and light modes

#### 2. Content Wrapper
- **Reading Width**: `max-w-4xl` (approximately 66-72 characters)
- **Line Height**: `leading-relaxed` (1.625)
- **Margins**: Generous spacing between sections

#### 3. Mobile Navigation
```html
<input type="checkbox" id="mobile-menu" class="hidden">
<label for="mobile-menu" class="md:hidden cursor-pointer p-2">
  <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
  </svg>
</label>
```
- **Hamburger Menu**: CSS-only toggle using checkbox hack
- **TOC Integration**: Collapsible section list
- **Responsive**: Hidden on desktop, prominent on mobile

#### 4. Back-to-Top Button
```html
<button class="fixed bottom-6 right-6 bg-purple-600 hover:bg-purple-700 text-white p-3 rounded-full shadow-lg transition-all duration-300 opacity-0 invisible scroll-visible">
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18"></path>
  </svg>
</button>
```
- **Visibility**: Shows after scrolling 200px down the page
- **Smooth Scroll**: Uses CSS `scroll-behavior: smooth` for animated scrolling

## Data Models

### Page Metadata
```javascript
const pageData = {
  landing: {
    title: "Orbital — Focus that builds worlds",
    description: "Transform focus sessions into a cosmic journey. Build unique planets every 5 minutes, track progress, and stay distraction-free with Orbital.",
    ogImage: "assets/og-hero.png",
    canonical: "https://rabelson97.github.io/Orbital-Support/"
  },
  support: {
    title: "Orbital Support — Help & Documentation",
    description: "Get help with Orbital Focus app. Find answers to common questions, privacy policy, and terms of use.",
    ogImage: "assets/og-support.png"
  }
}
```

### Navigation Links
```javascript
const navigation = {
  support: "https://rabelson97.github.io/Orbital-Support/support.html",
  privacy: "https://rabelson97.github.io/Orbital-Support/support.html#privacy",
  terms: "https://rabelson97.github.io/Orbital-Support/support.html#terms",
  googlePlay: "https://play.google.com/store/apps/details?id=com.ra.orbital",
  appStore: "#" // Placeholder
}
```

### Feature Data
```javascript
const features = [
  {
    icon: "🪐",
    title: "Planet Generation",
    description: "Watch unique worlds build step-by-step during your focus sessions"
  },
  {
    icon: "⏱️",
    title: "Smart Sessions",
    description: "Automatic 5-minute intervals that create perfect focus rhythms"
  },
  {
    icon: "📊",
    title: "Progress & Stories",
    description: "Collect planets with AI-crafted lore and track your cosmic journey"
  },
  {
    icon: "🔔",
    title: "Gentle Reminders",
    description: "Weekly nudges to maintain your focus habits and momentum"
  }
]
```

## Error Handling

### Progressive Enhancement
- **No JavaScript Fallbacks**: All interactions work without JavaScript
- **Image Loading**: Proper alt text and loading states
- **Network Issues**: Graceful degradation for CDN failures

### Accessibility Fallbacks
- **Reduced Motion**: Disable animations when `prefers-reduced-motion: reduce`
- **High Contrast**: Ensure sufficient contrast ratios (4.5:1 minimum)
- **Screen Readers**: Proper ARIA labels and semantic markup

### Browser Compatibility
- **Modern Browsers**: Full experience with CSS Grid, Flexbox, backdrop-filter
- **Legacy Support**: Graceful degradation for older browsers
- **Mobile Safari**: Special handling for viewport units and backdrop-blur
- **CDN Fallback**: Minimal fallback stylesheet for Tailwind CDN failures:
```html
<noscript>
  <style>
    body { font-family: -apple-system, sans-serif; margin: 0; padding: 20px; }
    .container { max-width: 1200px; margin: 0 auto; }
    .nav { display: flex; justify-content: space-between; padding: 1rem 0; }
  </style>
</noscript>
```

## Testing Strategy

### Visual Testing
- **Responsive Breakpoints**: Test at 320px, 768px, 1024px, 1440px
- **Color Schemes**: Verify dark/light mode appearance
- **Animation States**: Test with and without motion preferences

### Accessibility Testing
- **Keyboard Navigation**: Tab through all interactive elements
- **Screen Reader**: Test with VoiceOver on iOS Safari and NVDA on Windows
- **Color Contrast**: Verify WCAG AA compliance (4.5:1 minimum)
- **Focus Management**: All interactive elements MUST have visible focus states in both dark and light modes
- **iOS Specific**: Test VoiceOver navigation patterns on iOS Safari given the mobile app audience

### Performance Testing
- **Lighthouse Scores**: Target 95+ for Performance, Accessibility, SEO
- **Core Web Vitals**: Optimize LCP, FID, CLS metrics
- **Network Conditions**: Test on slow 3G connections

### Cross-Browser Testing
- **Desktop**: Chrome, Firefox, Safari, Edge
- **Mobile**: iOS Safari, Chrome Mobile, Samsung Internet
- **Feature Detection**: Test CSS feature support

### Content Validation
- **Link Testing**: Verify all external links work correctly
- **Form Validation**: Test contact forms and interactions
- **SEO Validation**: Check meta tags, structured data
- **Social Sharing**: Verify Open Graph and Twitter Card previews

## Implementation Notes

### CSS Architecture
- **Utility-First**: Leverage Tailwind's utility classes
- **Custom Properties**: Use CSS variables for brand colors
- **Component Classes**: Create reusable component classes for complex elements
- **Media Queries**: Mobile-first responsive design

### Asset Optimization
- **Images**: Use WebP with JPEG fallbacks
- **Icons**: Inline SVGs for store badges and icons
- **Fonts**: System fonts to avoid loading delays
- **Critical CSS**: Inline above-the-fold styles

### SEO Optimization
- **Structured Data**: JSON-LD using schema.org SoftwareApplication for app store optimization
```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Orbital Focus",
  "operatingSystem": ["iOS", "Android"],
  "applicationCategory": "ProductivityApplication",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  }
}
```
- **Meta Tags**: Complete Open Graph and Twitter Card data
- **Sitemap**: Generate XML sitemap for GitHub Pages
- **Robots.txt**: Configure crawler access

### Deployment Strategy
- **GitHub Pages**: Automatic deployment on push to main
- **Branch Protection**: Require reviews for main branch
- **Asset Versioning**: Use versioned filenames instead of query parameters (GitHub Pages doesn't support custom cache headers)
  - Example: `solar-system-v1.webp` instead of `solar-system.webp?v=1`
- **Monitoring**: Set up uptime monitoring for the live site