---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsclaimdescription?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSClaimDescription

## SYNOPSIS
Sets the properties of an existing claim description.

## SYNTAX

### Name
```
Set-ADFSClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-TargetName] <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Identifier
```
Set-ADFSClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-TargetClaimType] <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-ADFSClaimDescription [-IsAccepted <Boolean>] [-IsOffered <Boolean>] [-IsRequired <Boolean>]
 [-Notes <String>] [-Name <String>] [-ClaimType <String>] [-TargetClaimDescription] <ClaimDescription>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSClaimDescription cmdlet sets properties on an existing AD FS claim description.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADFSClaimDescription -TargetName "Role" -Name "New Role Claim Name"
```

Description

-----------

Sets a new name for the "Role" claim description.

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

### -IsAccepted
Specifies that the claim should be published in federation metadata as a claim that is accepted by the federation service.

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
Specifies that the claim should be published in federation metadata as a claim that is offered by the federation service.

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
Specifies that the claim should be published in federation metadata as a claim that is required by the federation service.

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
Specifies the friendly name of this claim.

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
Specifies any notes for this claim description.

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
Passes an object to the pipeline.
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
Specifies the claim description that will be modified by the cmdlet.
This value is typically taken from the pipeline.

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
Specifies the claim type of the claim description that will be modified by the cmdlet.

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
Specifies the friendly name of the claim description that will be modified by the cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription
A class structure for representing a claim description object for the Federation Service.

## OUTPUTS

### None

## NOTES
* All Set-* cmdlets have a positional parameter (at position 0) with a name that starts with Target*. This parameter defines the search criteria (and the parameter set). For example, Set-ADFSRelyingParty has the parameters TargetName, TargetIdentifierUri, and TargetRelyingParty. You can use only one of these Target* parameters to identify which RelyingParty will be modified. Because these parameters are positional, their name does not have be specified. Therefore, the following commands are identical in effect.

Changes the RelyingParty object whose name is RP1, setting its name to RP2 Set-ADFSRelyingParty -TargetName RP1Name -Name RP2Name  OR Set-ADFSRelyingParty RP1Name -Name RP2Name

## RELATED LINKS

[Add-ADFSClaimDescription](./Add-ADFSClaimDescription.md)

[Get-ADFSClaimDescription](./Get-ADFSClaimDescription.md)

[Remove-ADFSClaimDescription](./Remove-ADFSClaimDescription.md)

