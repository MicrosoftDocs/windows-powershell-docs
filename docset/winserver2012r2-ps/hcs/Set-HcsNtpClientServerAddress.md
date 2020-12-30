---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-HcsNtpClientServerAddress
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5646FED8-7205-446C-8B53-E72E4ACDA1A9
---

# Set-HcsNtpClientServerAddress

## SYNOPSIS
Sets the NTP URLs for this device.

## SYNTAX

```
Set-HcsNtpClientServerAddress [-Primary <String>] [-Secondary <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsNtpClientServerAddress** cmdlet sets the Network Time Protocol (NTP) URLs for this device.
You can set one primary URL and several optional secondary URLs.

## EXAMPLES

### Example 1: Set primary and secondary NTP servers
```
PS C:\> Set-HcsNtpClientServerAddress -Primary "time.contoso.com" -Secondary "secondary.contoso.com"
Primary                                                     Secondary
-------                                                     ---------
time.contoso.com                                            {secondary.contoso.com}
```

This command sets the primary and secondary NTP servers for your device.

### Example 2: Set primary NTP server
```
PS C:\> Set-HcsNtpClientServerAddress -Primary "time.contoso.com"
Primary                                                     Secondary
-------                                                     ---------
time.contoso.com                                            {secondary.contoso.com}
```

This command sets the primary NTP server for your device.

### Example 3: Set secondary NTP server
```
PS C:\> Set-HcsNtpClientServerAddress -Secondary "secondary.contoso.com"
Primary                                                     Secondary
-------                                                     ---------
time.contoso.com                                            {secondary.contoso.com}
```

This command sets the secondary NTP server for your device.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Primary
Specifies the primary NTP server address.
The device uses this server unless it is not available.
You can change the primary address, but you cannot remove it.

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

### -Secondary
Specifies an array of secondary NTP server addresses.
If the primary NTP server does not respond, the device tries the secondary addresses in order.

If you specify a value for this parameter, this cmdlet replaces the entire list of secondary servers with the array that you specify.
The cmdlet does not append the servers to the current array of secondary servers.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Powershell.Cmdlets.NtpInfo
The NtpInfo object has the following properties:

- String Primary 
- String\[\] Secondary

## NOTES

## RELATED LINKS

[Get-HcsNtpClientServerAddress](./Get-HcsNtpClientServerAddress.md)

