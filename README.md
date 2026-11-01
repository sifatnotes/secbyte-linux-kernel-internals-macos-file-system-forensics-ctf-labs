# secbyte-linux-kernel-internals-macos-file-system-forensics-ctf-labs
A practical collection of cybersecurity CTF labs covering Linux kernel architecture (Ring 0, LKM rootkits, Initramfs, Syscall tracing, Virtual Memory page faults, Cgroups, Namespaces, Scheduler) and macOS digital forensics (APFS Time Machine trails, evidence vault triaging, Gatekeeper security).
# Linux Kernel Internals, Syscall Tracing, Memory Forensics & macOS File System CTF Labs

Welcome to the **Linux Kernel Internals, Syscall Tracing, Memory Forensics & macOS File System CTF Lab Collection**. This repository serves as an organized, searchable catalog of practical cybersecurity labs hosted on Learn SecByte.

This collection focuses on deep OS kernel mechanics, low-level process isolation primitives, and advanced host forensics—spanning **Linux Kernel Architecture & Privilege Transitions (User space to Ring 0, Initramfs unpacking, Device drivers, LKM rootkits)**, **Linux Resource Management & Low-Level Forensics (Syscall tracing, Virtual Memory page faults, Scheduler, Cgroup isolation, Namespace drift)**, and **macOS Digital Forensics & System Auditing (APFS Time Machine backups, Evidence vault triage, Gatekeeper incidents)**.

---

## Lab Collection Index

