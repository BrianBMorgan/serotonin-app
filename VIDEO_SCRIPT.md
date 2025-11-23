# Serotonin App - Google OAuth Demo Video Script

## Video Overview
**Length**: 2-3 minutes
**Purpose**: Show Google reviewers exactly how each sensitive scope is used
**Recording Device**: Your phone (screen recording + voiceover)

---

## 📱 Recording Setup

### Before You Start:
1. Enable screen recording on your phone:
   - **iOS**: Settings → Control Center → Add Screen Recording
   - Swipe down from top-right, tap record button
2. Clear any sensitive data from the app
3. Have a test Google account ready
4. Practice the flow once before recording

### Video Settings:
- **Orientation**: Portrait (vertical)
- **Quality**: Highest available
- **Audio**: Speak clearly, moderate pace
- **Background**: Quiet environment

---

## 🎬 Video Script & Storyboard

### SCENE 1: Introduction (0:00 - 0:20)
**Visual**: App home screen
**Voiceover**:
> "Hi! This is Serotonin, a mood-based productivity app that helps users manage tasks according to their emotional state. Today I'll show you how we use Google API scopes to provide valuable features to our users. All features are optional, and users have full control over their data."

**Actions**:
- Show the app home screen briefly
- Navigate to Settings tab

---

### SCENE 2: Connecting Google Account (0:20 - 0:45)
**Visual**: Settings screen → Connect Google button → OAuth consent screen
**Voiceover**:
> "When users choose to connect their Google account, they see this consent screen. Let me show you what permissions we request and why."

**Actions**:
1. Tap "Connect Google Account"
2. Show the Google OAuth consent screen
3. **Pause and point out** the scopes listed:
   - Read your email address
   - View and manage Google Tasks
   - View your calendars
   - View your Google Drive files
   - View your Google Docs, Sheets, and Slides

**Voiceover during pause**:
> "As you can see, we clearly request access to Tasks, Calendar, Drive, and document viewing. Let me show you exactly how each is used."

4. Complete sign-in

---

### SCENE 3: Email Address Scope (0:45 - 1:00)
**Visual**: Settings screen showing connected account
**Voiceover**:
> "First, the email address scope. We automatically retrieve the user's email address and store it locally on their device. This is used for our mention scanning feature, which I'll demonstrate shortly."

**Actions**:
- Show the connected account in Settings (with email visible if possible)
- Briefly show where email is stored/used

---

### SCENE 4: Google Tasks Sync (1:00 - 1:20)
**Visual**: Settings → Sync Tasks button → Task import
**Voiceover**:
> "The Tasks scope allows users to import their Google Tasks into Serotonin. Watch what happens when I tap Sync Tasks."

**Actions**:
1. Tap "Sync Tasks"
2. Show loading indicator
3. Show success message (e.g., "Imported 5 tasks")
4. Navigate to Tasks tab
5. Show imported tasks with mood categorization

**Voiceover**:
> "Tasks are automatically categorized based on their energy and focus requirements. The app only syncs when the user explicitly requests it, and all task data is stored locally on the device."

---

### SCENE 5: Calendar & Drive Scopes - Meeting Notes (1:20 - 1:50)
**Visual**: Settings → Sync from Calendar Events → Results
**Voiceover**:
> "The Calendar and Drive scopes work together to help users import action items from meeting notes. Let me demonstrate."

**Actions**:
1. Tap "Sync from Calendar Events"
2. Show loading indicator
3. Show success message (e.g., "Imported 3 action items from 2 meetings")

**Voiceover**:
> "The app searches the user's calendar for meetings they attended in the last 7 days. When it finds meetings with attached Google Docs, it reads those documents to extract action items that mention the user by name. This saves users from manually searching through meeting notes."

**Actions**:
4. Navigate to Tasks tab
5. Show newly imported action items
6. Point out one task showing it came from a meeting note

---

### SCENE 6: @Mention Scanner - Docs, Sheets, Slides (1:50 - 2:30)
**Visual**: Settings → Scan for @Mentions → Results screen
**Voiceover**:
> "Now for the mention scanner - this is where we use the Docs, Sheets, and Slides scopes. This feature helps users find everywhere they've been mentioned across their Google Workspace documents."

**Actions**:
1. Tap "Scan for @Mentions"
2. Show the scanner screen with user's email displayed
3. Tap "Scan Last 30 Days"
4. Show loading with progress

**Voiceover during loading**:
> "The app searches through Google Docs, Sheets, and Slides from the last 30 days, looking for mentions of the user's email address."

5. Show results screen with multiple documents
6. Expand one document to show:
   - Document type (Doc/Sheet/Slide)
   - Document name
   - When it was modified
   - Location of mention (e.g., "Sheet1!A5" or "Slide 3")
   - Context around the mention

