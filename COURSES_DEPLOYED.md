# StaySafe Hub Courses - Deployed Courses

## All Courses Successfully Deployed! ✅

Your xAPI courses have been successfully deployed to Vercel and are now live on the StaySafe Hub platform.

---

## Course 1: Crisis Management

**Course URL**:
```
https://staysafehub-courses.vercel.app/courses/crisis-management/scormdriver/indexAPI.html
```

**Course Description**:
The phone rings. An explosion has ripped through one of your manufacturing plants. Two people have been killed, and a dozen others are injured. The media have picked up the story, and reporters are already on site. So, what do you do? How do you respond? How will you move to minimize the damage and take control of the situation? How do you lead others through a crisis—and land on your feet?

**Modules**:
1. An Introduction to Crisis Management
2. Types of Business Crises
3. Preventing and Preparing for a Crisis
4. Responding to a Crisis
5. Recovery After a Crisis
6. Summary

**Activity ID**: `http://7qTuNyYH3fIlpWoSE_gCVLEukt2l78Za_rise`

---

## Course 2: Blood Borne Pathogen Risks and Response for Service Workers (US Version)

**Course URL**:
```
https://staysafehub-courses.vercel.app/courses/blood-borne-pathogen/scormdriver/indexAPI.html
```

**Course Description**:
Have you ever wondered what to do if you encounter blood or a sharp object while working? This course equips service workers with the essential knowledge and practical skills to recognize, prevent, and respond to blood borne pathogen risks in non-medical settings. You'll learn about the most common blood borne pathogens, how to spot and avoid risky situations, and the right steps to take if an exposure occurs. Through clear explanations and real-world examples, you'll gain the confidence to protect yourself and others, following OSHA, CDC, and Cal/OSHA guidelines every step of the way.

**Modules**:
1. Understanding Blood Borne Pathogens and Their Health Impacts
2. Recognizing and Preventing BBP Exposure in the Workplace
3. Responding to Blood Borne Pathogen Exposure Incidents
4. Safe Handling of Sharps and Blood Spill Cleanup

**Activity ID**: `http://f9Ou5YUUz3AZbSSMHcwp4OungJS5UBWE_rise`

---

## Integration with Cognify Academy (StaySafe Hub)

To integrate these courses with your Cognify Academy LMS for xAPI tracking:

### Step 1: Add Course to LMS

1. Log into your Cognify Academy admin panel
2. Navigate to **Courses** → **Add New Course**
3. Enter course details:
   - **Course Name**: Crisis Management (or Blood Borne Pathogen...)
   - **Course Type**: xAPI/SCORM
   - **Launch URL**: Use the course URL from above

### Step 2: Configure xAPI Tracking

Each course needs to be configured to send xAPI statements to your Cognify Academy LRS. You'll need to provide:

1. **LRS Endpoint URL**: Your Cognify Academy xAPI endpoint
2. **LRS Authentication**: Username and password or API key
3. **Activity ID**: Use the Activity ID listed above for each course

### Step 3: Update tc-config.js Files

To enable tracking, the `tc-config.js` file in each course needs to be updated with your LRS credentials. 

**Required Information**:
- LRS Endpoint URL (e.g., `https://lrs.cognify360.com/xapi/`)
- LRS Username
- LRS Password or API Key
- Actor information (learner identification)

### Current Configuration Status

⚠️ **Tracking Not Yet Configured**

The courses are currently deployed but **not yet configured** to send xAPI statements to your Cognify Academy LRS. 

To complete the setup, please provide:
1. Your Cognify Academy LRS endpoint URL
2. LRS authentication credentials (username/password or API key)
3. How you want to identify learners (email, user ID, etc.)

Once you provide these details, I can:
- Update the `tc-config.js` files for both courses
- Configure proper authentication
- Set up actor identification
- Test the xAPI tracking
- Redeploy the courses with tracking enabled

---

## Course Access Options

### Option 1: Direct Browser Access
Simply share the course URLs with learners for standalone access.

### Option 2: LMS Integration (Recommended)
Add the courses to your Cognify Academy LMS with the launch URLs above. This allows you to:
- Track learner progress
- Monitor completion rates
- View detailed xAPI statements
- Generate reports
- Manage user assignments

### Option 3: Website Embed
Embed courses using iframes:
```html
<iframe 
  src="https://staysafehub-courses.vercel.app/courses/crisis-management/scormdriver/indexAPI.html"
  width="100%" 
  height="800px" 
  frameborder="0"
  allowfullscreen>
</iframe>
```

---

## Repository Structure

```
staysafehub-courses/
├── index.html                           # Landing page
├── vercel.json                          # Vercel configuration
├── README.md                            # Setup guide
├── COURSE_STRUCTURE.md                  # Course organization guide
├── COURSES_DEPLOYED.md                  # This file
└── courses/
    ├── crisis-management/
    │   ├── tincan.xml                   # xAPI manifest
    │   ├── tc-config.js                 # xAPI config (needs LRS setup)
    │   ├── scormdriver/
    │   │   └── indexAPI.html           # Launch page
    │   └── scormcontent/
    │       └── index.html              # Course content
    └── blood-borne-pathogen/
        ├── tincan.xml                   # xAPI manifest
        ├── tc-config.js                 # xAPI config (needs LRS setup)
        ├── scormdriver/
        │   └── indexAPI.html           # Launch page
        └── scormcontent/
            └── index.html              # Course content
```

---

## Next Steps

### Immediate Actions:
1. ✅ Test both courses in your browser
2. ⚠️ Provide LRS credentials to enable xAPI tracking
3. ✅ Add courses to Cognify Academy LMS

### For Complete xAPI Tracking:
1. Provide your Cognify Academy LRS endpoint URL
2. Provide LRS authentication credentials
3. I'll update both courses with tracking configuration
4. Test xAPI statements are being sent correctly
5. Verify tracking in Cognify Academy dashboard

### Adding More Courses:
Simply upload the course zip file and I'll extract, deploy, and configure it following the same process.

---

## Support & Resources

- **GitHub Repository**: https://github.com/RichieHiggins/staysafehub-courses
- **Vercel Dashboard**: https://vercel.com/richiehiggins-projects/staysafehub-courses
- **Email Support**: info@staysafehub.com

---

**Status**: ✅ Courses deployed and accessible | ⚠️ xAPI tracking pending LRS configuration
