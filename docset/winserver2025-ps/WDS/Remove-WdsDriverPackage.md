---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsDriverPackage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/remove-wdsdriverpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WdsDriverPackage
---

# Remove-WdsDriverPackage

## SYNOPSIS
Removes a driver package from a driver group or removes it from all driver groups and deletes it.

## SYNTAX

### StoreById
```
Remove-WdsDriverPackage -Id <Guid> [-RemoveFiles] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### GroupById
```
Remove-WdsDriverPackage -Id <Guid> -GroupName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### GroupByName
```
Remove-WdsDriverPackage -GroupName <String> -Name <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### StoreByName
```
Remove-WdsDriverPackage -Name <String> [-RemoveFiles] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WdsDriverPackage** cmdlet removes a driver package from a driver group or removes a driver package from all driver groups and deletes it from the Windows Deployment Services driver store.
Specify a driver package by its unique name or ID.

To remove a driver package from a driver group, specify the name of the group.
A client must have access to at least one group that a driver package belongs to in order to install it.

To remove a driver package from all groups and delete if from the driver store, specify the *RemoveFiles* parameter.
Use the Import-WdsDriverPackage cmdlet to import drivers into the driver store.

## EXAMPLES

### Example 1: Remove a driver package from a group by using the package ID
```
PS C:\> Remove-WdsDriverPackage -GroupName "Drivers for Fabrikam Devices" -Id 32d78628-07fb-4e18-adc4-f0ecf8b41bbe
```

This command removes the driver package that has the specified ID from the group named Drivers for Fabrikam Devices.

### Example 2: Remove a named driver package from a group
```
PS C:\>Remove-WdsDriverPackage -GroupName "Drivers for Fabrikam Devices" -Name "Fabrikam Device Driver (x64)"
```

This command removes the driver package named Fabrikam Device Driver (x64) from the group named Drivers for Fabrikam Devices.

### Example 3: Remove a driver package from all groups by using the package ID
```
PS C:\>Remove-WdsDriverPackage -Id 32d78628-07fb-4e18-adc4-f0ecf8b41bbe -RemoveFiles
```

This command removes the driver package that has the specified ID from all groups and deletes it from the driver store.

### Example 4: Remove a named driver package from all groups
```
PS C:\>Remove-WdsDriverPackage -Name "Fabrikam Device Driver (x64)" -RemoveFiles
```

This command removes the driver package named Fabrikam Device Driver (x64) from all groups and deletes it from the driver store.

## PARAMETERS

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

### -GroupName
Specifies the name of a driver group.
The cmdlet removes the driver package from this group.

```yaml
Type: String
Parameter Sets: GroupById, GroupByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an ID.
This is the ID of the driver package to remove.

```yaml
Type: Guid
Parameter Sets: StoreById, GroupById
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
Parameter Sets: GroupByName, StoreByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveFiles
Indicates that this cmdlet removes the driver package from all driver groups and deletes it from the store.

```yaml
Type: SwitchParameter
Parameter Sets: StoreById, StoreByName
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

[Add-WdsDriverPackage](./Add-WdsDriverPackage.md)

[Disable-WdsDriverPackage](./Disable-WdsDriverPackage.md)

[Enable-WdsDriverPackage](./Enable-WdsDriverPackage.md)

[Get-WdsDriverPackage](./Get-WdsDriverPackage.md)

[Import-WdsDriverPackage](./Import-WdsDriverPackage.md)

