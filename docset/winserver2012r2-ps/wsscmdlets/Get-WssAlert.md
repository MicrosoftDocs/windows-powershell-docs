---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssalert?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssAlert
---

# Get-WssAlert

## SYNOPSIS
Gets alerts that the server generated.

## SYNTAX

```
Get-WssAlert [-Network] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssAlert** cmdlet gets alerts that the server generated for issues that relate to computer backups, server storage, low disk space, files system, and hard drives.
Specify the **Network** parameter to get the alerts that the server generates for the local computer and the computers in your network that the server monitors.

## EXAMPLES

### Example 1: Get alerts
```
PS C:\> Get-WssAlert
```

This command gets alerts that the server generated.

## PARAMETERS

### -Network
Indicates that the cmdlet gets alerts for all computers in the home network.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.IEnumerable<Microsoft.WindowsServerSolutions.NetworkHealth.AlertFramework.Alert
This cmdlet returns a collection of alert objects.

## NOTES

## RELATED LINKS

[Enable-WssAlert](./Enable-WssAlert.md)

[Disable-WssAlert](./Disable-WssAlert.md)

[Clear-WssAlert](./Clear-WssAlert.md)

[Repair-WssAlert](./Repair-WssAlert.md)

