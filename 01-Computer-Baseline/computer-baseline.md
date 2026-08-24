# Computer Baseline

## Purpose

This document records the baseline configuration of the computer being used for my IT Support Home Lab.

The baseline provides a reference point before carrying out troubleshooting and technical exercises.

## System Information

| Component | Specification |
|---|---|
| Operating System | Windows 11 Pro |
| Windows Version | 25H2 |
| CPU | Intel Core i7-10610U |
| CPU Cores | 4 cores / 8 logical processors |
| RAM | 32 GB |
| Storage | 475 GB |
| Available Storage | 406 GB |
| System Type | 64-bit |
| Manufacturer | Lenovo |
| Model | ThinkPad X13 Gen 1 |
| BIOS Mode | UEFI |
| Secure Boot | Enabled |

## Network Configuration

The computer is connected to a local network using Wi-Fi.

- IPv4 address: `192.168.1.xxx` (redacted)
- Default gateway: `192.168.1.xxx` (redacted)
- Subnet mask: `255.255.255.0`

Private network information has been redacted from the public repository.

## Baseline Observations

The computer has sufficient RAM and available storage for the planned IT support exercises.

The system uses UEFI firmware and has Secure Boot enabled.

The computer will be used to practise:

- Windows troubleshooting
- Networking
- Hardware and device management
- Software troubleshooting
- Command-line tools
- System administration
- Simulated help-desk scenarios

## Evidence

System information was collected using built-in Windows tools including:

- System Information (`msinfo32`)
- Windows version information (`winver`)
- File Explorer
- Command Prompt (`ipconfig`)

Screenshots may be included where they provide useful evidence while ensuring that private information is removed or redacted.

## Performance Baseline

The system was observed under normal idle conditions using Windows Task Manager.

### Performance at Idle

| Resource | Observed Usage |
|---|---:|
| CPU | 3% |
| Memory | 24% |
| Disk | 4% |
| Wi-Fi | 0 Kbps |
| GPU | 1% |

The system was not performing any intensive tasks during this observation.

### Running Processes

The Processes tab was also reviewed to identify applications and services using system resources.

The highest visible CPU users included:

- Google Chrome
- Task Manager
- Desktop Window Manager
- Steam Client WebHelper
- System and Windows background services

No obvious resource bottleneck was identified during the baseline observation.

### Observations

The computer had relatively low CPU, disk and GPU utilisation while idle.

Approximately 24–25% of the available memory was being used, leaving substantial memory available for additional applications and tasks.

Task Manager itself contributed a small amount of CPU and memory usage while it was open. This is expected and was taken into consideration when observing the system.

## Evidence

The following screenshots provide evidence of the computer's normal operating condition during the baseline assessment:

- [Task Manager Performance](./task-manager-idle.png)
- [Running Processes](./processes-idle.png)

These screenshots show the system's resource usage and running processes during normal operation.