### 1. Linux Kernel Architecture, Drivers & LKM Rootkits
* **Linux Kernel Architecture: From User Space to Ring 0**  
  *Lab Link:* [https://learn.secbyte.org/ctf/linux-kernel-architecture-from-user-space-to-ring-0](https://learn.secbyte.org/ctf/linux-kernel-architecture-from-user-space-to-ring-0)  
  *Focus:* Analyzing CPU privilege rings, context switching mechanics, system call handlers (`sysenter`/`syscall`), and transition boundaries between User Space (Ring 3) and Kernel Space (Ring 0).

<Image src="image_agent_tag_1404088853578802919" alt="x86 CPU Protection Rings diagram showing Ring 0 Kernel and Ring 3 User Applications" caption="x86 CPU Protection Rings & Execution Isolation" />

---

* **Linux Internals Lab: The Initramfs Incident**  
  *Lab Link:* [https://learn.secbyte.org/ctf/linux-internals-lab-the-initramfs-incident](https://learn.secbyte.org/ctf/linux-internals-lab-the-initramfs-incident)  
  *Focus:* Inspecting early boot initial RAM file systems (`initramfs.img`), extracting cpio archives, discovering persistence backdoors in early boot scripts, and analyzing kernel initialization routines.

* **Linux Kernel Modules: The Rogue Driver**  
  *Lab Link:* [https://learn.secbyte.org/ctf/linux-kernel-modules-the-rogue-driver](https://learn.secbyte.org/ctf/linux-kernel-modules-the-rogue-driver)  
  *Focus:* Reversing Loadable Kernel Modules (LKMs), detecting malicious module insertion (`insmod`), unhooking hooked system call tables, and auditing kernel symbol exports (`/proc/kallsyms`).

* **Kernel Crash Lab: Linux Device Drivers**  
  *Lab Link:* [https://learn.secbyte.org/ctf/kernel-crash-lab-linux-device-drivers](https://learn.secbyte.org/ctf/kernel-crash-lab-linux-device-drivers)  
  *Focus:* Triaging Linux kernel Oops and panic crash dumps (`kdump`/`crash`), analyzing null-pointer dereferences in custom character device drivers, and identifying memory corruption bugs.

### 2. Syscall Tracing, Virtual Memory & Kernel Subsystems
* **Syscall Sleuth: The Midnight Trace**  
  *Lab Link:* [https://learn.secbyte.org/ctf/syscall-sleuth-the-midnight-trace](https://learn.secbyte.org/ctf/syscall-sleuth-the-midnight-trace)  
  *Focus:* Tracing low-level system calls using `strace`, `ftrace`, and eBPF; identifying obfuscated malware execution pathways; and intercepting hidden file read/write operations.

* **Page Fault Files: Virtual Memory Forensics**  
  *Lab Link:* [https://learn.secbyte.org/ctf/page-fault-files-virtual-memory-forensics](https://learn.secbyte.org/ctf/page-fault-files-virtual-memory-forensics)  
  *Focus:* Inspecting Linux virtual memory management (`/proc/[pid]/maps` and `pagemap`), analyzing soft vs. hard page faults, and dumping raw memory pages from running processes.

* **The Scheduler's Secret**  
  *Lab Link:* [https://learn.secbyte.org/ctf/the-schedulers-secret](https://learn.secbyte.org/ctf/the-schedulers-secret)  
  *Focus:* Auditing Completely Fair Scheduler (CFS) behavior, analyzing process priority manipulation (`nice`/`renice`), and detecting CPU starvation covert timing channels.

* **Cgroup Crash Cart**  
  *Lab Link:* [https://learn.secbyte.org/ctf/cgroup-crash-cart](https://learn.secbyte.org/ctf/cgroup-crash-cart)  
  *Focus:* Inspecting Control Group (`cgroups` v1/v2) resource limits (memory, CPU, pids), diagnosing out-of-memory (OOM) killer events, and hardening container resource boundaries.

* **Namespace Drift**  
  *Lab Link:* [https://learn.secbyte.org/ctf/namespace-drift](https://learn.secbyte.org/ctf/namespace-drift)  
  *Focus:* Auditing Linux kernel namespaces (PID, Mount, Network, User, IPC, UTS), detecting namespace leaks and unshare manipulation, and auditing container isolation integrity.

### 3. macOS File System & Digital Forensics
* **macOS File System Forensics: The Time Machine Trail**  
  *Lab Link:* [https://learn.secbyte.org/ctf/macos-file-system-forensics-the-time-machine-trail](https://learn.secbyte.org/ctf/macos-file-system-forensics-the-time-machine-trail)  
  *Focus:* Investigating APFS file system snapshots, mounting historical Time Machine backup bundles, recovering deleted evidence artifacts, and auditing file modification timestamps.

<Image src="image_agent_tag_1404088853578801890" alt="macOS APFS Time Machine backup snapshot architecture diagram" caption="macOS APFS File System & Time Machine Snapshot Mechanics" />

---

* **macOS Fundamentals: Evidence Vault**  
  *Lab Link:* [https://learn.secbyte.org/ctf/macos-fundamentals-evidence-vault](https://learn.secbyte.org/ctf/macos-fundamentals-evidence-vault)  
  *Focus:* Triaging macOS forensic evidence collections (TCC databases, System Extensions, quarantine events), parsing property lists (`.plist`), and extracting user activity traces.

* **macOS Security: The Gatekeeper Incident**  
  *Lab Link:* [https://learn.secbyte.org/ctf/macos-security-the-gatekeeper-incident](https://learn.secbyte.org/ctf/macos-security-the-gatekeeper-incident)  
  *Focus:* Investigating Gatekeeper execution blocking events, auditing code signature validity (`codesign`, `spctl`), and triaging unnotarized binary execution attempts.

---

## Learning Path

### Path A: Linux Kernel & Subsystem Specialist
1. **Architecture & Boot:** Start with [Linux Kernel Architecture: From User Space to Ring 0](https://learn.secbyte.org/ctf/linux-kernel-architecture-from-user-space-to-ring-0) and [Linux Internals: The Initramfs Incident](https://learn.secbyte.org/ctf/linux-internals-lab-the-initramfs-incident).
2. **Kernel Modules & Crash Analysis:** Master LKM security via [Linux Kernel Modules: The Rogue Driver](https://learn.secbyte.org/ctf/linux-kernel-modules-the-rogue-driver) and [Kernel Crash Lab](https://learn.secbyte.org/ctf/kernel-crash-lab-linux-device-drivers).

### Path B: Linux Low-Level Memory & Isolation Specialist
1. **Syscall & Memory Tracing:** Trace kernel interactions in [Syscall Sleuth](https://learn.secbyte.org/ctf/syscall-sleuth-the-midnight-trace) and [Page Fault Files](https://learn.secbyte.org/ctf/page-fault-files-virtual-memory-forensics).
2. **Scheduler & Container Primitives:** Audit kernel features via [The Scheduler's Secret](https://learn.secbyte.org/ctf/the-schedulers-secret), [Cgroup Crash Cart](https://learn.secbyte.org/ctf/cgroup-crash-cart), and [Namespace Drift](https://learn.secbyte.org/ctf/namespace-drift).

### Path C: macOS File System Forensic Investigator
1. **APFS & Artifact Forensics:** Recover digital evidence using [macOS File System Forensics](https://learn.secbyte.org/ctf/macos-file-system-forensics-the-time-machine-trail) and [macOS Fundamentals: Evidence Vault](https://learn.secbyte.org/ctf/macos-fundamentals-evidence-vault).
2. **Security Controls:** Triage macOS execution policies in [macOS Security: The Gatekeeper Incident](https://learn.secbyte.org/ctf/macos-security-the-gatekeeper-incident).

---

## How to Use the Labs

1. Select a practice scenario from the **Lab Collection Index**.
2. Click the direct link to launch the exercise environment on Learn SecByte.
3. Review scenario directives, kernel crash dumps, initramfs archives, process trace logs, or APFS snapshot images.
4. Decompile rogue LKMs, trace process syscalls using `strace`, triage cgroup resource limits, audit macOS TCC databases, or extract hidden files from APFS Time Machine backups to capture flags.

---

## Target Audience

* **Linux Kernel Engineers & Vulnerability Researchers:** Analyze kernel privilege transitions (Ring 0), audit device driver code, inspect LKM rootkits, and triage kernel crash dumps.
* **System Administrators & Site Reliability Engineers (SREs):** Debug kernel OOM killer events, audit Cgroup/Namespace isolation boundaries, and analyze system call performance.
* **macOS Forensic Examiners & Incident Responders:** Parse APFS snapshot artifacts, mount Time Machine backups, triage TCC permissions, and evaluate Gatekeeper security events.
* **Cybersecurity Students:** Acquire practical expertise in OS kernel architecture, digital forensics, and low-level system internals.

---

## Disclaimer

All lab links provided in this repository direct to official training environments hosted on Learn SecByte. All materials and exercises are provided strictly for educational purposes, defensive skill building, and authorized security research. Unauthorized kernel modification or forensic extraction against external production systems is strictly prohibited.
