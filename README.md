# windows-dfir-lab21-recent-files-jump-list-investigation
## Objective

Investigate Windows Recent Items and Jump List artifacts to determine which files a user recently accessed.

This lab demonstrates how Windows stores evidence of user activity and how these artifacts can help investigators reconstruct actions performed on a system.

---

# Understanding the Artifacts

## What are Recent Items?

Windows automatically creates a shortcut (.lnk) whenever a user opens a file through File Explorer or an application.

These shortcuts are stored in:

```
%AppData%\Microsoft\Windows\Recent
```

Recent Items allow investigators to quickly determine which documents were recently opened, even if the original files have been moved or deleted.

---

## What are Jump Lists?

Jump Lists are application-specific records introduced in Windows 7.

They maintain a history of files recently opened by applications such as:

- Notepad
- Microsoft Word
- Excel
- PowerPoint
- File Explorer

They are stored in:

```
%AppData%\Microsoft\Windows\Recent\AutomaticDestinations
```

Unlike Recent Items, Jump Lists often contain richer information about user activity and are commonly examined during DFIR investigations.

---

# Lab Scenario

A Windows workstation is suspected of being used to access confidential documents.

Although no malware is detected, investigators must determine:

- Which files were recently opened
- Whether sensitive documents were accessed
- Which forensic artifacts remain after file access

The investigation focuses on Recent Items and Jump List artifacts.

---

# Skills Learned

- Windows forensic artifact analysis
- Recent Items investigation
- Jump List investigation
- User activity reconstruction
- Evidence correlation
- Timeline reconstruction

---

# Tools Used

- Windows 10
- PowerShell
- File Explorer
- Notepad

---

# Investigation Workflow

1. Create sample documents.
2. Open the documents.
3. Investigate the Recent Items folder.
4. Examine Jump List artifacts.
5. Correlate artifacts with opened files.
6. Document findings.

---

# Evidence Collected

- Recent Item (.lnk) shortcuts
- Jump List (.automaticDestinations-ms) files
- Sample documents
- PowerShell output
- File Explorer observations

---

# DFIR Importance

Recent Items and Jump Lists help investigators answer questions such as:

- What files did the user access?
- Which applications opened them?
- When were they accessed?
- Was sensitive information viewed?

These artifacts are frequently used in insider threat investigations, data theft cases, and incident response engagements.

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Collection | T1005 – Data from Local System |
| Discovery | T1083 – File and Directory Discovery |

---


troubleshooting-notes.md
Screenshots/
```
