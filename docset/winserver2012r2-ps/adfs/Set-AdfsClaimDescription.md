---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Set-AdfsClaimDescription
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B0582590-F312-4959-88B2-7EF66A7383A6
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

This command changes the name of the  claim description named Role to RoleDesc.

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
Indicates whether the claim is published in federation metadata as a claim that is accepted by the federation service.

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
Indicates whether the claim is published in federation metadata as a claim that is offered by the federation service.

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
Indicates whether the claim is published in federation metadata as a claim that is required by the federation service.

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
{{Fill ShortName Description}}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription
A class structure for representing a claim description object for the Federation Service.

## OUTPUTS

### None

## NOTES
* All Set-* cmdlets have a positional parameter (at position 0) with a name that starts with Target*. This parameter defines the search criteria, and the parameter set. For example, **Set-ADFSRelyingParty** has the parameters **TargetName**, **TargetIdentifierUri**, and **TargetRelyingParty**. You can use only one of these Target* parameters to identify which RelyingParty to modify. Because these parameters are positional, you do not have to specify their name. Therefore, the following commands are identical in effect. The commands change the RelyingParty object named RP1 to RP2

Set-ADFSRelyingParty -TargetName RP1Name -Name RP2Name
Set-ADFSRelyingParty RP1Name -Name RP2Name

## RELATED LINKS

[Add-AdfsClaimDescription](./Add-AdfsClaimDescription.md)

[Get-AdfsClaimDescription](./Get-AdfsClaimDescription.md)

[Remove-AdfsClaimDescription](./Remove-AdfsClaimDescription.md)

