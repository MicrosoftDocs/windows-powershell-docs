---
author: brianlic-msft
description: 
external help file: StorageScripts-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-StorageHealthSetting
ms.assetid: E0C4854A-F19E-40D9-A098-6BCE4AFCD169
---

# Remove-StorageHealthSetting

## SYNOPSIS
Removes a storage health service setting.

## SYNTAX

```
Remove-StorageHealthSetting -InputObject <CimInstance> -Name <String> [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-StorageHealthSetting** cmdlet removes a storage health service setting for a specified Storage subsystem.

## EXAMPLES

### Example 1: Remove a Storage Health Setting
```
PS C:\>$StorageSubSystem | Get-StorageHealthSetting -Name "System.Storage.PhysicalDisk.AutoPool.BaseName"

Name                                          Value               PSComputerName
----                                          -----               --------------
System.Storage.PhysicalDisk.AutoPool.BaseName S2D on Contoso-C1



PS C:\>$StorageSubSystem | Remove-StorageHealthSetting -Name "System.Storage.PhysicalDisk.AutoPool.BaseName"
PS C:\> $StorageSubSystem | Get-StorageHealthSetting -Name "System.Storage.PhysicalDisk.AutoPool.BaseName"
```

This example removes the existing Storage Health Setting named System.Storage.PhysicalDisk.AutoPool.BaseName from the system.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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
Type: CimSession
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{Fill InputObject Description}}

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage health service setting to remove.

```yaml
Type: String
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Get-StorageHealthSetting](./Get-StorageHealthSetting.md)

[Set-StorageHealthSetting](./Set-StorageHealthSetting.md)

