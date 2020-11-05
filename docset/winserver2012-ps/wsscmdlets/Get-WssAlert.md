---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 3358F893-793E-4493-B998-D49104083E7E
manager: dansimp
---

# Get-WssAlert

## SYNOPSIS
Gets alerts that the server generated.

## SYNTAX

```
Get-WssAlert [-Network]
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-WssAlert](./Enable-WssAlert.md)

[Disable-WssAlert](./Disable-WssAlert.md)

[Clear-WssAlert](./Clear-WssAlert.md)

[Repair-WssAlert](./Repair-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

