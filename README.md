# 🧰 DLL Injector

![Platform](https://img.shields.io/badge/platform-Windows%2010%2B-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Language](https://img.shields.io/badge/C%2B%2B-Qt6%20%2F%20WinAPI-blue)
![Methods](https://img.shields.io/badge/injection-6%20methods-purple)

![DLL Injector Banner](https://i.imgur.com/EngOTez.png)


> **Standalone DLL injection toolkit for Windows**  
> GUI, multiple injection techniques, and real-time logging. No build required.

---

## ⚙️ Requirements

- Windows 10+ (x64)
- [VC++ Redistributable x64](https://aka.ms/vs/17/release/vc_redist.x64.exe)
- Admin rights (for elevated processes)

---

## 🚀 How to Use

1. Place `DLLInjector.exe` and `ManualMapper.exe` in the same folder
2. Run the GUI (`DLLInjector.exe`)
3. Select target process + DLL
4. Pick method:  
   `AutoDetect`, `CreateRemoteThread`, `QueueUserAPC`, `NtCreateThreadEx`, `ManualMap`, `KernelInject`
5. Click **Inject** and view logs in real-time

---

## 🧠 AutoDetect Logic

- Detects elevation, debugger presence, memory size, and architecture
- Chooses optimal method dynamically

---

## 📜 License

MIT License – see [LICENSE](LICENSE) for details

---

## ✅ To-Do

- [ ] CLI arguments support
- [ ] Fix ManualMap
- [ ] Kernel mode injector (driver)
- [ ] x86 DLL support
- [ ] GUI theme toggle Improve
- [ ] External file logging


---

## ⚠️ Disclaimer

This tool is provided **"AS IS"**, without any warranties.  
The author **is not responsible** for any misuse, damage, or illegal activity caused by this software.  
**Use at your own risk.**

---
