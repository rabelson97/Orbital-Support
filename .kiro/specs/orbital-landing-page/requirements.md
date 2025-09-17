# Requirements Document

## Introduction

This feature involves creating a professional landing page for the Orbital Focus app and restyling the existing support page. The landing page will serve as the primary marketing site to showcase the app's unique planet-building focus mechanics, while the support page will be enhanced with better visual design and navigation while maintaining all existing functionality and anchor links.

## Requirements

### Requirement 1: Landing Page Creation

**User Story:** As a potential user visiting the Orbital website, I want to see an engaging landing page that explains the app's concept and provides download links, so that I can understand the value proposition and easily access the app.

#### Acceptance Criteria

1. WHEN a user visits the landing page THEN the system SHALL display a responsive single-file HTML page with Tailwind CSS via CDN
2. WHEN the page loads THEN the system SHALL show a sticky navigation bar with "Orbital" logo text and links to Support, Privacy, and Terms
3. WHEN a user views the hero section THEN the system SHALL display the headline "Build worlds. One focused minute at a time." with explanatory subcopy emphasizing distraction-free focus leading to unique planet generation
4. WHEN a user sees the hero section THEN the system SHALL show official-style app store badges for Google Play and App Store using official Apple/Google design guidelines with proper accessibility
5. WHEN a user views the hero section THEN the system SHALL display a phone mockup (CSS-created frame) containing the solar system screenshot with subtle glow effects
6. WHEN a user scrolls to features THEN the system SHALL display 3-4 feature cards with minimal icons and titles like "Planet Generation", "Smart Sessions", "Progress & Stories", "Gentle Reminders"
6. WHEN a user views the page THEN the system SHALL use a dark-mode first design with deep space blues/purples matching the app screenshots
7. WHEN a user interacts with elements THEN the system SHALL provide proper focus states and hover effects
8. WHEN the page loads THEN the system SHALL include proper SEO meta tags, Open Graph data, and accessibility features

### Requirement 2: Visual Design and Branding

**User Story:** As a user viewing the Orbital landing page, I want to experience a premium, cosmic-themed design that reflects the app's space aesthetic, so that I feel confident about the app's quality and design.

#### Acceptance Criteria

1. WHEN the page renders THEN the system SHALL use a color scheme matching the app screenshots with deep space blues (#1e1b4b, #312e81) and purples
2. WHEN displaying interactive elements THEN the system SHALL include subtle animations like parallax float for the phone mockup
3. WHEN showing feature cards THEN the system SHALL use soft gradient backgrounds with rounded corners and hover lift effects
4. WHEN rendering text THEN the system SHALL use clean typography with generous spacing and proper contrast ratios
5. WHEN displaying the phone mockup THEN the system SHALL show a CSS-created frame containing the solar system screenshot with subtle glow effects
6. WHEN a user enables light mode THEN the system SHALL support light mode via prefers-color-scheme media queries
7. WHEN motion is reduced THEN the system SHALL respect prefers-reduced-motion for accessibility

### Requirement 3: Support Page Enhancement

**User Story:** As a user accessing support information, I want an improved visual design and navigation experience while maintaining all existing content and functionality, so that I can easily find the information I need.

#### Acceptance Criteria

1. WHEN a user visits the support page THEN the system SHALL maintain all existing anchor IDs (#privacy, #terms) without breaking links
2. WHEN the page loads THEN the system SHALL display a consistent navigation bar matching the landing page design
3. WHEN viewing on desktop THEN the system SHALL show a sticky sidebar table of contents for easy navigation
4. WHEN viewing on mobile THEN the system SHALL provide a collapsible navigation menu and collapsible table of contents
5. WHEN reading content THEN the system SHALL use comfortable reading width (66-72ch) with improved line height and spacing
6. WHEN interacting with links THEN the system SHALL show clear hover states and focus rings for accessibility
7. WHEN scrolling through sections THEN the system SHALL highlight the current section in the table of contents
8. WHEN scrolling THEN the system SHALL provide a back-to-top button for long content sections

### Requirement 4: Technical Implementation

**User Story:** As a developer maintaining the site, I want clean, semantic HTML with Tailwind CSS that works on GitHub Pages without build steps, so that the site is easy to maintain and deploy.

#### Acceptance Criteria

1. WHEN implementing the landing page THEN the system SHALL create a single index.html file with Tailwind CSS via CDN
2. WHEN building the support page updates THEN the system SHALL provide minimal diff-style instructions for adding classes to existing elements
3. WHEN the pages load THEN the system SHALL achieve Lighthouse scores of 95+ for performance and accessibility
4. WHEN serving content THEN the system SHALL use semantic HTML5 elements with proper landmarks and heading hierarchy
5. WHEN users navigate THEN the system SHALL support keyboard navigation and screen readers
6. WHEN the page loads THEN the system SHALL include favicon and preload critical assets like store badge SVGs for optimal performance
7. WHEN linking externally THEN the system SHALL use the correct URLs for app stores and existing support page sections
8. WHEN deployed THEN the system SHALL work on GitHub Pages without requiring any build process or frameworks

### Requirement 5: Content and Navigation

**User Story:** As a user exploring the Orbital website, I want consistent navigation and accurate content that matches the app's current features and pricing, so that I have reliable information for making decisions.

#### Acceptance Criteria

1. WHEN viewing navigation links THEN the system SHALL link to https://rabelson97.github.io/Orbital-Support/support.html for Support
2. WHEN clicking Privacy THEN the system SHALL link to https://rabelson97.github.io/Orbital-Support/support.html#privacy
3. WHEN clicking Terms THEN the system SHALL link to https://rabelson97.github.io/Orbital-Support/support.html#terms
4. WHEN viewing store badges THEN the system SHALL link Google Play to https://play.google.com/store/apps/details?id=com.ra.orbital
5. WHEN viewing the App Store badge THEN the system SHALL use a placeholder link (#) as specified
6. WHEN reading feature descriptions THEN the system SHALL accurately describe the 5-minute planet generation mechanic
7. WHEN viewing pricing information THEN the system SHALL maintain consistency with existing support page pricing ($1/month, $7/year)
8. WHEN accessing any page THEN the system SHALL include proper meta descriptions, page titles, and Open Graph images (using solar system screenshot) for rich social media previews