---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SyncServerSetting.cdxml-help.xml
Module Name: SyncShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/syncshare/get-syncserversetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SyncServerSetting
---

# Get-SyncServerSetting

## SYNOPSIS
Gets the settings of the Sync Share server.

## SYNTAX

```
Get-SyncServerSetting [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SyncServerSetting** cmdlet gets the settings of the Sync Share server.

## EXAMPLES

### Example 1: Get all settings of the Sync Share server
```
PS C:\> Get-SyncServerSetting
AdministratorEmail                :
AuthSetting                       :
AuthType                          : Windows
ChangeDetectionMinIntervalMinutes : 5
DeniedUser                        :
Description                       :
Server                            : Localhost
SSLCertificateEnabled             : False
PSComputerName                    :
```

This command gets all the settings of the Sync Share server.

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

### SyncServerSetting

## NOTES

## RELATED LINKS

[Set-SyncServerSetting](./Set-SyncServerSetting.md)

