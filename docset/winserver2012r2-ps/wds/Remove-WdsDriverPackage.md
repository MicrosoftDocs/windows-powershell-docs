---
external help file: MSFT_WdsDriverPackage_v1.0.cdxml-help.xml
Module Name: WDS
online version: 
schema: 2.0.0
title: Remove-WdsDriverPackage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AF37FA78-C711-4798-BEAA-B2775F5C0BFC
ms.author: v-kaunu
ms.reviewer: brianlic
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

To remove a driver package from all groups and delete if from the driver store, specify the **RemoveFiles** parameter.
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
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
If this name is not unique, specify the driver package ID, instead, by using the **Id** parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

