```markdown
# DLL Injector Suite

A standalone Windows toolset for DLL injection — no compilation needed.  
Includes:

- **DLLInjector.exe**  
  Qt6 GUI for selecting target process, DLL path and injection method.  
- **ManualMapper.exe**  
  Console app that performs _manual map_ injection with detailed logging.

---

## ⚙️ Prerequisites

1. **Windows 10 or later** (x64)  
2. **Microsoft Visual C++ Redistributable (x64)**  
   Download & install:  
   `https://aka.ms/vs/17/release/vc_redist.x64.exe`  
3. **Administrator privileges**  
   To inject into elevated processes or services, right‑click **DLLInjector.exe** → “Run as administrator”.

---

## 🚀 Quickstart

1. **Place both executables** in one folder:  
   ```
   DLLInjector.exe  
   ManualMapper.exe  
   ```
2. **Launch** the GUI:  
   ```
   DLLInjector.exe
   ```
3. **Select target process**  
   - Browse the process list or visible windows tab  
   - Filter by name or PID  
4. **Choose your DLL**  
   - Click **Select DLL**  
   - Navigate to your `.dll` file  
5. **Select injection method**  
   - **AutoDetect**: smart heuristic chooses safest/fastest method  
   - **CreateRemoteThread**: standard `LoadLibraryW` remote thread  
   - **QueueUserAPC**: `LoadLibraryA` via APC on a target thread  
   - **NtCreateThreadEx**: native `NtCreateThreadEx` call  
   - **ManualMap**: raw section mapping + shellcode entry  
   - **KernelInject**: placeholder (driver required)  
6. **Click “Inject”**  
   - For **ManualMap**, the GUI will invoke  
     `ManualMapper.exe <PID> <path-to-dll>` in background and stream its logs  
   - Other methods run directly in‑process  
7. **Monitor Logs**  
   - Real‑time log panel shows validation, allocations, writes, protections, relocations, imports, entry‑point calls, errors and exit codes.

---

## 🧠 AutoDetect

- **Elevation & Architecture**: picks driver‑level or native calls if needed  
- **Debug state**: prefers APC when a debugger is present  
- **Memory footprint**: switches to ManualMap for large targets  
- **64‑bit vs 32‑bit**: chooses correct code paths automatically  

---

## 📄 Logging & Debug

- **Merged stdout/stderr** from ManualMapper.exe → GUI log panel  
- **Verbose messages** include:  
  - PE header validation  
  - Section mapping & write errors  
  - Relocations & import resolution  
  - Memory protection adjustments  
  - Shellcode allocation & thread creation  
  - Success/failure with exit code

---

## ⚠️ Disclaimer

This software is provided “AS IS”, without warranty of any kind.  
The author **is not responsible** for damage or misuse.  
Use at your own risk.

---

## 📜 License

Distributed under the **MIT License**. See [LICENSE](LICENSE) for details.
```

