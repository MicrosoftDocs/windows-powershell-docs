---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsclaimdescription?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsClaimDescription
---

# Add-AdfsClaimDescription

## SYNOPSIS
Adds a claim description to the Federation Service.

## SYNTAX

```
Add-AdfsClaimDescription -Name <String> -ClaimType <String> [-ShortName <String>] [-IsAccepted <Boolean>]
 [-IsOffered <Boolean>] [-IsRequired <Boolean>] [-Notes <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsClaimDescription** cmdlet adds a claim description to the Federation Service.

## EXAMPLES

### Example 1: Add a claim description
```
PS C:\> Add-AdfsClaimDescription -Name "Role" -ClaimType "https://Fabrikam.com/role"
```

This command adds the claim description named Role for a custom claim that has the specified claim type.

## PARAMETERS

### -ClaimType
Specifies the claim type URN or URI of the claim.
All claim descriptions must include a valid URN or URI.

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

### -IsAccepted
Indicates whether the claim is published in federation metadata as a claim that the Federation Service accepts.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsOffered
Indicates whether the claim is published in federation metadata as a claim that the Federation Service offers.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsRequired
Indicates whether the claim is published in federation metadata as a claim that the Federation Service requires.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a friendly name for the claim description to add.

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

### -Notes
Specifies text that describes the purpose of the claim description.
The cmdlet adds the notes to the claim description.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### -ShortName
Specifies a short name.

```yaml
Type: String
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
Aliases: cf

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
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.ClaimDescription

Returns the new ClaimDescription object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* Use claim descriptions to configure the list of claims that are available to be offered or accepted by Active Directory Federation Services (AD FS).

## RELATED LINKS

[Get-AdfsClaimDescription](./Get-AdfsClaimDescription.md)

[Remove-AdfsClaimDescription](./Remove-AdfsClaimDescription.md)

[Set-AdfsClaimDescription](./Set-AdfsClaimDescription.md)

