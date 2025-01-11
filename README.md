# DefenderCheck
Quick tool to help make evasion work a little bit easier.

> **Warning:** As of the 1.337.157.0 Defender signature update, [DefenderCheck is classified as VirTool:MSIL/BytzChk.C!MTB](https://twitter.com/matterpreter/status/1387858265686544393?s=20). As a workaround while I work to get around this, please disable Real-time Protection in Defender before compiling DefenderCheck.  

Takes a binary as input and splits it until it pinpoints that exact byte that Microsoft Defender will flag on, and then prints those offending bytes to the screen. This can be helpful when trying to identify the specific bad pieces of code in your tool/payload.

![](/demo.gif)

**Note:** Defender must be enabled on your system, but the realtime protection and automatic sample submission features should be disabled.

## Changes in This Fork

- **Custom `tempDir` Support**: You can now specify a custom temporary directory when running DefenderCheck.
    - By default, the tool uses **`C:\Temp`**.
    - If you supply a second argument to DefenderCheck, that path will be used instead.

### Usage Example (New Custom Directory)

```powershell
# Default usage (uses C:\Temp):
.\DefenderCheck.exe C:\Temp\mimikatz.exe

# Specify a custom temporary directory:
.\DefenderCheck.exe C:\Temp\mimikatz.exe D:\MyCustomTemp
```

Where:

- `C:\Temp\mimikatz.exe` is the **binary** you want DefenderCheck to analyze.
- `D:\MyCustomTemp` is your **optional** override for the temp folder.
