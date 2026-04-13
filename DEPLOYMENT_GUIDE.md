# EMR Demo Deployment Guide

## Overview
You have **4 main options** to have your physiotherapist friend fill in the EMR based on the video and use that data for your demo.

---

## **Option 1: Export/Import JSON (SIMPLEST) ⭐ RECOMMENDED FOR YOUR USE CASE**

### What You Get
- A form that your friend fills in
- One-click "Export Data" button that converts all filled data to JSON
- One-click "Import Data" button to re-populate the form anytime
- No server needed, no deployment required

### How It Works
1. **Send her the HTML file**: `emr_demo_export.html`
2. **She fills in the form** based on the video
3. **She clicks "💾 Export Data"** → JSON is copied to clipboard
4. **She sends you the JSON** (via email, message, etc.)
5. **You paste it back** → Auto-populates the entire form for your demo video

### For Your Demo Video
You can:
- **Pre-populate**: Import the JSON before recording to show filled form
- **Show auto-population**: Import data in real-time during demo (looks impressive!)
- **Store multiple sessions**: Keep different JSON files for different scenarios

### JSON Format Example
```json
{
  "pain": "Yes",
  "painLocation": "Right knee",
  "painDescription": "Sharp pain on movement",
  "pfreq": "Movement",
  "painIntensity": "4",
  "subjectiveFindings": "Patient reports difficulty walking up stairs...",
  "pulseRate": "72",
  "bpSystolic": "120",
  "bpDiastolic": "80",
  ...
}
```

### Pros
✅ Zero setup required  
✅ Works on any device  
✅ No internet needed  
✅ Private (data stays local)  
✅ Perfect for quick demos  

### Cons
❌ Manual copy-paste of JSON  
❌ Less real-time collaboration  

---

## **Option 2: Google Form + Auto-Population**

### What You Get
- Cloud-based form your friend can fill from any device
- Responses saved to Google Sheets
- You can script auto-population into the EMR HTML

### How It Works
1. Create a Google Form with the same questions as your EMR
2. Share the form link with your friend
3. She fills it out based on the video
4. Responses appear in Google Sheets
5. You convert sheet data to JSON and import into EMR

### Setup Steps
1. Go to https://forms.google.com
2. Create form with your EMR field names
3. Share link: `https://forms.google.com/form/[YOUR_ID]`
4. She submits responses
5. Download responses as CSV → Convert to JSON → Import

### Pros
✅ Easy to share link  
✅ Automatic data collection  
✅ Time-stamped entries  
✅ Good for multiple sessions  
✅ Can see responses in real-time  

### Cons
❌ Requires Google account  
❌ Manual CSV→JSON conversion  
❌ Additional setup needed  

---

## **Option 3: Airtable Shared Base (MOST PROFESSIONAL)**

### What You Get
- Collaborative spreadsheet view
- Real-time syncing
- Built-in API for auto-import
- Professional interface

### How It Works
1. Create Airtable base with EMR field names
2. Share base link with your friend (read/write access)
3. She fills fields in table view
4. You connect Airtable API to EMR HTML
5. One-click sync to auto-populate EMR

### Setup (Quick)
1. Go to https://airtable.com (free account)
2. Create new base
3. Add fields matching your EMR
4. Share base link: `https://airtable.com/invite/[YOUR_ID]`
5. Install Airtable JS API in EMR HTML

### Pros
✅ Beautiful UI  
✅ Real-time collaboration  
✅ Can see her filling form live  
✅ Easy to manage multiple sessions  
✅ Professional appearance  

### Cons
❌ Requires setup  
❌ Airtable account needed  
❌ API key management  

---

## **Option 4: Dedicated Demo Web App (MOST PROFESSIONAL)**

