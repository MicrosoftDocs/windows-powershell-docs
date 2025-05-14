---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsclaimdescription?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsClaimDescription
---

# Set-AdfsClaimDescription

## SYNOPSIS
Modifies the properties of a claim description.

## SYNTAX

### Name
```
Set-AdfsClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-ShortName <String>] [-TargetName] <String>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShortName
```
Set-AdfsClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-ShortName <String>] [-TargetShortName] <String>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Set-AdfsClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-ShortName <String>] [-TargetClaimType] <String>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-AdfsClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-ShortName <String>]
 [-TargetClaimDescription] <ClaimDescription> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsClaimDescription** cmdlet modifies properties on a Active Directory Federation Services (AD FS) claim description.

## EXAMPLES

### Example 1: Change the name of a claim description
```
PS C:\> Set-AdfsClaimDescription -TargetName "Role" -Name "RoleDesc"
```

This command changes the name of the claim description named Role to RoleDesc.

## PARAMETERS

### -ClaimType
Specifies the claim type URI of the claim.

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

### -IsAccepted
Indicates whether the claim is published in federation metadata as a claim that is accepted by the Federation Service.

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
Indicates whether the claim is published in federation metadata as a claim that is offered by the Federation Service.

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
Indicates whether the claim is published in federation metadata as a claim that is required by the Federation Service.

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
Specifies the friendly name of the claim to modify.

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
Specifies the unique short name identifier for the claim description that is used for issuing and consuming JWT tokens.

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

### -TargetClaimDescription
Specifies a **ClaimDescription** object.
The cmdlet modifies the **ClaimDescription** object that you specify.
To obtain a claim description, use the **Get-AdfsClaimDescription** cmdlet.

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
Specifies the claim type of the claim description to modify.

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
Specifies the friendly name of the claim description to modify.

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
Specifies the short name identifier that AD FS uses to lookup an existing claim description.

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

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription

A ClaimDescription object is received by the *TargetClaimDescription* parameter.

### System.String

String objects are received by the *TargetClaimType*, *TargetName*, and *TargetShortName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription

Returns the updated ClaimDescription object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* All Set-* cmdlets have a positional parameter (at position 0) with a name that starts with Target*. This parameter defines the search criteria, and the parameter set. For example, **Set-ADFSRelyingParty** has the parameters *TargetName*, *TargetIdentifierUri*, and *TargetRelyingParty*. You can use only one of these *Target** parameters to identify which RelyingParty to modify. Because these parameters are positional, you do not have to specify their name. Therefore, the following commands are identical in effect. The commands change the RelyingParty object named RP1 to RP2.

- `Set-ADFSRelyingParty -TargetName RP1Name -Name RP2Name`
- `Set-ADFSRelyingParty RP1Name -Name RP2Name`

## RELATED LINKS

[Add-AdfsClaimDescription](./Add-AdfsClaimDescription.md)

[Get-AdfsClaimDescription](./Get-AdfsClaimDescription.md)

[Remove-AdfsClaimDescription](./Remove-AdfsClaimDescription.md)

