---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 26FEDD30-5883-40FF-9383-082E38113C67
manager: dansimp
---

# Remove-WssComputerAccess

## SYNOPSIS
Removes a relationship between a user and a computer for Remote Web Access.

## SYNTAX

```
Remove-WssComputerAccess -ComputerName <String> -UserName <String>
```

## DESCRIPTION
The **Remove-WssComputerAccess** cmdlet removes a relationship between a user account and a computer used for Remote Web Access.
After you remove the relationship, a user cannot access a computer by means of Remote Web Access.
You can use the Add-WssComputerAccess cmdlet to create a relationship for use with Remote Web Access.

## EXAMPLES

### Example 1: Remove computer access for a user
```
PS C:\> Remove-WssComputerAccess -ComputerName "Workstation033" -UserName "SarahJones"
```

This command deletes a relationship between the user SarahJones and the computer named Workstation033.
The user can no longer use Remote Web Access to connect to this computer.

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

[Add-WssComputerAccess](./Add-WssComputerAccess.md)

