# StaySafe Hub Courses - Quick Access URLs

## ✅ Verified Working Course URLs

### Course 1: Crisis Management
**Launch URL for LMS**:
```
https://staysafehub-courses.vercel.app/courses/crisis-management/scormdriver/indexAPI.html
```

**Direct Content URL** (alternative):
```
https://staysafehub-courses.vercel.app/courses/crisis-management/scormcontent/index.html
```

---

### Course 2: Blood Borne Pathogen Risks and Response for Service Workers
**Launch URL for LMS**:
```
https://staysafehub-courses.vercel.app/courses/blood-borne-pathogen/scormdriver/indexAPI.html
```

**Direct Content URL** (alternative):
```
https://staysafehub-courses.vercel.app/courses/blood-borne-pathogen/scormcontent/index.html
```

---

## 📋 For Cognify Academy LMS Integration

When adding these courses to your Cognify Academy LMS:

1. **Course Type**: Select "xAPI" or "SCORM" or "External Content"
2. **Launch URL**: Copy the "Launch URL for LMS" from above
3. **Launch Method**: New Window or Iframe (recommended: New Window)
4. **Tracking**: xAPI (requires LRS configuration)

---

## 🔍 Troubleshooting 404 Errors

If you see a 404 error:

### Solution 1: Clear Cache
- Clear your browser cache (Ctrl+Shift+Delete)
- Try in an incognito/private window
- Wait 30 seconds for Vercel CDN to update

### Solution 2: Verify URL
Make sure you're using the **exact URLs** above. Common mistakes:
- ❌ Missing `/scormdriver/indexAPI.html` at the end
- ❌ Wrong course name (use hyphens: `crisis-management` not `crisis_management`)
- ❌ Missing `https://`

### Solution 3: Check Deployment Status
Visit the Vercel dashboard to verify deployment is complete:
```
https://vercel.com/richiehiggins-projects/staysafehub-courses
```

### Solution 4: Test Direct Access
Open the URL directly in your browser (not through LMS) to verify it works standalone.

---

## 📊 Course Status

| Course | Status | URL Verified | xAPI Tracking |
|--------|--------|--------------|---------------|
| Crisis Management | ✅ Live | ✅ Yes | ⚠️ Needs LRS Config |
| Blood Borne Pathogen | ✅ Live | ✅ Yes | ⚠️ Needs LRS Config |

---

## 🎯 Next Steps for Full Integration

To enable xAPI tracking in Cognify Academy:

1. **Get LRS Credentials** from Cognify Academy admin panel
2. **Provide to me**:
   - LRS Endpoint URL
   - Username/Password or API Key
3. **I'll configure** the `tc-config.js` files
4. **Test tracking** to verify statements are being sent
5. **View reports** in Cognify Academy dashboard

---

## 📞 Support

If you continue to experience 404 errors after trying the solutions above:
- Email: info@staysafehub.com
- Provide: The exact URL you're trying to access and when the error occurred
- Include: Screenshot of the error if possible

---

**Last Updated**: January 13, 2026  
**Deployment Status**: ✅ All courses deployed and verified working