**Voiceover**:
> "Results show the document name, type, and exactly where the mention appears - like this cell in a spreadsheet, or this slide in a presentation. Users can tap to open the document directly in Google Workspace."

7. Tap "Open Document" to show it opens in browser/Google app

---

### SCENE 7: Privacy & Data Handling (2:30 - 2:50)
**Visual**: Settings → Show disconnect option
**Voiceover**:
> "All of these features prioritize user privacy. Data is processed locally on the device, we never store user data on our servers, and we don't share data with third parties. Users can disconnect their Google account at any time."

**Actions**:
1. Show the "Disconnect" button
2. Optionally show Settings with toggle for auto-sync (showing manual control)

---

### SCENE 8: Closing (2:50 - 3:00)
**Visual**: App home screen
**Voiceover**:
> "That's how Serotonin uses Google API scopes - to help users stay organized and find important information across their Google Workspace. All features are optional, transparent, and designed with privacy in mind. Thank you for watching!"

**Actions**:
- Show app home screen one final time
- Fade out

---

## 🎥 Recording Tips

### Do's:
✅ Speak clearly and at a moderate pace
✅ Show each feature working in real-time
✅ Point out the consent screen scopes
✅ Demonstrate actual data being imported/scanned
✅ Show that everything is user-initiated (button clicks)
✅ Mention "local storage" and "privacy" multiple times
✅ Keep video under 3 minutes

### Don'ts:
❌ Don't show any real sensitive data (use test account)
❌ Don't rush through the steps
❌ Don't skip the OAuth consent screen
❌ Don't make it too long (Google reviewers are busy)
❌ Don't use shaky camera movements
❌ Don't have background noise

---

## 📝 Alternative: Create Slides Instead

If recording video is difficult, you can create a slide presentation with screenshots showing:

1. **Slide 1**: App overview
2. **Slide 2**: OAuth consent screen with scopes
3. **Slide 3**: Email scope usage (Settings screen)
4. **Slide 4**: Tasks sync (before/after screenshots)
5. **Slide 5**: Calendar meeting sync (process + results)
6. **Slide 6**: Mention scanner (search screen)
7. **Slide 7**: Mention results (showing Docs/Sheets/Slides)
8. **Slide 8**: Privacy controls (disconnect button)
9. **Slide 9**: Summary of scope usage

Then record yourself narrating the slides.

---

## 📤 After Recording

### 1. Edit the Video (Optional):
- Trim any mistakes at beginning/end
- Add text overlays for key points:
  - "User-initiated sync"
  - "Local storage only"
  - "Read-only access"
  - "Optional feature"

### 2. Upload to YouTube:
- **Title**: "Serotonin App - Google OAuth Scope Usage Demo"
- **Description**:
  ```
  This video demonstrates how the Serotonin app uses Google API scopes to provide user value:

  - Email scope: Identify user for mention scanning
  - Tasks scope: Import and sync Google Tasks
  - Calendar scope: Find meetings with notes
  - Drive scope: Search for documents
  - Docs/Sheets/Slides scopes: Read content for mentions

  All features are optional, user-initiated, and privacy-focused.
  Data is stored locally on the device.

  Privacy Policy: https://brianb morgan.github.io/serotonin-app/privacy-policy.html
  ```
- **Privacy**: Unlisted (only for Google reviewers)
- **Category**: Science & Technology

### 3. Get the YouTube URL:
- Copy the unlisted video URL
- Add it to your Google OAuth verification form

---

## 🎯 Key Messages to Emphasize

Throughout the video, make sure to emphasize:

1. **User Control**: "Users choose to connect" / "Users tap to sync"
2. **Local Storage**: "Stored locally on device" / "Never sent to our servers"
3. **Read-Only**: "We only read documents, never modify them"
4. **Transparency**: "Users see exactly what's being synced"
5. **Optional**: "All Google features are optional"
6. **Value**: "Saves time" / "Helps users stay organized"
7. **Privacy**: "No third-party sharing" / "Can disconnect anytime"

---

## ✅ Checklist Before Submitting

- [ ] Video shows OAuth consent screen with all scopes
- [ ] Each sensitive scope is demonstrated with actual usage
- [ ] Video emphasizes user control and privacy
- [ ] Video is under 3 minutes
- [ ] Audio is clear and understandable
- [ ] No sensitive/personal data visible
- [ ] Video is uploaded to YouTube as "Unlisted"
- [ ] YouTube URL is ready for OAuth verification form

---

**Good luck with your recording! This demo will show Google exactly how you're using their APIs responsibly.**
