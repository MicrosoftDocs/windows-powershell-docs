---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: CC660DCC-301B-434F-AB10-BD4203A38FC7
manager: dansimp
---

# Add-WssComputerAccess

## SYNOPSIS
Creates a relationship between a user and a computer for Remote Web Access.

## SYNTAX

```
Add-WssComputerAccess -ComputerName <String> -UserName <String>
```

## DESCRIPTION
The **Add-WssComputerAccess** cmdlet creates a relationship between a user account and a computer to use for Remote Web Access.
You can use the Remove-WssComputerAccess cmdlet to delete an access relationship.

## EXAMPLES

### Example 1: Add computer access for a user
```
PS C:\> Add-WssComputerAccess -ComputerName "Workstation033" -UserName "SarahJones"
```

This command creates a relationship between the user SarahJones and the computer named Workstation033.
The user can now use Remote Web Access to connect to this computer.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user name of an account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WssComputerAccess](./Remove-WssComputerAccess.md)

