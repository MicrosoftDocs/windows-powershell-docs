---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: DCFAA816-E8C7-4DD0-B324-19F03597DD23
manager: dansimp
---

# Remove-WssComputer

## SYNOPSIS
Removes a client computer identity, backup, and properties from the network.

## SYNTAX

```
Remove-WssComputer [-Computer] <DeviceInfo> [-RemoveBackup] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-WssComputer** cmdlet removes a client computer identity, backup, and properties from the network.
For active clients, the cmdlet removes the computer identity, but does not remove backups, unless you use the **RemoveBackup** parameter to remove associated backups.

An archived client exists only as a backup of a computer that is no longer part of the network.
This cmdlet removes the identity, backup, and properties for an archived client without the **RemoveBackup** parameter.

## EXAMPLES

### Example 1: Remove a computer and backups
```
PS C:\>$DeviceList = Get-WssComputer PS C:\> Remove-WssComputer -Computer $DeviceList[0] -RemoveBackup
```

This example removes a computer identity and any backups from the network.

The first command uses the Get-WssComputer cmdlet to get all **DeviceInfo** objects, and then stores them in the **$DeviceList** variable.

The second command removes a **DeviceInfo** object.
The command uses standard array notation to specify the first element of the **$DeviceList** array as the computer to be removed.
The command includes the **RemoveBackup** parameter.
Therefore, the command removes any backups.

## PARAMETERS

### -Computer
Specifies the **DeviceInfo** object for computer.
To obtain **DeviceInfo** objects, use the Get-WssComputer cmdlet.

```yaml
Type: DeviceInfo
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RemoveBackup
Indicates that the cmdlet removes any backups for the specified computer.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssComputer](./Get-WssComputer.md)

[Get-WssComputer](./Get-WssComputer.md)

