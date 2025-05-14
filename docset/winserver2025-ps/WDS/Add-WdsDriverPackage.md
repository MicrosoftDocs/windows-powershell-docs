---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsDriverPackage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/add-wdsdriverpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WdsDriverPackage
---

# Add-WdsDriverPackage

## SYNOPSIS
Adds an existing driver package to a driver group or injects it into a boot image.

## SYNTAX

### IdIntoDriverGroupName
```
Add-WdsDriverPackage -Id <Guid> -GroupName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### IdIntoBootImageProperties
```
Add-WdsDriverPackage -Id <Guid> -Architecture <Architecture> [-FileName <String>] -ImageName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### NameIntoBootImageProperties
```
Add-WdsDriverPackage -Architecture <Architecture> [-FileName <String>] -ImageName <String> -Name <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### NameIntoDriverGroupName
```
Add-WdsDriverPackage -GroupName <String> -Name <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WdsDriverPackage** cmdlet adds an existing driver package to a driver group or injects a driver package into a boot image.
Use the Import-WdsDriverPackage cmdlet to import driver packages into the Windows Deployment Services driver store.
Specify a driver package by its unique name or ID.

To add a driver package to a driver group, specify the group name.
Use the Remove-WdsDriverPackage to remove a drive package from a group.

To insert a driver package into a boot image, specify the image name and architecture.
If the image name and architecture do not uniquely identify the boot image, specify the boot image file.
After you insert a driver package into a boot image, Windows Deployment Services cannot remove the driver package.

## EXAMPLES

### Example 1: Add a driver package to a group by using the package ID
```
PS C:\> Add-WdsDriverPackage -Id 32d78628-07fb-4e18-adc4-f0ecf8b41bbe -GroupName "Drivers for Fabrikam Devices"
```

This command adds a driver package to the group named Drivers for Fabrikam Devices.
The command specifies the ID of the driver package.

### Example 2: Add a driver package to a group by using the package name
```
PS C:\>Add-WdsDriverPackage -GroupName "Drivers for Fabrikam Devices" -Name "Fabrikam Device Driver (x64)"
```

This command adds a driver package to the group named Drivers for Fabrikam Devices.
The command specifies Fabrikam Device Driver (x64) as the name of the driver package.

### Example 3: Inject a driver package into a boot image by using the package ID
```
PS C:\>Add-WdsDriverPackage -Architecture X64 -Id 32d78628-07fb-4e18-adc4-f0ecf8b41bbe -ImageName "Contoso general setup (x64)"
```

This command injects the driver package into the boot image named Contoso general setup (x64).
The command specifies the ID of the driver package.

### Example 4: Inject a driver package into a boot image by using the package name
```
PS C:\>Add-WdsDriverPackage -Architecture X64 -ImageName "Contoso general setup (x64)" -Name "Fabrikam Device Driver (x64)"
```

This command injects the driver package into the boot image named Contoso general setup (x64).
The command specifies Fabrikam Device Driver (x64) as the name of the driver package.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the image.
In order to insert a driver into a boot image, you must specify an architecture.
The acceptable values for this parameter are:

- Arm
- Ia64
- X64
- X86

```yaml
Type: Architecture
Parameter Sets: IdIntoBootImageProperties, NameIntoBootImageProperties
Aliases:
Accepted values: X86, Ia64, X64, Arm

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -FileName
Specifies a file name.
This is the file name of the boot image.
Use this parameter to specify the file name for the boot image if the boot image name and architecture do not uniquely identify the image.

```yaml
Type: String
Parameter Sets: IdIntoBootImageProperties, NameIntoBootImageProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies the name of a driver group.
The cmdlet adds the driver package to this group.

```yaml
Type: String
Parameter Sets: IdIntoDriverGroupName, NameIntoDriverGroupName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an ID.
This is the ID of the driver package to add.

```yaml
Type: Guid
Parameter Sets: IdIntoDriverGroupName, IdIntoBootImageProperties
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Specifies the name of an image.
This is the name of the boot image.
If this name is not unique, specify the file name of the boot image by using the *FileName* parameter.

```yaml
Type: String
Parameter Sets: IdIntoBootImageProperties, NameIntoBootImageProperties
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name.
This is the unique name of the driver package.
If this name is not unique, specify the driver package ID, instead, by using the *Id* parameter.

```yaml
Type: String
Parameter Sets: NameIntoBootImageProperties, NameIntoDriverGroupName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsDriverPackage

## NOTES

## RELATED LINKS

[Disable-WdsDriverPackage](./Disable-WdsDriverPackage.md)

[Enable-WdsDriverPackage](./Enable-WdsDriverPackage.md)

[Get-WdsDriverPackage](./Get-WdsDriverPackage.md)

[Import-WdsDriverPackage](./Import-WdsDriverPackage.md)

[Remove-WdsDriverPackage](./Remove-WdsDriverPackage.md)

