---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsclaimsprovidertrustsgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsClaimsProviderTrustsGroup
---

# Add-AdfsClaimsProviderTrustsGroup

## SYNOPSIS
Creates a claims provider trust group based on metadata that contains multiple entities.

## SYNTAX

### MetadataFile
```
Add-AdfsClaimsProviderTrustsGroup -MetadataFile <String> [-Force] [-PassThru]
 [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>] [-MonitoringEnabled <Boolean>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MetadataUrl
```
Add-AdfsClaimsProviderTrustsGroup -MetadataUrl <Uri> [-AutoUpdateEnabled <Boolean>] [-Force] [-PassThru]
 [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>] [-MonitoringEnabled <Boolean>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsClaimsProviderTrustsGroup** cmdlet creates a claims provider trust group based on metadata that contains multiple entities.

## EXAMPLES

### Example 1: Add a trust group by metadata URL
```
PS C:\> Add-AdfsClaimsProviderTrustsGroup -MetadataUrl https://www.contosoconsortium.com/metadata/metadata.xml
```

This command specifies a metadata URL to add a trust group

### Example 2: Add a trust group by metadata file
```
PS C:\> Add-AdfsClaimsProviderTrustsGroup -MetadataFile "C:\metadata.xml"
```

This command specifies a metadata file to add a trust group.

## PARAMETERS

### -AcceptanceTransformRules
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AcceptanceTransformRulesFile
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

### -AutoUpdateEnabled
Indicates whether automatic updates are enabled.

```yaml
Type: Boolean
Parameter Sets: MetadataUrl
Aliases:

Required: False
Position: Named
Default value: None
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

### -MetadataFile
Specifies the file path and name of a metadata file on the local file system.

```yaml
Type: String
Parameter Sets: MetadataFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetadataUrl
Specifies the URL of a metadata file available on the public Internet.

```yaml
Type: Uri
Parameter Sets: MetadataUrl
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringEnabled
Indicates whether monitoring is enabled.

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

[Get-AdfsClaimsProviderTrustsGroup](./Get-AdfsClaimsProviderTrustsGroup.md)

[Remove-AdfsClaimsProviderTrustsGroup](./Remove-AdfsClaimsProviderTrustsGroup.md)

