---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/remove-adfsclaimdescription?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsClaimDescription
---

# Remove-AdfsClaimDescription

## SYNOPSIS
Removes a claim description from the Federation Service.

## SYNTAX

### Name
```
Remove-AdfsClaimDescription [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShortName
```
Remove-AdfsClaimDescription [-TargetShortName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Remove-AdfsClaimDescription [-TargetClaimType] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-AdfsClaimDescription [-TargetClaimDescription] <ClaimDescription> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsClaimDescription** cmdlet removes a claim description from the Federation Service.

## EXAMPLES

### Example 1: Remove a claim description
```
PS C:\> Remove-AdfsClaimDescription -TargetName "Role"
```

This command removes the claim description named Role.

## PARAMETERS

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -TargetClaimDescription
Specifies a **ClaimDescription** object.
The cmdlet removes the **ClaimDescription** object that you specify.
To obtain a claim description, use the Get-AdfsClaimDescription cmdlet.

```yaml
Type: ClaimDescription
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetClaimType
Specifies the claim type of the claim description to remove.

```yaml
Type: String
Parameter Sets: Identifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the claim description to remove.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetShortName
{{Fill TargetShortName Description}}

```yaml
Type: String
Parameter Sets: ShortName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription
A class structure that represents a claim description object for the Federation Service.

## OUTPUTS

### None

## NOTES
* Use claim descriptions to configure the list of claims that are available to be offered or accepted by the Active Directory Federation Services (AD FS) 2.0.

## RELATED LINKS

[Add-AdfsClaimDescription](./Add-AdfsClaimDescription.md)

[Get-AdfsClaimDescription](./Get-AdfsClaimDescription.md)

[Set-AdfsClaimDescription](./Set-AdfsClaimDescription.md)

