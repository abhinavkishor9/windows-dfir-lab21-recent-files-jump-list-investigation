# Investigation Notes

## Investigation Scenario

A Windows workstation is suspected of being used to access confidential documents.

The objective is to reconstruct recent user activity by examining Windows forensic artifacts rather than relying solely on the original files.

---

# Understanding the Evidence

Windows records user activity in multiple locations.

For this investigation, two important artifacts were examined.

### Recent Items

Recent Items contains shortcut (.lnk) files created whenever a user opens a document.

Location:

```
%AppData%\Microsoft\Windows\Recent
```

These shortcuts provide evidence that a file was accessed.

---

### Jump Lists

Jump Lists are application-specific records of recently opened files.

Location:

```
%AppData%\Microsoft\Windows\Recent\AutomaticDestinations
```

Jump Lists often provide stronger evidence because they are maintained separately for each application.

---

# Environment

Operating System

- Windows 10

Tools Used

- File Explorer
- PowerShell
- Notepad

---

# Sample Files Created

- EmployeeList.txt
- Passwords.txt
- ConfidentialReport.txt

---

# Investigation Steps

## Step 1

Created the working directory.

```
C:\RecentFilesLab
```

---

## Step 2

Created three sample text files using PowerShell.

Purpose:

Generate realistic documents for forensic analysis.

---

## Step 3

Opened each file using Notepad.

This action caused Windows to generate Recent Item shortcuts and update Jump List artifacts.

---

## Step 4

Investigated the Recent Items folder.

Observed:

- EmployeeList shortcut
- Passwords shortcut
- ConfidentialReport shortcut

These entries confirmed that the files had been opened.

---

## Step 5

Navigated to:

```
%AppData%\Microsoft\Windows\Recent\AutomaticDestinations
```

Observed multiple Jump List files.

These files indicate that applications had recorded recently opened documents.

---

## Step 6

Compared the evidence.

The Recent Items folder and Jump List artifacts both reflected the documents accessed during the lab.

---

# Findings

Recovered evidence showed access to:

- EmployeeList.txt
- Passwords.txt
- ConfidentialReport.txt

Both forensic artifacts successfully captured user activity.

---

# DFIR Analysis

Recent Items provide a quick overview of recently accessed files.

Jump Lists provide additional application-specific evidence that strengthens forensic analysis.

Using both artifacts together allows investigators to:

- Reconstruct user activity
- Validate file access
- Support incident investigations
- Build forensic timelines

---

# Conclusion

Windows automatically preserves evidence of recently accessed files through Recent Items and Jump Lists.

These artifacts are valuable during DFIR investigations because they help reconstruct user actions even when the original files are no longer available.
