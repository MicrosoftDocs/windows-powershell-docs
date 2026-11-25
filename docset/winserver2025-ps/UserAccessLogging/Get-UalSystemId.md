---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_SystemId.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualsystemid?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalSystemId
---

# Get-UalSystemId

## SYNOPSIS
Gets information that can uniquely identify a server.

## SYNTAX

```
Get-UalSystemId [-PhysicalProcessorCount <UInt32[]>] [-CoresPerPhysicalProcessor <UInt32[]>]
 [-LogicalProcessorsPerPhysicalProcessor <UInt32[]>] [-OSMajor <UInt32[]>] [-OSMinor <UInt32[]>]
 [-OSBuildNumber <UInt32[]>] [-OSPlatformId <UInt32[]>] [-ServicePackMajor <UInt32[]>]
 [-ServicePackMinor <UInt32[]>] [-OSSuiteMask <UInt32[]>] [-OSProductType <UInt32[]>]
 [-OSSerialNumber <String[]>] [-OSCountryCode <String[]>] [-OSCurrentTimeZone <Int16[]>]
 [-OSDaylightInEffect <Boolean[]>] [-OSLastBootUpTime <DateTime[]>] [-MaximumMemory <UInt64[]>]
 [-SystemSMBIOSUUID <String[]>] [-SystemSerialNumber <String[]>] [-SystemDNSHostName <String[]>]
 [-SystemDomainName <String[]>] [-CreationTime <DateTime[]>] [-SystemManufacturer <String[]>]
 [-SystemProductName <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalSystemId** cmdlet gets information that can uniquely identify a server.
Use the *CimSession* parameter to run the cmdlet on a remote server.
Otherwise, the cmdlet refers to the local server.

This cmdlet returns an **MsftUal_SystemId** object.
You can specify one or more parameters, such as the *CoresPerPhysicalProcessor* parameter.
If you do so, the cmdlet only returns an object if it matches the specified value.

## EXAMPLES

### Example 1: Get system information
```
PS C:\>Get-UalSystemId
```

This command gets an **MsftUal_SystemId** object for the current system.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CoresPerPhysicalProcessor
Specifies an array of values.
Each value specifies the number of cores for the physical processor of the system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreationTime
Specifies an array of **DateTime** objects.
Each object is the date and time that the current operating system became operational with this set of system identity properties.
If the properties of a system change, the operating system creates a new **MsftUal_SystemId** object.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogicalProcessorsPerPhysicalProcessor
Specifies an array of values.
Each value specifies the number of logical processors for an instance of a Hyper-Thread capable physical processor in the system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumMemory
Specifies an array of values.
Each value represents the maximum memory size, in bytes, for the system.
For a virtual machine, this value represents the memory size of the virtual machine as configured by the hypervisor.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSBuildNumber
Specifies an array of values.
Each value represents the build number for the operating system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSCountryCode
Specifies an array of strings.
Each value is a code for the country or region that an operating system uses, based on international phone prefixes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSCurrentTimeZone
Specifies an array of values.
Each value represents an offset, in minutes, between the operating system time and Greenwich Mean Time (GMT).
The value can be positive, negative, or zero.

```yaml
Type: Int16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSDaylightInEffect
Specifies an array of Boolean values.
If a value is $True, daylight saving time is in effect.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSLastBootUpTime
Specifies an array of **DateTime** objects.
A value represents the last time the operating system was restarted.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSMajor
Specifies an array of values.
Each value represents the major portion of the version number of an operating system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSMinor
Specifies an array of values.
Each value represents the minor portion of the version number of an operating system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSPlatformId
Specifies an array of values.
Each value represents an operating system platform.
The acceptable values for this parameter are:

- 1 - An unsupported Windows system.
- 2 - A supported Windows system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSProductType
Specifies an array of values.
Each value represents an operating system product type.
The acceptable values for this parameter are:

- 1 - Standard Edition of a server product.
- 2 - Enterprise Edition of a server product.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSSerialNumber
Specifies an array of strings.
Each string is an operating system product serial number.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSSuiteMask
Specifies an array of values.
Each value represents the suite mask for an system.
A suite mask is a combination of bit flags that identify the product suites available on the system.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalProcessorCount
Specifies an array of values.
Each value represents the number of physical processors available on the local system.
This number does not include the disabled processors.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePackMajor
Specifies an array of values.
Each value represents the major portion of the version number of a service pack.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePackMinor
Specifies an array of values.
Each value represents the minor portion of the version number of a service pack.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemDNSHostName
Specifies an array of strings.
Each string is a server name according to the Domain Name System (DNS) server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemDomainName
Specifies an array of strings.
Each sting is the name of the domain or workgroup that the server belongs to.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemManufacturer
Specifies an array of strings.
Each string represents the name of the BIOS manufacturer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemProductName
Specifies an array of strings.
Each string represents the product name specified in the system BIOS.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemSMBIOSUUID
Specifies an array of strings.
Each string represents the universally unique identifier (UUID) for this server unit as reported by the SMBIOS.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemSerialNumber
Specifies an array of strings.
Each string represents a unit identification for a server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Ual](./Get-Ual.md)

[Get-UalOverview](./Get-UalOverview.md)

