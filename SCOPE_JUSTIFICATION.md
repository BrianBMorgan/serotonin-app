# Google OAuth Scope Justification for Serotonin App

## Application Overview
**App Name**: Serotonin
**Developer**: Brian Morgan
**Purpose**: A mood-based productivity and task management app that helps users organize tasks according to their emotional state and energy levels.

## Sensitive Scopes Requested

### 1. `https://www.googleapis.com/auth/userinfo.email`
**Scope Type**: Sensitive
**Why Required**:
- **Primary Use**: To identify the authenticated user and personalize the app experience
- **Specific Feature**: Used by the @Mention Scanner feature to search Google Workspace documents (Docs, Sheets, Slides) for mentions of the user's email address
- **User Benefit**: Allows users to quickly find all documents where they've been @mentioned, helping them track action items and collaborative work
- **Data Handling**: Email is stored locally on the user's device only, never transmitted to our servers
- **Alternative Considered**: None - email is required to perform mention searches across Google Workspace

### 2. `https://www.googleapis.com/auth/tasks`
**Scope Type**: Sensitive (read/write access)
**Why Required**:
- **Primary Use**: Import and sync user's tasks from Google Tasks into Serotonin
- **Specific Feature**: Two-way sync between Google Tasks and Serotonin's mood-based task system
- **User Benefit**: Users can manage their existing Google Tasks within Serotonin, automatically categorized by mood and energy requirements
- **Data Handling**: Tasks are stored locally on device; sync occurs only when user explicitly triggers it
- **Write Access Justification**: Required to mark tasks as completed in Google Tasks when user completes them in Serotonin
- **Alternative Considered**: Read-only would limit functionality; users expect bidirectional sync

### 3. `https://www.googleapis.com/auth/calendar.readonly`
**Scope Type**: Sensitive
**Why Required**:
- **Primary Use**: Access calendar events to find meetings with attached Google Doc notes
- **Specific Feature**: "Sync from Calendar Events" - searches user's calendar for meetings they attended with Google Doc attachments (Gemini meeting notes)
- **User Benefit**: Automatically imports action items from meeting notes without manual searching
- **Data Handling**: Calendar data is processed locally, only relevant meeting information is retained
- **Read-Only Justification**: App never modifies calendar events, only reads them to find meeting notes
- **Alternative Considered**: None - calendar access is essential to identify relevant meetings

### 4. `https://www.googleapis.com/auth/drive.readonly`
**Scope Type**: Highly Sensitive
**Why Required**:
- **Primary Use**: Search Google Drive for meeting notes and documents containing action items
- **Specific Features**:
  1. Find Google Docs attached to calendar meetings
  2. Search for documents modified in the last 30 days for mention scanning
  3. Access document metadata (filename, modification date) to present results to user
- **User Benefit**: Centralized access to action items scattered across multiple documents
- **Data Handling**: Only searches user's own Drive; metadata and relevant excerpts stored locally
- **Read-Only Justification**: App never modifies, deletes, or uploads files to Drive
- **Scope Limitations**:
  - Only accesses documents user owns or has access to
  - Searches limited to recent timeframes (7-30 days)
  - No bulk downloading of files
- **Alternative Considered**: Per-file access would require users to manually select each document, defeating the purpose of automated scanning

### 5. `https://www.googleapis.com/auth/documents.readonly`
**Scope Type**: Highly Sensitive
**Why Required**:
- **Primary Use**: Read content from Google Docs to extract action items and search for mentions
- **Specific Features**:
  1. Parse Gemini-generated meeting notes for action items assigned to the user
  2. Search document text for mentions of user's email address
  3. Extract context around mentions (surrounding text)
- **User Benefit**: Automatic extraction of relevant tasks and mentions without manual copy/paste
- **Data Handling**:
  - Document content processed locally on device
  - Only relevant excerpts (action items, mention context) are stored
  - Full document content is never stored or transmitted to our servers
- **Read-Only Justification**: App never edits or modifies document content
- **Scope Limitations**:
  - Only reads documents user has access to
  - Limited to documents linked from calendar or found in Drive search
  - Parses only structured content (action items, mentions)
- **Alternative Considered**: Manual copy/paste would eliminate the automation benefit

