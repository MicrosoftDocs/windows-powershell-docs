---
description: 
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 09/27/2021
online version: https://docs.microsoft.com/powershell/module/networkcontroller/invoke-networkcontrollersubnetegressreset?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-NetworkControllerSubnetEgressReset
---

# Invoke-NetworkControllerSubnetEgressReset

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Invoke-NetworkControllerSubnetEgressReset [[-Tags] <PSObject>] [-Properties] <SubnetEgressResetProperties>
 [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [[-ResourceId] <String>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CertificateThumbprint
{{ Fill CertificateThumbprint Description }}

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

### -ConnectionUri
{{ Fill ConnectionUri Description }}

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
{{ Fill Credential Description }}

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Etag
{{ Fill Etag Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{ Fill Force Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException
{{ Fill PassInnerException Description }}

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

### -Properties
{{ Fill Properties Description }}

```yaml
Type: SubnetEgressResetProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
{{ Fill ResourceId Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceMetadata
{{ Fill ResourceMetadata Description }}

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
{{ Fill Tags Description }}

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.NetworkController.SubnetEgressResetProperties

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-NetworkControllerSubnetEgressReset](Get-NetworkControllerSubnetEgressReset.md)
