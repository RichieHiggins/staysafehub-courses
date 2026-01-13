# Course Structure Guide

This document outlines the recommended directory structure for adding xAPI and SCORM courses to the StaySafeHub Courses repository.

## Directory Organization

```
staysafehub-courses/
├── courses/
│   ├── hotel-safety-essentials/
│   │   ├── index.html
│   │   ├── manifest.xml (SCORM only)
│   │   ├── imsmanifest.xml (SCORM 2004)
│   │   ├── package.json (optional, for xAPI config)
│   │   ├── config/
│   │   │   ├── xapi-config.json
│   │   │   └── course-metadata.json
│   │   ├── assets/
│   │   │   ├── css/
│   │   │   │   └── style.css
│   │   │   ├── js/
│   │   │   │   ├── xapi-handler.js
│   │   │   │   ├── course-logic.js
│   │   │   │   └── vendor/
│   │   │   └── media/
│   │   │       ├── images/
│   │   │       ├── videos/
│   │   │       └── audio/
│   │   ├── data/
│   │   │   ├── course-content.json
│   │   │   └── lessons/
│   │   │       ├── lesson-1.html
│   │   │       ├── lesson-2.html
│   │   │       └── lesson-3.html
│   │   └── README.md
│   │
│   └── another-course/
│       └── [similar structure]
│
└── [root files]
    ├── README.md
    ├── vercel.json
    └── .gitignore
```

## File Naming Conventions

- **Directories**: Use lowercase with hyphens (e.g., `hotel-safety-essentials`)
- **Files**: Use lowercase with hyphens or underscores (e.g., `xapi-config.json`)
- **HTML files**: Use descriptive names (e.g., `lesson-1.html`, `quiz.html`)
- **Media files**: Include file type in name (e.g., `intro-video.mp4`, `icon-check.svg`)

## xAPI Course Structure

### Configuration File: `config/xapi-config.json`

```json
{
  "course": {
    "id": "hotel-safety-essentials-v1",
    "name": "Hotel Safety Essentials",
    "description": "Comprehensive training for hotel safety protocols",
    "version": "1.0.0",
    "language": "en-US"
  },
  "xapi": {
    "version": "1.0.3",
    "lrs": {
      "endpoint": "https://your-lrs-endpoint.com/xapi/",
      "auth": {
        "username": "${LRS_USERNAME}",
        "password": "${LRS_PASSWORD}"
      }
    },
    "actor": {
      "name": "Learner",
      "mbox": "mailto:learner@staysafehub.com"
    }
  },
  "tracking": {
    "trackPageViews": true,
    "trackInteractions": true,
    "trackCompletion": true,
    "trackQuizzes": true
  }
}
```

### JavaScript Handler: `assets/js/xapi-handler.js`

```javascript
// Example xAPI handler
class XAPIHandler {
  constructor(config) {
    this.config = config;
    this.lrs = this.initLRS();
  }

  initLRS() {
    // Initialize LRS connection
  }

  sendStatement(verb, object, context) {
    // Send xAPI statement to LRS
  }

  trackPageView(pageTitle) {
    // Track page view
  }

  trackCompletion(score, duration) {
    // Track course completion
  }
}
```

### Course Metadata: `config/course-metadata.json`

```json
{
  "metadata": {
    "title": "Hotel Safety Essentials",
    "author": "StaySafeHub",
    "created": "2024-01-13",
    "updated": "2024-01-13",
    "version": "1.0.0",
    "duration": "45 minutes",
    "difficulty": "Intermediate",
    "targetAudience": ["Hotel Staff", "Managers"],
    "keywords": ["safety", "hotel", "compliance", "training"]
  },
  "learning_objectives": [
    "Understand hotel safety protocols",
    "Identify potential hazards",
    "Respond to emergencies",
    "Maintain compliance standards"
  ],
  "modules": [
    {
      "id": "module-1",
      "title": "Safety Fundamentals",
      "duration": "15 minutes",
      "lessons": 3
    },
    {
      "id": "module-2",
      "title": "Emergency Procedures",
      "duration": "20 minutes",
      "lessons": 2
    },
    {
      "id": "module-3",
      "title": "Compliance & Documentation",
      "duration": "10 minutes",
      "lessons": 1
    }
  ]
}
```

