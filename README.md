# Windows Internals & Detection Engineering Research

Hands-on research exploring Windows internals, execution flow, DLL loading behavior, and detection engineering through controlled experiments and telemetry analysis.

## 🎯 Project Objectives

The goal of this project is to bridge the gap between low-level Windows behavior and practical threat detection.

Rather than relying solely on process names, command-line arguments, or individual event IDs, this research focuses on understanding **how Windows operations work, what telemetry they produce, and how that telemetry can be used to build and validate detections.**

The research follows a four-week learning and experimentation roadmap throughout November 2026.

## 🗓️ Research Roadmap

| Week | Research Focus | Key Activities | Status |
|---|---|---|---|
| Week 1 — Nov 7–8 | Windows Internals & WinDbg | CPU registers, RIP/RSP, CALL/RET, breakpoints, call stacks | 🟡 In Progress |
| Week 2 — Nov 9–15 | DLL Search Order Analysis | C++ DLL loading experiments, Procmon, WinDbg | ⏳ Planned |
| Week 3 — Nov 16–22 | Detection Engineering | Sysmon Event ID 7, Sigma rules, FP/FN analysis | ⏳ Planned |
| Week 4 — Nov 23–30 | Research & Validation | Detection limitations, reproducibility, final report | ⏳ Planned |

## 🔬 Research Modules

### Week 1 — Windows Internals & WinDbg

**Focus:** Understanding execution flow at the CPU instruction and stack level.

Topics covered:

- User-mode debugging with WinDbg
- RIP and RSP registers
- Stack memory and return addresses
- CALL and RET instructions
- INT 3 and software breakpoints
- Assembly instructions and hexadecimal opcodes
- Thread and call stack inspection
- Symbol configuration and disassembly

**Research documentation:**

[WinDbg Fundamentals — CPU Registers, Stack, and Breakpoints](week-01-windows-internals/windbg-fundamentals.md)

### Week 2 — DLL Search Order Analysis

**Focus:** Investigating how Windows resolves and loads dynamic-link libraries.

Planned experiments:

- Study Windows DLL search order
- Develop a controlled C++ DLL loader
- Compare full-path and name-based DLL loading
- Observe filesystem activity using Process Monitor
- Investigate DLL loading behavior with WinDbg
- Document security implications and defensive considerations

**MITRE ATT&CK:** [T1574.001 — Hijack Execution Flow: DLL Search Order Hijacking](https://attack.mitre.org/techniques/T1574/001/)

### Week 3 — Detection Engineering

**Focus:** Translating observed DLL loading behavior into testable detection logic.

Planned activities:

- Collect Sysmon Event ID 7 telemetry
- Develop Sigma detection logic
- Test against controlled suspicious and benign scenarios
- Investigate false positives and false negatives
- Document telemetry limitations and detection trade-offs

The objective is not merely to create a detection rule, but to evaluate **what it detects, what it misses, and why.**

### Week 4 — Research Consolidation

**Focus:** Bringing together the experiments, telemetry, and detection results.

Planned deliverables:

- Reproducible laboratory instructions
- Final technical research report
- Detection coverage and limitations
- Lessons learned
- Organized code, evidence, and documentation

## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| Debugging | WinDbg |
| Programming | C++, Python (optional) |
| System Monitoring | Process Monitor, Sysmon |
| Detection Engineering | Sigma |
| Operating System | Windows 10 |
| Framework | MITRE ATT&CK |

Tools will be introduced as needed throughout the research.

## 📁 Repository Structure

```text
Windows-Internals-Detection-Research/
│
├── README.md
│
├── week-01-windows-internals/
│   └── windbg-fundamentals.md
│
├── week-02-dll-search-order/          # Planned
│   ├── src/
│   ├── evidence/
│   └── analysis.md
│
├── week-03-detection-engineering/     # Planned
│   ├── sigma/
│   ├── sysmon/
│   └── test-results/
│
└── week-04-final-research/            # Planned
    ├── final-report.md
    └── lessons-learned.md
```

*Planned directories will be added as experiments are completed.*

## 🧪 Research Methodology

Each experiment follows a structured workflow:

1. **Understand:** Study the underlying Windows mechanism.
2. **Reproduce:** Create a controlled, harmless laboratory scenario.
3. **Observe:** Collect debugger output and relevant telemetry.
4. **Analyze:** Explain the observed execution behavior.
5. **Detect:** Develop and test detection logic where applicable.
6. **Document:** Publish findings, limitations, and reproducible steps.

This approach emphasizes understanding system behavior before writing detection rules.

## 📚 References

- [Microsoft — WinDbg Documentation](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/)
- [Microsoft — Dynamic-Link Library Search Order](https://learn.microsoft.com/en-us/windows/win32/dlls/dynamic-link-library-search-order)
- [Microsoft Sysinternals — Process Monitor](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon)
- [Microsoft Sysinternals — Sysmon](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)
- [Sigma Detection Format](https://sigmahq.io/)
- [MITRE ATT&CK](https://attack.mitre.org/)

## ⚠️ Disclaimer

All experiments are intended for educational and defensive security research in an isolated, authorized laboratory environment.

The project focuses on understanding Windows behavior, analyzing security telemetry, and evaluating detection capabilities.

---

**Author:** [Busra Ugur](https://github.com/busraugurx)

**Research Period:** November 2026

**Project Status:** Active Research
