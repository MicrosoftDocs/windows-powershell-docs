---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: FFB5A209-2F24-4A8A-B42A-807947BCE14C
manager: dansimp
---

# Get-WssFileHistoryManagementStatus

## SYNOPSIS
Gets the File History managed status of a computer.

## SYNTAX

```
Get-WssFileHistoryManagementStatus [-ComputerName] <String>
```

## DESCRIPTION
The **Get-WssFileHistoryManagementStatus** cmdlet gets the File History managed status of a computer.
The cmdlet returns $True if the File History setting of the computer is managed by the server.

## EXAMPLES

### Example 1: Get the File History managed status of a computer
```
PS C:\> Get-WssFileHistoryManagementStatus -ComputerName "Workstation071"
```

This command gets the File History managed status of a computer named Workstation071.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WssFileHistoryManagementStatus](./Set-WssFileHistoryManagementStatus.md)

[Get-WssFileHistoryConfiguration](./Get-WssFileHistoryConfiguration.md)

