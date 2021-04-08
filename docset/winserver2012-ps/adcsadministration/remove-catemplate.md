---
author: Kateyanne
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
manager: dansimp
Module Name: adcsadministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adcsadministration/remove-catemplate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-CATemplate

## SYNOPSIS
Removes the templates from the certification authority (CA) which were set for issuance of certificates.

## SYNTAX

### Default (Default)
```
Remove-CATemplate [-Name] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllTemplates
```
Remove-CATemplate [-AllTemplates] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-CATemplate cmdlet removes the templates from the certification authority (CA) which were set for issuance of certificates.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-CATemplate -AllTemplates
```

Description

-----------

All the templates on the CA set for certificates issuance are removed.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-CATemplate -Name "EFS"
```

Description

-----------

The template named "EFS" on the CA that is set for certificate issuance is removed.

## PARAMETERS

### -AllTemplates
Removes all certificate templates on the CA that are available for certificate issuance.
A common task administrative task is to remove all the default templates that are currently added for issuance.
This allows the administrator to add only the templates that should be available for certificate issuance in the given scenario.

```yaml
Type: SwitchParameter
Parameter Sets: AllTemplates
Aliases: 

Required: True
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

### -Force
Forces the command to run without asking for user confirmation.

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

### -Name
Removes an individual certificate template from the CA that is available for certificate issuance.
Be sure to use the certificate template name and not the certificate template display name.
For example, the certificate template display name of Basic EFS is assigned the template name EFS.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.String

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-CATemplate](./Add-CATemplate.md)

[Get-CATemplate](./Get-CATemplate.md)

