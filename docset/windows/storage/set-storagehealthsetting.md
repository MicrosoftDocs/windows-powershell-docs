---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-StorageHealthSetting
ms.reviewer:
ms.assetid: 64E07C9C-77E9-470C-8E42-51AA151911DE
---

# Set-StorageHealthSetting

## SYNOPSIS
Modifies a storage health service setting.

## SYNTAX

```
Set-StorageHealthSetting -InputObject <CimInstance> -Name <String> -Value <String> [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageHealthSetting** cmdlet modifies a setting to the current storage health service for the specified storage subsystem.
If the setting doesn't exist, it creates it.

## EXAMPLES

### Example 1:Set Storage Health Setting on Storage subsystem
```
PS C:\>$StorageSubSystem | Get-StorageHealthSetting -Name "System.Storage.PhysicalDisk.AutoPool.BaseName"
PS C:\> $StorageSubSystem | Set-StorageHealthSetting -Name "System.Storage.PhysicalDisk.AutoPool.BaseName" -Value "S2D on Contoso-C1"
PS C:\> $StorageSubSystem | Get-StorageHealthSetting -Name "System.Storage.PhysicalDisk.AutoPool.BaseName"

Name                                          Value             PSComputerName
----                                          -----             --------------
System.Storage.PhysicalDisk.AutoPool.BaseName S2D on Contoso-C1
```

This example sets the Storage Health Setting named System.Storage.PhysicalDisk.AutoPool.BaseName to a new value.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the input object that is used in a pipeline command.

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
Specifies the name of the Storage health setting to set.

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

### -Value
Specifies the value for a storage health setting.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-StorageHealthSetting](./Get-StorageHealthSetting.md)

[Remove-StorageHealthSetting](./Remove-StorageHealthSetting.md)

