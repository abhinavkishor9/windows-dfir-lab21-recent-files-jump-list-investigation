# Troubleshooting Notes

## Issue 1

Recent Items folder was empty.

### Cause

The files had been created but never opened.

### Resolution

Opened each document with Notepad.

Windows then created Recent Item shortcuts.

---

## Issue 2

Shortcut files appeared instead of the original documents.

### Cause

Recent Items stores Windows shortcut (.lnk) files rather than the actual files.

### Resolution

Compared shortcut names with the original filenames.

---

## Issue 3

Many old entries appeared in Recent Items.

### Cause

Windows preserves historical user activity.

### Resolution

Used timestamps to identify the artifacts generated during this investigation.

---

## Issue 4

Multiple Jump List files were present.

### Cause

Each application maintains its own Jump List.

The folder naturally contains entries from various applications.

### Resolution

Focused on recently updated Jump List files created after opening the sample documents.

---

## Issue 5

Recent Items did not update immediately.

### Cause

Windows may delay writing artifacts until the application is closed.

### Resolution

Closed Notepad and refreshed File Explorer before rechecking the folders.

---

# Key Lessons Learned

- Recent Items stores shortcut (.lnk) files that indicate recently opened documents.
- Jump Lists store application-specific histories of recently accessed files.
- These artifacts complement each other and help reconstruct user activity.
- Timestamp analysis is essential when distinguishing current activity from historical evidence.
- Recent Items and Jump Lists are commonly examined during Windows DFIR investigations involving insider threats, data theft, and incident response.
