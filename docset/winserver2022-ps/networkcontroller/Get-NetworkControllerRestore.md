---
description: 
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 09/27/2021
online version: https://docs.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerrestore?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerRestore
---

# Get-NetworkControllerRestore

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Get-NetworkControllerRestore [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1: Get the restore object
```powershell
Get-NetworkControllerRestore -ConnectionUri  https://networkcontroller
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

### -ResourceId
{{ Fill ResourceId Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

### System.Object#https://localhost/

## NOTES

## RELATED LINKS

[New-NetworkControllerRestore](New-NetworkControllerRestore.md)

[Remove-NetworkControllerRestore](Remove-NetworkControllerRestore.md)
