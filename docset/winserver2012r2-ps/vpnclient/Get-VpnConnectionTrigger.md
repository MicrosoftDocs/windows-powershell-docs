---
external help file: PS_VpnConnectionTrigger_v1.0.cdxml-help.xml
Module Name: VpnClient
online version: 
schema: 2.0.0
title: Get-VpnConnectionTrigger
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3892FC6B-6E54-4626-BD02-910A766FE9E0
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-VpnConnectionTrigger

## SYNOPSIS
Gets trigger properties of a VPN connection.

## SYNTAX

```
Get-VpnConnectionTrigger [-ConnectionName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VpnConnectionTrigger** cmdlet gets trigger properties of a virtual private network (VPN) connection.

## EXAMPLES

### Example 1: Get trigger properties of a VPN connection
```
PS C:\> Get-VpnConnectionTrigger -ConnectionName "ContosoVPN"
ConnectionName:           Contoso


ApplicationID:            {microsoft.windowsphotos_8wekyb3d8bbwe, C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe}


TrustedNetwork:           {newyork.contoso.com, washington.contoso.com}
```

This command gets the trigger properties of the VPN connection named ContosoVPN.

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

### -ConnectionName
Specifies the name of a VPN connection profile.
To view existing VPN connection profiles, use the Get-VpnConnection cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnConnectionTrigger

## NOTES

## RELATED LINKS

