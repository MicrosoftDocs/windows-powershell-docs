---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: DD55D534-9E4C-42E1-B950-054DB4B0A777
manager: dansimp
---

# Disable-WssClientBackup

## SYNOPSIS
Disables client backup for a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-WssClientBackup [-ComputerName] <String> [-Force] [-RemoveBackup] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-WssClientBackup [-ComputerSid] <String> [-Force] [-RemoveBackup] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-WssClientBackup** cmdlet disables client backup for a computer.
Specify a computer by name or security identifier (SID).
Use the **RemoveBackup** parameter to remove existing backups.

This cmdlet prevents client backups from the current time forward.
If you want to stop only a current backup operation, use the Stop-WssClientBackup cmdlet.

## EXAMPLES

### Example 1: Disable client backup for a computer
```
PS C:\> Disable-WssClientBackup -ComputerName "Workstation073" -RemoveBackup
```

This command disables client backups for a computer named Workstation073, and removes any existing backup.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerSid
Specifies the SID of a computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### -RemoveBackup
Indicates that the cmdlet removes the current client backup for the specified computer.

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

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

