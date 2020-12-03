---
external help file: IpamIpAuditEvent.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Remove-IpamIpAddressAuditEvent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B6206257-6557-42E1-8579-1F9C00D0EA0E
---

# Remove-IpamIpAddressAuditEvent

## SYNOPSIS
Removes IP address audit events from the IPAM database.

## SYNTAX

```
Remove-IpamIpAddressAuditEvent -EndDate <DateTime> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamIpAddressAuditEvent** cmdlet permanently removes all IP address audit events, including the events collected on the date identified by the **EndDate** parameter, from the IP Address Management (IPAM) database.

## EXAMPLES

### Example 1: Remove all event data
```
PS C:\>$Today = Get-DatePS C:\>Remove-IpamIpAuditEvent -EndDate $Today
Confirm

All Event catalog data up to and including the date selected by you will be deleted permanently. Do you want to

continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes all IP address audit event data prior to today.

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

### -EndDate
Specifies the end date, in YYYY/MM/DD.hh:mm:ss format, for which to delete the event data.
The cmdlet deletes all event data up to, and including, this date.
The value cannot be the same as the current date.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### IpamIpAuditEvent
Represents an IP address audit event in IPAM

## NOTES

## RELATED LINKS

[Get-IpamIpAddressAuditEvent](./Get-IpamIpAddressAuditEvent.md)