### What You Get
- Separate EMR for data collection (physiotherapist's view)
- Separate EMR for playback (your demo view)
- Real-time sync between both
- Professional demo experience

### How It Works
1. Host both HTML versions online
2. Your friend: `data-entry.html` - filled by physiotherapist
3. You control: `demo-playback.html` - shows auto-population live
4. JavaScript syncs data between pages

### Deployment Options
- **GitHub Pages** (Free): Push HTML files to GitHub, publish as GitHub Pages
- **Netlify** (Free): Drag & drop HTML files to Netlify
- **Vercel** (Free): Connect GitHub repo, auto-deploys

### Setup (Netlify - 5 minutes)
1. Go to https://netlify.com
2. Click "Drag and drop to deploy"
3. Drop your HTML file
4. Share link with friend: `https://your-site.netlify.app/`
5. She fills form
6. You see real-time sync

### Pros
✅ No local file sharing  
✅ Professional URL  
✅ Works on any device  
✅ Real-time collaboration  
✅ Looks impressive in demo  

### Cons
❌ Requires account setup  
❌ Need to manage hosting  
❌ Slightly more technical  

---

## **My Recommendation For Your Use Case**

**Use Option 1 (Export/Import JSON)** because:
1. ✅ You have the file ready: `emr_demo_export.html`
2. ✅ Zero deployment needed
3. ✅ Works immediately
4. ✅ Perfect for single-session demo
5. ✅ Easy to show data transfer in demo video
6. ✅ Can demonstrate "smart form auto-population"

**Then upgrade to Option 4** if you want:
- Professional deployment for stakeholder demos
- Real-time collaboration with physiotherapists
- Multiple patient scenarios

---

## **Step-by-Step: Using Option 1**

### Step 1: Send the Form to Your Friend
```
Subject: Help me demo EMR - 5 minutes

Hi [Friend],

I'm building a demo of an EMR system that auto-populates based on 
physiotherapy sessions. Can you fill in this form based on the video I sent?

Just click this file and fill in all the fields you can:
[Attach: emr_demo_export.html]

When done, click "💾 Export Data" and send me the JSON text.

Thanks!
```

### Step 2: She Fills the Form
- Opens `emr_demo_export.html` in browser
- Navigates through tabs
- Fills in fields based on video
- Takes ~10-15 minutes

### Step 3: She Exports
- Clicks "💾 Export Data (JSON)"
- JSON automatically copied to clipboard
- She pastes it in email/message to you
- Or saves as `session_data.json`

### Step 4: You Import for Demo
```
A. To show auto-population live:
   1. Open emr_demo_export.html
   2. Click "📥 Import Data (JSON)"
   3. Paste her data
   4. All fields populate instantly ← Record this!

B. To prepare demo video:
   1. Import the JSON
   2. Take screenshots
   3. Record screen with auto-population demo
```

### Step 5: Use in Demo Video Narrative
```
"When a physiotherapist finishes a session, instead of 
manually typing everything into the EMR, our system can 
intelligently populate fields. Watch as I import real 
session data..."

[Show import happening]
[Show fields auto-populating]
[Zoom in on specific populated fields]

"This saves the clinician 15-20 minutes per session."
```

---

## **File You Already Have**

I've created: **`emr_demo_export.html`**

This includes:
- ✅ All EMR tabs (Pain, Observation, ROM, Mobility, etc.)
- ✅ Export button → exports to JSON
- ✅ Import button → imports from JSON
- ✅ Clear button → clears all data
- ✅ 50+ data fields ready to capture
- ✅ Demo mode notice for clarity

---

## **Quick Reference: All Your Files**

| File | Purpose |
|------|---------|
| `emr_complete.html` | Full EMR template (display only) |
| `emr_demo_export.html` | **USE THIS** - Has export/import |
| Your JSON file | Data from physiotherapist |

---

## **Advanced: Storing Multiple Sessions**

If you want to collect data from multiple scenarios:

```
Session 1 - Acute Knee Injury.json
Session 2 - Post-Stroke Recovery.json
Session 3 - Chronic Pain Management.json
```

You can:
1. Collect each session separately
2. Store all JSON files
3. Rapidly switch between scenarios in demo
4. Show how system handles different patient types

---

## **Questions?**

- **Q: Does she need to install anything?**  
  A: No! Just open the HTML file in any browser.

- **Q: What if she forgets to export?**  
  A: Ask her to fill again. Also fast second time.

- **Q: Can I edit the JSON manually?**  
  A: Yes! It's just text. Edit directly, then import.

- **Q: How long does it take?**  
  A: Filling form: 10-15 min. Export/import: 1 minute.

- **Q: Can I add more fields later?**  
  A: Yes! Tell me which fields. I'll add them to the HTML.

---

## **Next Steps**

1. **Immediately**: Send `emr_demo_export.html` to your physio friend
2. **While she fills**: Plan your demo narrative
3. **After she sends**: Import data and test auto-population
4. **For recording**: Use Option 4 (web app) for professional appearance
