---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: A4145239-080D-48A1-81E1-F574440CCB67
ms.manager: dansimp
---

# Get-OBFileSpec

## SYNOPSIS
Gets the list of OBFileSpec objects associated with the specified backup policy (OBPolicy object).

## SYNTAX

```
Get-OBFileSpec [-Policy] <CBPolicy>
```

## DESCRIPTION
The **Get-OBFileSpec** cmdlet gets the list of OBFileSpec\[\] objects associated with the specified backup policy (OBPolicy object).
The OBFileSpec\[\] objects define what items will be included or excluded from backups created using the backup policy.
Use the New-OBFileSpec and Add-OBFileSpec cmdlets to define and apply changes to the backup policy.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBPolicy | Get-OBFileSpec
```

This example gets the file specification for a given policy.

## PARAMETERS

### -Policy
Specify the policy from which to obtain the list of file specifications.

```yaml
Type: CBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBFileSpec[]

## NOTES

## RELATED LINKS

[Add-OBFileSpec](./Add-OBFileSpec.md)

[Get-OBPolicy](./Get-OBPolicy.md)

[New-OBFileSpec](./New-OBFileSpec.md)

