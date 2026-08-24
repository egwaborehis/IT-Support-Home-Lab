# Test 02 — Hardware & Device Inventory

## Objective

The objective of this test was to investigate how Windows identifies installed hardware and to verify the operating status of selected hardware devices using Device Manager.

This exercise was designed to develop practical IT support skills in hardware identification, device management and basic hardware troubleshooting.

## Tools Used

- Windows 11 Device Manager
- Windows hardware information
- Lenovo ThinkPad X13 Gen 1

## Procedure

1. Opened Windows Device Manager.
2. Reviewed the available hardware and device categories.
3. Investigated the following categories:
   - Disk drives
   - Display adapters
   - Network adapters
   - Processors
4. Identified individual hardware devices.
5. Opened the Properties window for selected devices.
6. Checked the Device Status field.
7. Recorded the results without changing device settings or drivers.

## Hardware Identified

### Storage

The system contains a WDC PC SN730 NVMe SSD.

### Graphics

The system uses:

- Intel UHD Graphics

### Network Adapters

The system contains several network-related devices, including:

- Intel Wi-Fi 6 AX201 160MHz
- Intel Ethernet Connection (10) I219-LM
- Fibocom L850-GL
- Bluetooth Device (Personal Area Network)
- Multiple Windows WAN Miniport adapters

### Processor

Device Manager displayed eight entries for the Intel Core i7-10610U processor.

These represent the processor's eight logical processors rather than eight physical CPUs.

The system has:

- 4 physical CPU cores
- 8 logical processors

## Device Health Checks

Three important hardware devices were checked through their Properties windows.

| Device | Device Status | Result |
|---|---|---|
| Intel Wi-Fi 6 AX201 160MHz | Working properly | Pass |
| Intel UHD Graphics | Working properly | Pass |
| WDC PC SN730 NVMe SSD | Working properly | Pass |

## Findings

No obvious hardware errors were identified during the Device Manager inspection.

The selected Wi-Fi, graphics and storage devices were all reported by Windows as working properly.

No devices displaying an obvious warning indicator were identified during the inspection.

## Conclusion

The hardware inventory and health check were completed successfully.

The test demonstrated how Device Manager can be used to:

- Identify installed hardware
- Identify network adapters
- Identify storage and graphics devices
- Understand logical processor entries
- Check device status
- Identify potential hardware problems

No corrective action was required because the tested devices were operating normally.

## Evidence

The following screenshots provide evidence of the investigation:

- [Device Manager Overview](device-manager%20overview.png)
- [Hardware Components and Network Adapters](device-manager%20adapters.png)
- [Processor Inventory](device-manager%20processors.png)
- [Wi-Fi Device Status](Wi-Fi%20device%20status.png)
- [Graphics Device Status](graphics%20device%20status.png)
- [Storage Device Status](storage%20device%20status.png)

Private or unnecessary system information should be removed or redacted before publishing evidence.
