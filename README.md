## 💾 4.3 Where Data is Stored (weight: 3)
**Weight:** 3  

**Description:**  
Understand where various types of information are stored on a Linux system.

**Notes:**  
- 💻 **Programs and configuration:**  
  - Executables: `/bin`, `/usr/bin`, `/usr/local/bin`  
  - System configuration: `/etc/`  
  - User-specific configuration: hidden files in home directories (e.g., `~/.bashrc`)  
  - Some programs use `/opt/` for optional packages  

- ⚙️ **Processes:**  
  - Each process has a unique PID (process ID)  
  - `/proc/` provides a virtual filesystem with process info (`/proc/<pid>/status`)  
  - `ps` and `top` show active processes and resource usage  

- 🧠 **Memory addresses:**  
  - Physical vs virtual memory  
  - `/proc/meminfo` shows detailed memory info  
  - Swap space: used when RAM is full (`/swapfile` or `/dev/sdX`)  

- 📣 **System messaging:**  
  - `dmesg` shows kernel ring buffer messages  
  - Important for boot errors, hardware detection, and driver messages  

- 📝 **Logging:**  
  - Logs stored in `/var/log/`  
  - Common files:  
    - `/var/log/syslog` — general system messages  
    - `/var/log/messages` — critical system events (Red Hat-based)  
    - `/var/log/auth.log` — authentication logs  
    - `/var/log/kern.log` — kernel messages  
  - Log rotation via `logrotate`  

- 🛠️ **Key directories:**  
  - `/boot/` — Kernel images and bootloader files  
  - `/proc/` — Virtual filesystem, runtime process and system info  
  - `/dev/` — Device files (block, character devices)  
  - `/sys/` — Kernel and hardware info (modern sysfs)  

**Partial List of Key Knowledge (in order):**
- ⚙️ **ps, top, free** — Process monitoring, memory usage, PID awareness.  
- 📣 **syslog, dmesg** — System messages, boot messages, kernel info.  
- 💻 **/etc/, /var/log/** — Configuration files, log storage, log rotation.  
- 🛠️ **/boot/, /proc/, /dev/, /sys/** — Boot files, process info, devices, kernel info.  

**Exam Tips / Extra Notes:**  
- Virtual filesystems (`/proc`, `/sys`) do not consume disk space.  
- Swap is not permanent storage; used as overflow for RAM.  
- `/dev/sd*` devices represent physical storage; partitions are numbered (`/dev/sda1`).  
- `top` updates dynamically; `ps` is a snapshot.  
- Hidden files (starting with `.`) in home directories often store user-level configs.  
- Kernel messages can help troubleshoot hardware issues without accessing logs.  
- Logs may rotate; check `/var/log/` for older archived logs (`.gz`).  
