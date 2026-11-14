# Project 002 — Windows System Diagnostics

## 1. Project Overview

**Project Type:** Windows Support / System Diagnostics  
**Environment:** Windows 365 Cloud PC  
**Operating System:** Windows 11  
**Virtual Machine Specifications:** 2 vCPU / 8 GB RAM / 128 GB Storage

### Objective

The objective of this project was to gain hands-on experience with Windows diagnostic and administrative utilities. The investigation focused on monitoring system performance, identifying hardware specifications, reviewing system events, inspecting connected devices, and examining resource utilization.
This project involved navigating built-in Windows utilities, collecting system information, observing system behavior, and documenting diagnostic findings.

### Tools Used

- Task Manager
- System Information (`msinfo32`)
- Event Viewer (`eventvwr.msc`)
- Device Manager (`devmgmt.msc`)
- Resource Monitor (`resmon`)

---

## 2. Task Manager

Task Manager was used to examine running applications and background processes, monitor system resource utilization, and review hardware performance.

### 2.1 Processes

<img width="2732" height="1782" alt="IMG_7791" src="https://github.com/user-attachments/assets/7f2b5af6-7674-41b4-ad66-53f77fd5a16d" />

**Observations:**

- Windows displayed one active application and 47 background processes.
- Overall CPU utilization was approximately 2%.
- Memory utilization was approximately 51%.
- Disk activity was displayed at 0%.
- Network utilization was displayed at 0%.
- Microsoft Edge appeared with multiple processes running.

**What I Learned:**

Task Manager provides an overview of running applications and background processes. It allows technicians to identify processes consuming system resources and investigate potential performance issues. The Processes tab is particularly useful when investigating unresponsive applications, unusually high CPU or memory utilization, and background processes affecting system performance.

### 2.2 Memory Performance

<img width="2732" height="1782" alt="IMG_7793" src="https://github.com/user-attachments/assets/10ef839f-55aa-4c3a-a703-1e243ec214da" />

**Observations:**

- Total installed memory: 8 GB.
- Memory in use: 4.0 GB.
- Available memory: 3.9 GB.
- Memory utilization: approximately 50%.
- Cached memory: 3.9 GB.
- Committed memory: 4.3 / 9.8 GB.

**What I Learned:**

The Memory section provides information about physical memory utilization, available memory, and cached memory. Monitoring these values can help identify potential memory-related performance issues, particularly when a computer experiences sluggish performance or applications struggle to operate efficiently.

### 2.3 CPU Performance

<img width="2732" height="1784" alt="IMG_7794" src="https://github.com/user-attachments/assets/f77d12d4-646d-474d-8a93-0882dc2b8710" />

**Observations:**

- Processor: AMD EPYC 7763 64-Core Processor.
- Base speed: 2.44 GHz.
- Observed processor speed: 3.14 GHz.
- Virtual processors: 2.
- CPU utilization: approximately 8% at the time of observation.
- Windows identified the environment as a virtual machine.
- One processor socket was reported.

**What I Learned:**

The CPU performance section provides information about processor utilization, speed, and available processing resources. Virtual processors represent the processing resources allocated to a virtual machine rather than the total number of physical processor cores available on the underlying hardware. Monitoring CPU utilization can help technicians investigate performance complaints and determine whether processing resources may be contributing to system slowdowns.

### 2.4 Disk Performance

<img width="2732" height="1782" alt="IMG_7795" src="https://github.com/user-attachments/assets/cb115e3f-e29b-49f8-bc74-298260248ad5" />

**Observations:**

- Drive: Disk 0 (C:).
- Device: Microsoft Virtual Disk.
- Reported drive type: HDD (SAS).
- Total capacity: 128 GB.
- Formatted capacity: 128 GB.
- Active time: 0% at the time of observation.
- Average response time: 0 ms at the time of observation.

**What I Learned:**

The Disk section provides information about storage capacity, disk activity, and transfer rates. Monitoring disk utilization and response times can help identify potential storage-related performance issues, including excessive disk activity and slow storage response.

---

## 3. System Information

System Information (`msinfo32`) was used to inspect the computer's operating system, hardware configuration, and system environment.

### 3.1 System Summary

<img width="2732" height="1782" alt="IMG_7797" src="https://github.com/user-attachments/assets/00b04205-dc12-40cf-9ecd-c40df29b6c7b" />

**Observations:**

- Operating System: Microsoft Windows 11 Enterprise
- OS Version: 10.0.26300 Build 26300
- System Manufacturer: Microsoft Corporation
- System Model: Virtual Machine
- System Type: x64-based PC
- BIOS Version/Date: Microsoft Corporation Hyper-V UEFI Release v4.1, 1/14/2026
- Installed Physical Memory (RAM): 7.95 GB
- Available Physical Memory: 3.99 GB

**What I Learned:**

System Information provides a centralized overview of a computer's hardware and software configuration. This information can help technicians identify system specifications, verify hardware compatibility, and determine whether a device meets particular software or hardware requirements.

---

## 4. Event Viewer

Event Viewer (`eventvwr.msc`) was used to examine Windows system logs.

### 4.1 Windows Event Logs

<img width="2732" height="1781" alt="IMG_7799" src="https://github.com/user-attachments/assets/5799692e-e30a-4f01-ab4e-9ae885eabb8a" />

