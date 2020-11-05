---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 75A3AEAA-728D-4832-8781-78558CE933EA
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-ADFSClaimDescription

## SYNOPSIS
Adds a claim description to the Federation Service.

## SYNTAX

```
Add-ADFSClaimDescription -Name <String> -ClaimType <String> [-IsAccepted <Boolean>] [-IsOffered <Boolean>]
 [-IsRequired <Boolean>] [-Notes <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Add-ADFSClaimDescription cmdlet adds a claim description to the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADFSClaimDescription -name "Role" -ClaimType "https://fabrikam.com/role"
```

Description

-----------

Adds a new claim description for a custom Role claim.

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
Default value: False
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
Specifies that the claim should be published in federation metadata as a claim that the Federation Service accepts.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsOffered
Specifies that the claim should be published in federation metadata as a claim that the Federation Service offers.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsRequired
Specifies that the claim should be published in federation metadata as a claim that the Federation Service requires.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of this claim.

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

### None

## OUTPUTS

### None

## NOTES
* You can use claim descriptions to configure the list of claims that are available to be offered or accepted by AD FS 2.0.

## RELATED LINKS

[Get-ADFSClaimDescription](./Get-ADFSClaimDescription.md)

[Remove-ADFSClaimDescription](./Remove-ADFSClaimDescription.md)

[Set-ADFSClaimDescription](./Set-ADFSClaimDescription.md)

