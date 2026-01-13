# StaySafeHub Courses

Static hosting for xAPI and SCORM courses on Vercel.

## Project Overview

This repository serves as a centralized hosting solution for xAPI (Experience API) and SCORM course packages for the StaySafeHub platform. It provides a reliable, scalable infrastructure for delivering course content to learners.

## Features

- **xAPI Support**: Full support for Experience API (Tin Can API) course tracking
- **SCORM Compatibility**: Support for SCORM 1.2 and SCORM 2004 course packages
- **Static Hosting**: Optimized for fast, reliable content delivery via Vercel CDN
- **CORS Enabled**: Cross-origin resource sharing configured for LMS integration
- **Caching**: Intelligent caching headers for optimal performance

## Repository Structure

```
staysafehub-courses/
├── README.md              # This file
├── vercel.json           # Vercel deployment configuration
├── .gitignore            # Git ignore rules
└── courses/              # Course packages (xAPI/SCORM)
    └── [course-folders]
```

## Getting Started

### Prerequisites

- Git installed on your local machine
- GitHub account with access to the repository
- Vercel account (for deployment)
- SSH key configured for GitHub (recommended)

### Local Setup

1. **Clone the repository**:
   ```bash
   git clone git@github.com:RichieHiggins/staysafehub-courses.git
   cd staysafehub-courses
   ```

2. **Verify the setup**:
   ```bash
   git remote -v
   git log --oneline
   ```

## Deployment

### Deploying to Vercel

#### Option 1: Using Vercel CLI

1. **Install Vercel CLI**:
   ```bash
   npm install -g vercel
   ```

2. **Deploy the project**:
   ```bash
   vercel
   ```

3. **Follow the prompts**:
   - Link to your GitHub repository
   - Select the project scope (your account)
   - Confirm deployment settings

#### Option 2: GitHub Integration (Recommended)

1. **Connect your repository to Vercel**:
   - Go to [Vercel Dashboard](https://vercel.com/dashboard)
   - Click "Add New..." → "Project"
   - Select "Import Git Repository"
   - Search for and select `staysafehub-courses`
   - Click "Import"

2. **Configure project settings**:
   - **Framework Preset**: Other (static)
   - **Build Command**: Leave empty (static files)
   - **Output Directory**: `.` (root)
   - **Environment Variables**: Add any required variables

3. **Deploy**:
   - Click "Deploy"
   - Vercel will automatically deploy from the `master` branch

### Automatic Deployments

Once connected to Vercel via GitHub:
- Every push to the `master` branch triggers an automatic deployment
- Preview deployments are created for pull requests
- Deployment status is visible in GitHub checks

## Adding Course Content

### Directory Structure

Create a `courses/` directory in the repository root:

```
courses/
├── course-1/
│   ├── index.html
│   ├── manifest.xml (for SCORM)
│   ├── assets/
│   │   ├── css/
│   │   ├── js/
│   │   └── media/
│   └── data/
│       └── xapi-statements.json
└── course-2/
    └── [similar structure]
```

### xAPI Course Format

For xAPI courses, include:
- Course HTML/web content
- JavaScript files for xAPI statement generation
- Configuration file with LRS endpoint details

Example xAPI configuration:
```json
{
  "lrs": {
    "endpoint": "https://your-lrs-endpoint.com/xapi/",
    "username": "your-username",
    "password": "your-password"
  },
  "course": {
    "id": "course-unique-id",
    "name": "Course Name",
    "description": "Course Description"
  }
}
```

### SCORM Course Format

For SCORM packages:
- Package as standard SCORM 1.2 or SCORM 2004
- Include `manifest.xml` in the course root
- Ensure all assets are properly referenced

## Git Workflow

### Making Changes

1. **Create a feature branch**:
   ```bash
   git checkout -b feature/add-new-course
   ```

2. **Make your changes**:
   ```bash
   # Add course files, update documentation, etc.
   ```

3. **Stage and commit**:
   ```bash
   git add .
   git commit -m "Add new course: Course Name"
   ```

4. **Push to GitHub**:
   ```bash
   git push origin feature/add-new-course
   ```

5. **Create a Pull Request**:
   - Go to GitHub repository
   - Click "Compare & pull request"
   - Add description and submit

6. **Merge to master**:
   - After review and approval, merge the PR
   - Vercel automatically deploys the changes

### Commit Message Guidelines

Use clear, descriptive commit messages:
- `feat: Add new course - Hotel Safety Essentials`
- `fix: Correct xAPI endpoint configuration`
- `docs: Update README with deployment instructions`
- `chore: Update dependencies`

## Configuration

### Vercel Configuration (vercel.json)

The `vercel.json` file includes:

- **Headers**: CORS, caching, and security headers
- **Rewrites**: URL routing for course access
- **Build Settings**: Static file serving configuration

### Environment Variables

If needed, add environment variables in Vercel dashboard:
1. Go to Project Settings → Environment Variables
2. Add variables for LRS credentials or other sensitive data
3. Redeploy for changes to take effect

## Performance Optimization

### Caching Strategy

- **HTML files**: 1-hour cache
- **Static assets** (CSS, JS, images): Long-term caching with versioning
- **Course packages**: Configured via HTTP headers

### Best Practices

- Compress media files before uploading
- Use CDN-friendly file formats
- Implement lazy loading for large courses
- Minimize HTTP requests per course

## Troubleshooting

### Deployment Issues

**Problem**: Deployment fails with "Build error"
- **Solution**: Check that all files are properly committed to Git
- Ensure no large binary files are being tracked
- Review Vercel build logs for specific errors

**Problem**: Course content not loading
- **Solution**: Verify file paths are relative, not absolute
- Check CORS headers are properly configured
- Ensure all assets are included in the repository

### Git Issues

**Problem**: SSH key not recognized
- **Solution**: Ensure SSH key is added to GitHub account
- Run `ssh -T git@github.com` to verify connection

**Problem**: Cannot push to repository
- **Solution**: Verify you have push permissions
- Check that the remote URL is correct: `git remote -v`

## Support & Documentation

- **Vercel Documentation**: https://vercel.com/docs
- **xAPI Specification**: https://github.com/adlnet/xAPI-Spec
- **SCORM Documentation**: https://scorm.com/

## License

Internal use only - StaySafeHub

## Contact

For questions or issues, contact the development team at info@staysafehub.com