**Observations:**

- Reviewed the Windows Logs section.
- Examined the System log categories.
- Inspected recorded Windows events and their associated severity levels.

### 4.2 Individual Event Investigation

<img width="2732" height="1783" alt="IMG_7803" src="https://github.com/user-attachments/assets/31f6b34c-2034-4c59-9199-a25bc3aa9033" />

**Event Information:**

- Log: System
- Source: Serial
- Event ID: 36
- Level: Error
- Date and Time: 11/13/2026 3:13 PM
- Description: While validating that \Device\Serial0 was really a serial port, the contents of the divisor latch register was identical to the interrupt enable and the receive registers. The device is assumed not to be a serial port and will be deleted

**What I Learned:**

Event Viewer allows technicians to investigate recorded Windows events, including informational messages, warnings, and errors.

Event sources, identification numbers, severity levels, and descriptions can help technicians investigate system behavior and identify potential causes of application or operating system issues.

---

## 5. Device Manager

Device Manager (`devmgmt.msc`) was used to inspect installed hardware devices and their reported status.

### 5.1 Hardware Inspection

<img width="1558" height="1470" alt="IMG_7804" src="https://github.com/user-attachments/assets/5fd5f89a-4e05-451d-859c-b6548806e8e1" />

**Observations:**

- Inspected installed hardware categories, including computer devices, monitors, network adapters, disk drives, display adapters, and processors.
- Identified a Microsoft Corporation Virtual Machine entry under the Computer category.
- Two monitor entries were displayed: Generic Monitor and Generic Monitor (HyperVMonitor).
- An unidentified device displaying a yellow warning indicator was observed under Other devices.
- Several hardware categories were expanded to inspect their associated devices.

**Additional Finding:**

An Unknown device was displayed with a yellow warning triangle under Other devices. This indicator suggests that Windows has identified a device with a potential issue, possibly involving its driver or device configuration.

Further investigation is required to determine the exact cause and reported device status.

**What I Learned:**

Device Manager provides an overview of installed hardware devices and their associated drivers.

It can help technicians investigate hardware recognition problems, driver-related issues, and devices reporting errors.

The warning indicator observed during this investigation demonstrated how Device Manager can help identify hardware requiring additional attention.

---

## 6. Resource Monitor

Resource Monitor (`resmon`) was used to examine system resource utilization in greater detail.

Unlike Task Manager, Resource Monitor provides more detailed information about individual processes and their associated CPU, memory, disk, and network activity.

### 6.1 Resource Monitoring

<img width="2730" height="603" alt="Bazaart_2026-11-13_213848" src="https://github.com/user-attachments/assets/7625d340-a1b4-4f5a-a894-fa98a13640ff" />

**Observations:**

**CPU:**
- Approximately 12% CPU utilization was observed.
- Two virtual processors (CPU 0 and CPU 1) were displayed.
- Individual processes and their CPU usage were listed.
- CPU activity remained relatively low during the observed monitoring period.

**Memory:**
- Approximately 4,123 MB of physical memory was in use.
- Approximately 3,907 MB was available.
- Total installed memory was approximately 8,142 MB.
- Approximately 110 MB was modified memory.
- Approximately 3,856 MB was in standby.
- Approximately 51 MB was free.

**Disk:**
- Disk activity was approximately 20 KB/sec at the time of capture.
- Highest active time was approximately 1%.
- Individual processes accessing the disk were displayed.
- Disk read and write activity could be monitored separately.

**Network:**
- Total network I/O was approximately 242 Kbps.
- Network utilization was displayed as 0%.
- Individual processes generating network traffic were listed.
- TCP connections and listening ports were available for further inspection.

**What I Learned:**

Resource Monitor provides a more detailed view of system resource utilization than Task Manager and allows technicians to examine individual processes and investigate CPU, memory, disk, and network activity.

The Memory tab also demonstrates how Windows manages physical memory, including memory in use, modified memory, standby memory, and free memory.

The Disk and Network tabs provide additional visibility into individual processes generating storage and network activity.

These capabilities can help technicians to investigate performance complaints and identifying processes that may be contributing to resource utilization.

---

## 7. Project Summary

This project provided hands-on experience using built-in Windows diagnostic and administrative utilities within a Windows 365 virtual Cloud PC.

The investigation covered:

- Monitoring running applications and background processes.
- Examining CPU, memory, and disk utilization.
- Identifying processor, memory, and storage specifications.
- Reviewing operating system and hardware configuration.
- Examining Windows system and application event logs.
- Inspecting installed hardware devices and their reported status.
- Identifying a device displaying a potential hardware or driver-related warning.
- Monitoring detailed CPU, memory, disk, and network activity.

Through this exercise, I gained practical experience navigating Windows diagnostic tools, collecting system information, interpreting resource utilization, and identifying potential issues requiring further investigation.

These utilities are commonly used in IT support environments to help technicians assess system conditions, troubleshoot reported problems, and collect information needed for further diagnosis.

### Environment Note

This project was completed using a Windows 365 Cloud PC for educational and portfolio purposes. All observations and findings reflect the virtual environment used during the investigation rather than a physical workstation.

The exercise represents self-directed hands-on learning and is not professional workplace experience.
