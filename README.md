# Obsidian Academic Workspace

A lightweight Obsidian vault template for academic work.

The template supports:

- administrative task management and academic CV source material;
- concise research-project organization;
- teaching preparation;
- course, seminar, lecture, talk, and paper notes;
- contact management;
- daily task planning.

## Intended scope

This vault is **not** intended to contain extended mathematical research notes, long-form research diaries, or substantial documents such as papers, lecture notes, books, or preprints.

Long mathematical writing is better kept in a dedicated LaTeX project or repository. Research-project notes in this vault are intended to remain concise and to record mainly objectives, current status, central ideas, open questions, references, collaborators, and next actions.

Teaching notes in this vault are intended for preparation, planning, session notes, and organizational material. Full polished lecture notes or books are better kept in a dedicated writing project.

## Folder structure

```text
Workspace/
├── Home.md
├── README.md
├── Admin/
│   ├── Admin.md
│   ├── CV Source.md
│   └── Admin Board.md
├── Research/
│   ├── Research.md
│   └── Ideas and Questions.md
├── Teaching/
│   └── Teaching.md
├── Notes/
│   ├── Notes.md
│   ├── Courses/
│   ├── Seminars and Lectures/
│   ├── Talks/
│   └── Papers/
├── Daily/
├── Contacts/
│   ├── Contacts.base
│   └── People/
├── _Attachments/
└── _Templates/
```

Empty structural folders are preserved in Git with `.gitkeep` files.

## Home dashboard

`Home.md` is the main dashboard. It contains:

- a link for opening today’s daily note;
- instructions for preparing tomorrow’s daily note;
- tasks scheduled for today;
- unfinished tasks whose scheduled date has passed;
- overdue deadlines;
- a bounded list of unscheduled actionable tasks;
- links to the main areas and active work.

The dashboard is intentionally compact. It is not intended to reproduce a calendar or serve as a large database.

## Admin

The `Admin/` folder contains administrative work and academic reference material.

```text
Admin/Admin.md
Admin/CV Source.md
Admin/Admin Board.md
```

`CV Source.md` is a centralized source of accurate academic CV information. It is not a polished CV; it stores source material for later adaptation into CVs, bios, reports, applications, and institutional forms.

`Admin Board.md` is the main administrative Kanban board, using:

```text
Inbox → Next → In progress → Waiting → Done
```

Substantial administrative processes, such as grant applications or reimbursements, can receive their own board from `_Templates/Admin Process Board.md`.

## Research

The `Research/` folder is for concise project organization, not extended mathematical writing.

For a new project, create:

```text
Research/Project Name/
└── Project Name.md
```

Then insert the `Research Project` template into the project home note.

`Research/Ideas and Questions.md` is an incubator for short, undeveloped ideas or mathematical questions not yet assigned to an active project. Once an idea belongs to a project, the project note becomes the canonical location for its detailed formulation.

A global research Kanban board is not included. A project-specific board may optionally be added for a bounded workflow that genuinely benefits from columns, using `_Templates/Research Workflow Board.md`.

## Teaching

The `Teaching/` folder is for courses being taught.

For a new course, create:

```text
Teaching/Course Name/
├── Course Name.md
└── Classes/
```

Then insert the `Teaching Course` template into the course overview note.

One note is used for each class session inside `Classes/`, normally using the `Teaching Class` template.

Class times, office hours, appointments, and meetings are not reflected in the vault. Those belong in an external calendar.

## Notes

The `Notes/` folder is for notes taken from external material or expository material.

```text
Notes/Courses/
Notes/Seminars and Lectures/
Notes/Talks/
Notes/Papers/
```

Intended usage:

- `Notes/Courses/` — courses, summer schools, online courses, or extended learning activities being attended.
- `Notes/Seminars and Lectures/` — standalone seminars, colloquia, invited lectures, and one-off talks being attended.
- `Notes/Talks/` — notes and outlines for talks being given.
- `Notes/Papers/` — one Markdown note per paper by default.

For unusually involved paper reading, an adjacent reading board may be added, for example:

```text
Notes/Papers/bms16.md
Notes/Papers/bms16 - Reading Board.md
```

The default remains one Markdown file per paper.

## Paper-note naming convention

Paper notes use compact alphanumeric filenames:

- one author: first three letters of the surname plus two-digit year, for example `har77`;
- multiple authors: first letter of each surname plus two-digit year, for example `km98` or `kmm87`;
- collisions: append `a`, `b`, etc., for example `ser55a`.

The `Paper Note` template includes fields for a citation key and an optional Zotero link.

## Contacts

Contacts live as one Markdown note per person in:

```text
Contacts/People/
```

The `Contact` template uses a small property schema:

```yaml
type: contact
areas: []
affiliation: ""
email: ""
homepage: ""
```

`Contacts/Contacts.base` provides table views for all contacts, research contacts, admin contacts, and teaching contacts.

## Tasks

The vault uses the Tasks community plugin.

The organizing principle is:

> Every task has one canonical location, normally the note that gives the task its context.

Examples:

- a research task belongs in the relevant project note;
- a teaching-preparation task belongs in the relevant course or class note;
- an administrative task belongs in the relevant administrative note or board.

