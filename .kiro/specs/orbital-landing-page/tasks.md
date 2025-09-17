# Implementation Plan

- [ ] 1. Set up project structure and assets
  - Create index.html file with basic HTML5 structure and meta tags
  - Set up assets directory with placeholder images (solar-system.png, og-hero.png)
  - Include Tailwind CSS CDN and configure viewport meta tag
  - Add favicon placeholder and basic SEO meta tags
  - _Requirements: 4.1, 4.6, 5.8_

- [ ] 2. Implement navigation header component
  - Create sticky navigation bar with backdrop blur effect
  - Add Orbital logo text with proper typography
  - Implement navigation links (Support, Privacy, Terms) with correct URLs
  - Add responsive mobile navigation with CSS-only hamburger menu
  - Ensure proper focus states and hover effects for accessibility
  - _Requirements: 1.2, 3.1, 4.5, 5.1, 5.2, 5.3_

- [ ] 3. Build hero section layout and content
  - Create two-column responsive layout (60/40 split desktop, stacked mobile)
  - Implement headline "Build worlds. One focused minute at a time." with proper typography
  - Add explanatory subcopy about distraction-free focus and planet generation
  - Create phone mockup using pure CSS with specified dimensions (280px × 560px)
  - Add subtle glow effects and float animation to phone mockup
  - _Requirements: 1.3, 1.5, 2.4, 2.6_

- [ ] 4. Add store badges and call-to-action elements
  - Implement official Google Play and App Store badges using proper SVG assets
  - Link Google Play badge to correct URL (https://play.google.com/store/apps/details?id=com.ra.orbital)
  - Add placeholder link for App Store badge
  - Create secondary CTA link "Explore the Support Center" with proper styling
  - Ensure all badges meet accessibility requirements with proper alt text
  - _Requirements: 1.4, 4.6, 5.4, 5.5_

- [ ] 5. Implement cosmic background and visual effects
  - Create animated starfield background using CSS keyframes
  - Add CSS gradient fallback for low-power devices
  - Implement deep space color scheme matching app screenshots
  - Add support for prefers-reduced-motion to disable animations
  - Test battery impact on mobile Safari and optimize accordingly
  - _Requirements: 2.1, 2.2, 2.7_

- [ ] 6. Build feature cards section
  - Create responsive grid layout for 3-4 feature cards
  - Implement cards for "Planet Generation", "Smart Sessions", "Progress & Stories", "Gentle Reminders"
  - Add emoji icons and proper typography for each card
  - Apply gradient backgrounds with rounded corners and hover lift effects
  - Ensure proper spacing and alignment across breakpoints
  - _Requirements: 1.6, 2.3, 2.5_

- [ ] 7. Create FAQ accordion component (accessible)
  - Implement accessible accordion using HTML5 details/summary elements
  - Add 3-4 key questions about app mechanics, privacy, and pricing
  - Style accordion to match feature card design with smooth transitions
  - Ensure proper keyboard navigation and screen reader support
  - Add CSS fallback styling for browsers without details support
  - _Requirements: 1.8, 4.5_

- [ ] 8. Implement footer and social proof elements
  - Create simple two-column footer with copyright and navigation links
  - Add "Made with ✨ focus" note as specified
  - Include optional social proof section with micro-stats
  - Ensure footer styling is consistent with navigation
  - _Requirements: 1.8, 5.7_

- [ ] 9. Add light mode support and accessibility features
  - Implement light mode color palette using prefers-color-scheme
  - Ensure all interactive elements have visible focus states in both modes
  - Verify color contrast ratios meet WCAG AA standards (4.5:1 minimum)
  - Add skip-to-content link for keyboard navigation
  - Test with screen readers and ensure proper semantic markup
  - _Requirements: 2.6, 3.6, 4.4, 4.5_

- [ ] 10. Optimize performance and SEO
  - Add structured data using schema.org SoftwareApplication
  - Implement complete Open Graph and Twitter Card meta tags
  - Set proper canonical URLs (landing page canonical should point to landing URL)
  - Preload critical assets including store badge SVGs
  - Add proper alt text for all images
  - Optimize images as WebP with JPEG fallbacks
  - _Requirements: 1.8, 4.3, 4.6, 5.8_

- [ ] 11. Enhance support page with new design
  - Add consistent navigation header matching landing page
  - Implement sticky sidebar table of contents for desktop
  - Create collapsible mobile navigation and TOC
  - Apply comfortable reading width (max-w-4xl) and improved typography
  - Add section highlighting using :target pseudo-class (with optional IntersectionObserver for scroll-based highlighting)
  - _Requirements: 3.1, 3.2, 3.3, 3.4, 3.7_

- [ ] 12. Add support page interactive elements
  - Implement back-to-top button with smooth scrolling
  - Add JavaScript to toggle back-to-top button visibility on scroll (appears after 200px)
  - Add proper hover states and focus rings for all links
  - Ensure all existing anchor IDs (#privacy, #terms) remain functional
  - Apply Tailwind classes to existing content without breaking semantics
  - Test responsive behavior across all breakpoints
  - _Requirements: 3.1, 3.6, 3.8_

- [ ] 13. Implement error handling and fallbacks
  - Create baseline.css stylesheet for Tailwind CDN failures (not just noscript)
  - Add minimal fallback styles for core layout and typography
  - Ensure graceful degradation for older browsers
  - Test with JavaScript disabled to verify all functionality works
  - Add proper error handling for image loading failures
  - Implement progressive enhancement patterns throughout
  - _Requirements: 4.2, 4.4_

- [ ] 14. Conduct comprehensive testing and optimization
  - Test responsive design at breakpoints: 320px, 768px, 1024px, 1440px
  - Verify Lighthouse scores achieve 95+ for Performance, Accessibility, SEO
  - Test keyboard navigation and screen reader compatibility (VoiceOver on iOS Safari, NVDA on Windows)
  - Validate Open Graph and Twitter Card previews using Facebook Debugger and Twitter Card Validator
  - Validate all external links and store URLs
  - Test on multiple browsers: Chrome, Firefox, Safari, Edge
  - _Requirements: 4.3, 4.5_

- [ ] 15. Finalize deployment and documentation
  - Ensure single-file HTML works on GitHub Pages without build process
  - Use versioned filenames for assets instead of query parameters
  - Validate HTML and CSS for standards compliance
  - Create deployment documentation with asset optimization notes
  - Test final deployment on GitHub Pages
  - _Requirements: 4.7, 4.8_