# Usage Guide

This guide explains how to add meeting notes and member information to the Newport Writers website.

## Adding Meeting Notes

Meeting notes are stored in the `meeting-notes.json` file. To add a new meeting note:

1. Open `meeting-notes.json`
2. Add a new entry to the `notes` array with the following structure:

```json
{
  "id": "2026-02-05",
  "date": "2026-02-05",
  "title": "February 2026 Meeting",
  "attendees": 8,
  "summary": "We discussed our upcoming writing projects and shared progress on current works.",
  "topics": [
    "Novel writing techniques",
    "Poetry workshop planning",
    "Upcoming community events"
  ],
  "nextActions": [
    "Schedule poetry workshop for March",
    "Create shared document for project ideas",
    "Plan community reading event"
  ],
  "outcomeFile": "outcomes/2026-02-05.md"
}
```

### Fields:
- **id**: Unique identifier (use date format: YYYY-MM-DD)
- **date**: Meeting date (YYYY-MM-DD format)
- **title**: Display title for the meeting
- **attendees**: Number of people who attended (set to 0 if not yet held)
- **summary**: Brief summary of the meeting
- **topics**: Array of topics discussed (optional)
- **nextActions**: Array of action items from the meeting (optional)
- **outcomeFile**: Path to markdown file with detailed meeting outcome (optional)

The most recent meetings will appear first on the website.

## Adding Meeting Outcomes

Meeting outcomes are detailed markdown files stored in the `outcomes/` directory. They provide a more comprehensive summary after the meeting has concluded.

### Creating an Outcome File:

1. Create a new markdown file in the `outcomes/` directory
2. Name it with the meeting date (e.g., `2026-02-05.md`)
3. Write your outcome content using markdown formatting

### Example Outcome File Structure:

```markdown
# Meeting Outcome - February 2026

## Summary
Brief overview of what happened at the meeting.

## Key Achievements
- Achievement 1
- Achievement 2
- Achievement 3

## Writing Progress
Details about members' writing projects and progress shared.

## Next Steps
- Action item 1
- Action item 2

## Member Feedback
Any feedback or highlights from attendees.
```

### Markdown Formatting Supported:
- **Headers**: Use `#`, `##`, `###` for different heading levels
- **Bold**: Use `**bold text**`
- **Italic**: Use `*italic text*`
- **Lists**: Use `-` for bullet points

### Linking an Outcome to a Meeting:

Add the `outcomeFile` field to the corresponding meeting entry in `meeting-notes.json`:

```json
{
  "id": "2026-02-05",
  "date": "2026-02-05",
  ...
  "outcomeFile": "outcomes/2026-02-05.md"
}
```

The outcome will automatically appear in the meeting notes card on the website.

## Adding Members

Member information is stored in the `members.json` file. To add a new member:

1. Open `members.json`
2. Add a new entry to the `members` array with the following structure:

```json
{
  "id": "member-2",
  "name": "Jane Smith",
  "bio": "Jane is a novelist and poet who has been writing for over 10 years. She loves exploring themes of identity and belonging in her work.",
  "joinDate": "2026-01",
  "active": true
}
```

### Fields:
- **id**: Unique identifier for the member
- **name**: Member's full name
- **bio**: Short biography (2-3 sentences recommended)
- **joinDate**: When they joined (YYYY-MM format)
- **active**: Set to `true` to display, `false` to hide

Members are sorted by join date (oldest first) on the website.

## Publishing Changes

After editing the JSON files:

1. Commit your changes to the repository
2. Push to the `main` branch
3. GitHub Pages will automatically update the website within a few minutes

## Tips

- Keep summaries concise and informative
- Use topics and next actions to help members catch up if they missed a meeting
- Update member bios periodically to keep information current
- Set `active: false` for members who are no longer participating instead of deleting them
