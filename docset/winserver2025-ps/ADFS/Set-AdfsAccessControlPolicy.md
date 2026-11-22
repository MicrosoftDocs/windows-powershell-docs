---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsaccesscontrolpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAccessControlPolicy
---

# Set-AdfsAccessControlPolicy

## SYNOPSIS
Modifies an AD FS access control policy.

## SYNTAX

### IdentifierName
```
Set-AdfsAccessControlPolicy [-Name <String>] [-Identifier <String>] [-Description <String>]
 [-PolicyMetadata <PolicyMetadata>] [-PolicyMetadataFile <String>] [-PassThru] [-TargetName] <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Identifier
```
Set-AdfsAccessControlPolicy [-Name <String>] [-Identifier <String>] [-Description <String>]
 [-PolicyMetadata <PolicyMetadata>] [-PolicyMetadataFile <String>] [-PassThru] [-TargetIdentifier] <String>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsAccessControlPolicy [-Name <String>] [-Identifier <String>] [-Description <String>]
 [-PolicyMetadata <PolicyMetadata>] [-PolicyMetadataFile <String>] [-PassThru]
 [-TargetAccessControlPolicy] <AdfsAccessControlPolicy> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsAccessControlPolicy** cmdlet modifies an Active Directory Federation Services (AD FS) access control policy.

## EXAMPLES

## PARAMETERS

### -Description
Specifies a description for the policy.

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

### -Identifier
Specifies an ID for the policy.

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

### -Name
Specifies a name for the policy.

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

### -PolicyMetadata
Specifies metadata for the policy.

```yaml
Type: PolicyMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyMetadataFile
Specifies the metadata file for the policy.

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

### -TargetAccessControlPolicy
```yaml
Type: AdfsAccessControlPolicy
Parameter Sets: IdentifierObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the ID of the target.

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
Specifies the target name.

```yaml
Type: String
Parameter Sets: IdentifierName
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsAccessControlPolicy](./Get-AdfsAccessControlPolicy.md)

[New-AdfsAccessControlPolicy](./New-AdfsAccessControlPolicy.md)

[Remove-AdfsAccessControlPolicy](./Remove-AdfsAccessControlPolicy.md)

