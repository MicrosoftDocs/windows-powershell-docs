---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 896C4B21-95AA-4BE0-B8FA-F727222C47AC
manager: dansimp
---

# Set-WssFileHistoryManagementStatus

## SYNOPSIS
Changes the File History managed status of a computer.

## SYNTAX

```
Set-WssFileHistoryManagementStatus [-ComputerName] <String> [-Delete] [-Force] [-UnManage] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssFileHistoryManagementStatus** cmdlet changes the File History managed status of a computer.
Specify the **UnManage** parameter if you do not want the server to manage the client computer that you specify in the **ComputerName** parameter.

## EXAMPLES

### Example 1: Change the File History managed status of a computer
```
PS C:\> Set-WssFileHistoryManagementStatus -ComputerName "Workstation071" -UnManage -Delete
```

This command changes the File History managed status of a client computer named Workstation071 to unmanaged, and deletes the File History Backup folder for the client computer.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cn

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Delete
Indicates that the cmdlet deletes the File History Backup folder for the client computer when you specify the **UnManage** parameter.

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

### -UnManage
Indicates that the server does not manage the File History of the client computer.

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



