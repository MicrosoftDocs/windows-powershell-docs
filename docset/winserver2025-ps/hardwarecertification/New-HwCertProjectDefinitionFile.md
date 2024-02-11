---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
Module Name: HardwareCertification
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hardwarecertification/new-hwcertprojectdefinitionfile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HwCertProjectDefinitionFile
---

# New-HwCertProjectDefinitionFile

## SYNOPSIS
Creates an HCK project definition file.

## SYNTAX

### PdefOverrides
```
New-HwCertProjectDefinitionFile [-ControllerName <String>] [-PdefFilePath <String>]
 [-TestCollectionFilePath <String>] [-EnableIsolateTargets] [-EnableMultiDeviceTest] [-OutputAutomatedPdef]
 [-ProjectName <String>] [-SkipTestStatus <String>] [-CrashDumpCollection <String>] [-MachineList <String[]>]
 [-MachinePool <String>] [-RunSystemTest] [-TestAllDevices] [-HwIdList <String[]>] [-DriverList <String[]>]
 [-ContainerIdList <String[]>] [-ClassIdList <String[]>] [<CommonParameters>]
```

### MachineList
```
New-HwCertProjectDefinitionFile [-ControllerName <String>] [-PdefFilePath <String>]
 [-TestCollectionFilePath <String>] [-EnableIsolateTargets] [-EnableMultiDeviceTest] [-OutputAutomatedPdef]
 [-ProjectName <String>] [-SkipTestStatus <String>] [-CrashDumpCollection <String>] -MachineList <String[]>
 [-RunSystemTest] [-TestAllDevices] [-HwIdList <String[]>] [-DriverList <String[]>]
 [-ContainerIdList <String[]>] [-ClassIdList <String[]>] [<CommonParameters>]
```

### MachinePool
```
New-HwCertProjectDefinitionFile [-ControllerName <String>] [-PdefFilePath <String>]
 [-TestCollectionFilePath <String>] [-EnableIsolateTargets] [-EnableMultiDeviceTest] [-OutputAutomatedPdef]
 [-ProjectName <String>] [-SkipTestStatus <String>] [-CrashDumpCollection <String>] -MachinePool <String>
 [-RunSystemTest] [-TestAllDevices] [-HwIdList <String[]>] [-DriverList <String[]>]
 [-ContainerIdList <String[]>] [-ClassIdList <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-HwCertProjectDefinitionFile** cmdlet creates a Windows Hardware Certification Kit (HCK) project definition file.
The project definition file includes the targets, such as devices and systems, for certification tests.
The HCK automation tool uses the settings in this file to determine which targets to test.
For more information, see [Windows Hardware Certification Kit downloads](https://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

You can update this generated file by adding any changes that are valid with respect to the project definition file schema.

## EXAMPLES

### Example 1: Create a project definition file for a driver
```
PS C:\> New-HwCertProjectDefinitionFile -MachinePool "Test07" -DriverList "disk.sys"
```

This command creates a project definition file.
The command populates the project file with HCK target values for which disk.sys is a device driver, and from all machines available in the Test07 pool.

## PARAMETERS

### -ClassIdList
Specifies an array of class GUIDs as strings.
For more information, see [Class-GUID](https://technet.microsoft.com/en-us/library/cc957340.aspx) in the TechNet library.
You can use a comma-separated list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ClassList

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerIdList
Specifies an array of container IDs, in GUID format.
You can use a comma-separated list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ContainerList

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerName
Specifies the name of the controller or test server.
The project definition file stores the controller name in the **Controller** attribute of the \<ProjectDefinitionData\> element.
If you do not provide a controller name and do not specify the **OutputAutomatedPdef** parameter, the cmdlet uses the current computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CrashDumpCollection
Specifies the type of Windows crash dump file to generate and collect for the project.
The acceptable values for this parameter are:

- Mini
- Kernel
- Full
- Disable

Default value is Disable.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Mini, Kernel, Full, Disable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriverList
Specifies an array of names of target drivers.
You can use a comma-separated list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableIsolateTargets
Indicates that the cmdlet creates an individual device family for each discovered target.
If you do not specify this parameter, the cmdlet groups targets into families based on device class.

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

### -EnableMultiDeviceTest
Indicates that multiple-device scheduling is enabled.
The project definition file stores the Boolean setting for multiple-device scheduling in the \<MultiDeviceTestGroup\> element.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: EMDT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HwIdList
Specifies an array of hardware IDs for target devices.
You can use a comma-separated list.

You can specify partial hardware IDs.
The cmdlet matches a partial value as a substring of the hardware ID format.
The comparison uses ASCII characters and is not case sensitive.
If the ID contains an ampersand character (&), enclose the ID in double quotes ("").
In Windows PowerShell®, the ampersand is a reserved character.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineList
Specifies an array of test computer names.
You can use a comma-separated list.
If you specify more than one computer, all of them must be in the same pool.

```yaml
Type: String[]
Parameter Sets: PdefOverrides
Aliases: Machine

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: MachineList
Aliases: Machine

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachinePool
Specifies the name of an existing machine pool, which contains test computers.

```yaml
Type: String
Parameter Sets: PdefOverrides
Aliases: Pool

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: MachinePool
Aliases: Pool

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputAutomatedPdef
Indicates that the cmdlet generates the following attributes in the project definition file:

- **Controller** = "\[MACHINE\]"
- **TestCollectionReadLocation** = "\[FILTERED_TEST_COLLECTION\]"
- **Path** = "\[PACKAGES\]"

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: automate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PdefFilePath
Specifies the name of the project definition file.
If you do not specify a name, the cmdlet creates a name in the following format: %UserProfile%\Desktop\PDEF_Files\PDEF_TimeDate\PDEF_OSPlatformName_TimeDate.xml.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectName
Specifies the friendly name of the project.
The project definition file stores the project name in the **Name** attribute of the \<Project\> element.
If you do not specify a name, the cmdlet generates a name that contains a time stamp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PROJ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunSystemTest
Indicates that the cmdlet specifies a single **TargetType** attribute, which equals System.
Specify this parameter for testing a whole system.
You cannot run a System test with any other query types.

A System test treats the target as a single device.
This differs from TestAllDevices, which tests every target on a system, but treats them individually.
Specify the **TestAllDevices** parameter to test all devices.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: System

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipTestStatus
Specifies the skipping mode for scheduling tests.
The project definition file stores this value in the \<TestStatusToSkip\> element.
The acceptable values for this parameter are:

- Pass
- Fail
- NoData

The default value is Pass.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SkipStatus
Accepted values: Fail, NoData

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestAllDevices
Indicates that the controller tests all target devices that it discovers.
The controller discovers devices on the computers specified by the **MachineList** or the **MachinePool** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: AllDevices

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestCollectionFilePath
Specifies the full path for a test collection .xml file.
The project definition file stores the path in the **TestCollectionReadLocation** attribute of the \<Project\> element.
If you do not specify a path, the cmdlet uses an empty string.

```yaml
Type: String
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

[New-HwCertTestCollection](./New-HwCertTestCollection.md)

