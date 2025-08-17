# 📌 Add "Open with VS Code" to Windows Context Menu

This guide will help you add "Open with VS Code" option in the right-click menu for both directories and empty background space inside folders.

------------------------------------------------------------

## Step 1: Open Notepad
Press Win + R, type notepad, and hit Enter.  
A new Notepad window will open.

------------------------------------------------------------

## Step 2: Copy the Registry Code
Paste the following into Notepad:

```bash
[HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode]
@="Open with VS Code"
"Icon"="\"C:\\Users\\<YourUserName>\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\""

[HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode\command]
@="\"C:\\Users\\<YourUserName>\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" \"%V\""

[HKEY_CLASSES_ROOT\Directory\shell\vscode]
@="Open with VS Code"
"Icon"="\"C:\\Users\\<YourUserName>\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\""

[HKEY_CLASSES_ROOT\Directory\shell\vscode\command]
@="\"C:\\Users\\<YourUserName>\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" \"%1\""
```
------------------------------------------------------------

## Step 3: Replace <YourUserName>
Replace <YourUserName> with your actual Windows username.

To find your username, open Command Prompt and run:

echo %username%

Example output:
msi

So the path will become:
C:\Users\abcd\AppData\Local\Programs\Microsoft VS Code\Code.exe

------------------------------------------------------------

## Step 4: Save the File as .reg
In Notepad, click File > Save As.  
Change Save as type → All Files.  
Enter filename:
vscode-context.reg

Save it on your Desktop.

------------------------------------------------------------

## Step 5: Add to Registry
Go to the saved .reg file.  
Double-click it.  
Windows will ask for confirmation → Click Yes.

------------------------------------------------------------

## Step 6: Done ✅
Now, when you right-click on any folder or background inside a folder, you will see:  
Open with VS Code option.  

Clicking it will launch VS Code directly in that location. 🎉

------------------------------------------------------------

⚠️ Note: If VS Code is installed in a different location, update the path in the registry code accordingly.