## SCORM Course Structure

### SCORM 1.2 Manifest: `manifest.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest identifier="hotel-safety-essentials" version="1.0">
  <organizations default="org1">
    <organization identifier="org1">
      <title>Hotel Safety Essentials</title>
      <item identifier="item1" identifierref="res1">
        <title>Course Content</title>
      </item>
    </organization>
  </organizations>
  <resources>
    <resource identifier="res1" type="webcontent" href="index.html">
      <file href="index.html"/>
      <file href="assets/css/style.css"/>
      <file href="assets/js/scorm-handler.js"/>
    </resource>
  </resources>
</manifest>
```

### SCORM 2004 Manifest: `imsmanifest.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest identifier="hotel-safety-essentials-2004" version="1.0">
  <organizations default="org1">
    <organization identifier="org1">
      <title>Hotel Safety Essentials</title>
      <item identifier="item1" identifierref="res1">
        <title>Course Content</title>
      </item>
    </organization>
  </organizations>
  <resources>
    <resource identifier="res1" type="webcontent" href="index.html">
      <file href="index.html"/>
      <file href="assets/css/style.css"/>
      <file href="assets/js/scorm-handler.js"/>
    </resource>
  </resources>
</manifest>
```

## Course README Template

Each course should include a `README.md` file:

```markdown
# Course Name

Brief description of the course.

## Overview

Detailed course overview and objectives.

## Learning Outcomes

- Outcome 1
- Outcome 2
- Outcome 3

## Course Structure

- Module 1: Topic
- Module 2: Topic
- Module 3: Topic

## Duration

Estimated completion time.

## Requirements

- Browser compatibility
- JavaScript enabled
- Internet connection for xAPI tracking

## Access

- Direct URL: `https://staysafehub-courses.vercel.app/courses/course-name/`
- LMS Integration: Available via xAPI/SCORM

## Support

Contact: info@staysafehub.com
```

## Asset Organization

### CSS Files
- `assets/css/style.css` - Main stylesheet
- `assets/css/responsive.css` - Mobile/responsive styles
- `assets/css/print.css` - Print styles (optional)

### JavaScript Files
- `assets/js/xapi-handler.js` - xAPI integration
- `assets/js/scorm-handler.js` - SCORM integration
- `assets/js/course-logic.js` - Course functionality
- `assets/js/vendor/` - Third-party libraries

### Media Files
- `assets/media/images/` - Course images
- `assets/media/videos/` - Video content
- `assets/media/audio/` - Audio content
- `assets/media/documents/` - PDFs and other documents

## Deployment Checklist

Before pushing your course to the repository:

- [ ] All files are in the correct directory structure
- [ ] `index.html` is the entry point
- [ ] All asset paths are relative (not absolute)
- [ ] Configuration files are properly formatted JSON/XML
- [ ] Course README is complete
- [ ] No sensitive credentials in configuration files
- [ ] Media files are optimized for web
- [ ] All links are tested and working
- [ ] Course is tested in multiple browsers
- [ ] xAPI/SCORM tracking is functional

## Git Workflow for Adding Courses

1. Create a feature branch:
   ```bash
   git checkout -b feature/add-hotel-safety-course
   ```

2. Add course files:
   ```bash
   mkdir -p courses/hotel-safety-essentials/{config,assets/{css,js,media},data}
   # Add your course files
   ```

3. Commit changes:
   ```bash
   git add courses/hotel-safety-essentials/
   git commit -m "feat: Add Hotel Safety Essentials course"
   ```

4. Push and create PR:
   ```bash
   git push origin feature/add-hotel-safety-course
   ```

## Performance Optimization

### File Size Recommendations

- **HTML files**: < 500 KB
- **CSS files**: < 100 KB
- **JavaScript files**: < 500 KB per file
- **Images**: < 200 KB per image (use WebP format)
- **Videos**: Use streaming or external hosting
- **Total course size**: < 50 MB recommended

### Optimization Tips

- Minify CSS and JavaScript
- Compress images (use TinyPNG or similar)
- Use SVG for icons and graphics
- Implement lazy loading for media
- Cache static assets appropriately
- Use gzip compression on the server

## Support

For questions about course structure or deployment, contact the development team.
