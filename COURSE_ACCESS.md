# Crisis Management Course - Access Information

## Course Successfully Deployed! ✅

Your **Crisis Management** xAPI course has been successfully deployed to Vercel and is now live!

### Course Details

**Course Name**: Crisis Management

**Course Description**: 
The phone rings. An explosion has ripped through one of your manufacturing plants. Two people have been killed, and a dozen others are injured. The media have picked up the story, and reporters are already on site. So, what do you do? How do you respond? How will you move to minimize the damage and take control of the situation? How do you lead others through a crisis—and land on your feet?

This course will help. You'll learn to prepare for, and potentially prevent, crises before they occur. And, if disaster does strike, you'll get tools to help you respond and recover.

### Course Modules

1. An Introduction to Crisis Management
2. Types of Business Crises
3. Preventing and Preparing for a Crisis
4. Responding to a Crisis
5. Recovery After a Crisis
6. Summary

### Access URLs

**Primary Course URL** (Launch Page):
```
https://staysafehub-courses.vercel.app/courses/crisis-management/scormdriver/indexAPI.html
```

**Direct Content URL**:
```
https://staysafehub-courses.vercel.app/courses/crisis-management/scormcontent/index.html
```

**Course Directory**:
```
https://staysafehub-courses.vercel.app/courses/crisis-management/
```

### Course Structure

```
courses/crisis-management/
├── tincan.xml                    # xAPI course manifest
├── tc-config.js                  # xAPI configuration
├── scormdriver/                  # SCORM/xAPI driver
│   ├── indexAPI.html            # Main launch page
│   ├── scormdriver.js           # Driver logic
│   └── auto-scripts/            # Automation scripts
└── scormcontent/                 # Course content
    ├── index.html               # Content entry point
    ├── assets/                  # Media and resources
    └── lib/                     # Libraries and frameworks
```

### xAPI Configuration

The course is configured with xAPI (Tin Can API) tracking:
- **Activity ID**: `http://7qTuNyYH3fIlpWoSE_gCVLEukt2l78Za_rise`
- **Activity Type**: `http://adlnet.gov/expapi/activities/course`
- **Launch File**: `scormdriver/indexAPI.html`

### Testing the Course

#### Option 1: Direct Browser Access
Simply open the course URL in your browser:
```
https://staysafehub-courses.vercel.app/courses/crisis-management/scormdriver/indexAPI.html
```

#### Option 2: LMS Integration
To integrate with your LMS:
1. Use the course URL as the launch URL
2. Configure xAPI endpoint in your LMS
3. The course will send xAPI statements to your LRS

#### Option 3: Embed in Website
You can embed the course using an iframe:
```html
<iframe 
  src="https://staysafehub-courses.vercel.app/courses/crisis-management/scormdriver/indexAPI.html"
  width="100%" 
  height="800px" 
  frameborder="0"
  allowfullscreen>
</iframe>
```

### CORS Configuration

The course is configured with CORS headers to allow integration with any LRS:
- **Access-Control-Allow-Origin**: `*` (allows all origins)
- **Access-Control-Allow-Methods**: `GET, OPTIONS`

This means the course can send xAPI statements to any Learning Record Store (LRS) without cross-origin issues.

### Performance Features

- **CDN Delivery**: Course is served via Vercel's global CDN
- **Caching**: Optimized caching for fast loading (1-hour cache)
- **Compression**: Automatic gzip compression
- **HTTPS**: Secure delivery via HTTPS

### Monitoring & Analytics

View deployment status and analytics at:
```
https://vercel.com/richiehiggins-projects/staysafehub-courses
```

### Adding More Courses

To add additional courses:

1. **Create course directory**:
   ```bash
   cd /home/ubuntu/staysafehub-courses-main/courses
   mkdir your-course-name
   ```

2. **Add course files**:
   - Extract your xAPI/SCORM package into the directory
   - Ensure `index.html` or launch file is present

3. **Commit and push**:
   ```bash
   git add courses/your-course-name/
   git commit -m "feat: Add [Course Name] course"
   git push origin master:main
   ```

4. **Access your course**:
   ```
   https://staysafehub-courses.vercel.app/courses/your-course-name/
   ```

### Troubleshooting

#### Course Not Loading
- Clear browser cache and reload
- Check browser console for errors (F12)
- Verify all course files were uploaded correctly

#### xAPI Tracking Not Working
- Verify LRS endpoint is configured in `tc-config.js`
- Check that LRS credentials are correct
- Ensure CORS is enabled on your LRS

#### Slow Loading
- Course files are cached for 1 hour
- First load may be slower; subsequent loads will be faster
- Large media files may take time to download

### Support

For questions or issues:
- **Email**: info@staysafehub.com
- **GitHub Repository**: https://github.com/RichieHiggins/staysafehub-courses
- **Vercel Dashboard**: https://vercel.com/richiehiggins-projects/staysafehub-courses

### Next Steps

1. ✅ Test the course in your browser
2. ✅ Integrate with your LMS or LRS
3. ✅ Share the course URL with learners
4. ✅ Monitor course completion via xAPI statements
5. ✅ Add more courses as needed

---

**Congratulations!** Your Crisis Management xAPI course is now live and ready for learners! 🎉