The same task should not be manually copied into a project note, a daily note, and a dashboard. `Home.md` and daily notes use Tasks queries to surface tasks from their canonical locations.

### Scheduled dates and due dates

- A **scheduled date** means the day on which work is intended to be done on the task.
- A **due date** means a genuine deadline.

Daily planning uses scheduled dates.

```markdown
- [ ] Prepare next class ⏳ 2026-07-04
```

## Daily planning

Daily notes live in:

```text
Daily/YYYY-MM-DD.md
```

The intended workflow is:

1. In the evening, tomorrow’s daily note is created manually in `Daily/`.
2. The note is named in `YYYY-MM-DD` format.
3. The `Daily Plan` template is inserted.
4. Open tasks are reviewed from their original contexts.
5. Tomorrow is added as the scheduled date to the chosen tasks.
6. The chosen tasks appear automatically in tomorrow’s daily note.
7. Completing a task from the daily note updates the original source task.

The daily note is not a diary. It contains only loose planning blocks, a date-specific task query, and incidental notes.

## Kanban boards

The vault uses the Kanban community plugin for Markdown-backed boards.

The main board is:

```text
Admin/Admin Board.md
```

Reusable starter boards live in `_Templates`:

```text
_Templates/Admin Process Board.md
_Templates/Research Workflow Board.md
_Templates/Paper Reading Board.md
```

These are clean starter boards to duplicate when needed, not formal Obsidian template files. Checkbox cards are preferred when Tasks compatibility is desired.

## Templates

The `_Templates/` folder contains note templates and starter boards.

```text
_Templates/
├── Admin Process Board.md
├── Contact.md
├── Course Note.md
├── Daily Plan.md
├── Meeting Note.md
├── Paper Note.md
├── Paper Reading Board.md
├── Research Project.md
├── Research Workflow Board.md
├── Seminar or Lecture Note.md
├── Talk Note.md
├── Teaching Class.md
└── Teaching Course.md
```

Intended usage:

- `Daily Plan` — daily notes in `Daily/YYYY-MM-DD.md`.
- `Research Project` — concise project home notes.
- `Teaching Course` — course overview notes for courses taught.
- `Teaching Class` — notes for one class session in a course taught.
- `Course Note` — notes for courses, summer schools, or online courses attended.
- `Seminar or Lecture Note` — standalone seminars, lectures, or colloquia attended.
- `Talk Note` — title, abstract, outline, and preparation notes for talks given.
- `Paper Note` — one note per paper.
- `Meeting Note` — meetings associated with projects, courses, or administrative processes.
- `Contact` — one contact note in `Contacts/People/`.
- `Admin Process Board` — substantial administrative processes.
- `Research Workflow Board` — bounded research workflows.
- `Paper Reading Board` — unusually involved paper reading.

## Attachments

Attachments are centralized in:

```text
_Attachments/
```

Obsidian should be configured so that pasted screenshots, images, PDFs, and other attachments are automatically stored there. See [Files and links](#files-and-links) below.

## Zotero

This template does not require an Obsidian Zotero plugin. However, it is possible to use Zotero or Better BibTeX to maintain stable citation keys. The citation key and optional Zotero link are recorded in the corresponding paper note.

## Required Obsidian configuration

This template intentionally does **not** include the `.obsidian/` configuration folder.

After opening the folder as an Obsidian vault, the following settings should be configured.

### Core plugins

Enable:

- Command palette
- Daily notes
- Templates
- Bookmarks
- Bases

### Community plugins

Install and enable:

- Tasks
- Kanban

### Files and links

```text
Default location for new attachments: _Attachments
```

### Daily notes

```text
Date format: YYYY-MM-DD
New file location: Daily
Template file location: _Templates/Daily Plan
```

### Templates

```text
Template folder location: _Templates
```

### Kanban

For new boards, checkbox cards should be enabled whenever Tasks compatibility is desired.

### Bookmarks

`Home.md` should be bookmarked after the vault is opened. On desktop, it can also be pinned as a persistent tab.

## Using this GitHub template

### Option A: GitHub template repository

1. The GitHub repository page is opened.
2. **Use this template** is selected.
3. **Create a new repository** is selected.
4. A name and visibility are chosen.
5. The new repository is cloned locally.
6. The cloned folder is opened as an Obsidian vault.
7. The configuration checklist above is followed.
8. Generic placeholders are replaced with real projects, courses, contacts, and notes.

This is appropriate when the personal vault is intended to remain a Git repository.

### Option B: One-time download or copy

1. The repository is downloaded as a ZIP file or cloned locally.
2. The folder is copied to the location used for Obsidian vaults.
3. The folder is renamed if desired.
4. The folder is opened as an Obsidian vault.
5. The configuration checklist above is followed.
6. Generic placeholders are edited or replaced.

This is appropriate when the vault is not intended to be maintained with Git.

## Git and privacy notes

This template intentionally excludes the `.obsidian/` configuration folder. A published repository should not contain Sync settings, workspace state, plugin code, private notes or any other sensitive data.

If the template is maintained with Git, use a `.gitignore` excluding `.obsidian/`, `.trash/`, and local OS clutter. Empty structural folders may be preserved with `.gitkeep` files.