### 6. `https://www.googleapis.com/auth/spreadsheets.readonly`
**Scope Type**: Highly Sensitive
**Why Required**:
- **Primary Use**: Search Google Sheets for mentions of user's email address
- **Specific Feature**: @Mention Scanner for spreadsheets
- **User Benefit**: Find all spreadsheet cells containing user mentions, with cell location (e.g., "Sheet1!A5")
- **Data Handling**:
  - Only searches cell values for email matches
  - Stores cell location and surrounding context locally
  - No bulk export of spreadsheet data
- **Read-Only Justification**: App never modifies spreadsheet data or formulas
- **Scope Limitations**:
  - Searches limited to recent files (30 days)
  - Only matches email address, not broad keyword searches
  - Maximum 20 spreadsheets scanned per request
- **Alternative Considered**: None - Sheets-specific API required to search cell contents efficiently

### 7. `https://www.googleapis.com/auth/presentations.readonly`
**Scope Type**: Highly Sensitive
**Why Required**:
- **Primary Use**: Search Google Slides presentations for mentions of user's email
- **Specific Feature**: @Mention Scanner for presentations
- **User Benefit**: Find mentions in slide content and speaker notes across all presentations
- **Data Handling**:
  - Searches slide text and notes for email matches
  - Stores slide number and mention context locally
  - No export of full presentation content
- **Read-Only Justification**: App never modifies slides or presentation structure
- **Scope Limitations**:
  - Searches limited to recent files (30 days)
  - Only matches email address in text content
  - Maximum 20 presentations scanned per request
- **Alternative Considered**: None - Slides-specific API required to access slide content and notes

---

## Data Privacy & Security Commitments

### Local Storage First
- All user data (moods, tasks, profile) stored locally on device
- Google data processed locally, only relevant excerpts retained
- No user data transmitted to our servers

### Minimal Data Transfer
- API calls only when user explicitly triggers sync or scan
- Only necessary fields requested from APIs (not full documents)
- Data transfer limited by timeframes (7-30 days)

### No Third-Party Sharing
- Zero data sharing with advertisers or analytics services
- No selling or monetizing of user data
- OpenAI API used only for meeting transcription (user-initiated)

### User Control
- All Google features are optional
- Users can disconnect Google account anytime
- Clear in-app explanations of what each feature does
- Manual sync (auto-sync is opt-in)

### Compliance
- Adheres to Google API Services User Data Policy
- Complies with Limited Use requirements
- GDPR and CCPA compliant
- Comprehensive privacy policy available

---

## Limited Use Disclosure Compliance

Serotonin's use of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements:

✅ **We only request access to Google user data necessary for user-facing features**
✅ **We do not transfer Google data to third parties except for feature functionality**
✅ **We do not use Google data for advertising purposes**
✅ **We do not use Google data for creditworthiness or lending**

---

## User Flow Examples

### Example 1: @Mention Scanner
1. User connects Google account in Settings
2. User's email automatically retrieved and stored locally
3. User taps "Scan for @Mentions"
4. App searches Docs, Sheets, and Slides for email mentions
5. Results displayed with document links and context
6. User taps "Open Document" to view in Google Workspace

### Example 2: Meeting Notes Sync
1. User connects Google account
2. User enters first/last name in profile
3. User taps "Sync from Calendar Events"
4. App searches calendar for meetings user attended (last 7 days)
5. Finds meetings with Google Doc attachments
6. Reads docs to find action items mentioning user's name
7. Imports action items as tasks, categorized by mood
8. Duplicate detection prevents re-importing same tasks

### Example 3: Google Tasks Sync
1. User connects Google account
2. User taps "Sync Tasks"
3. App imports all Google Tasks
4. Tasks displayed with mood-based recommendations
5. When user completes task in Serotonin, it syncs back to Google Tasks

---

## App Screenshots for Verification

**Available Upon Request:**
1. Google OAuth consent screen flow
2. Settings screen showing sync options
3. @Mention Scanner results screen
4. Calendar Events sync in action
5. Privacy policy displayed in-app

---

## Contact Information

**Developer**: Brian Morgan
**Email**: support@vibecode.app
**GitHub Repository**: https://github.com/BrianBMorgan/serotonin-app
**Homepage**: https://brianb morgan.github.io/serotonin-app/homepage.html
**Privacy Policy**: https://brianb morgan.github.io/serotonin-app/privacy-policy.html

---

## Additional Notes

- App is in active development, available via Vibecode platform
- No previous policy violations or security incidents
- Regular security audits and dependency updates
- Commitment to user privacy and data protection
- Open to Google's security review and recommendations

---

**Prepared for Google Cloud OAuth Verification**
**Date**: January 2025
**App Version**: 1.0.0
