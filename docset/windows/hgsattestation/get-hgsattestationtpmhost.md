---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-HgsAttestationTpmHost
ms.assetid: FD4D4869-A010-4CD1-BA57-C75C96287360
---

# Get-HgsAttestationTpmHost

## SYNOPSIS
Gets guarded hosts with TPM 2.0 from the Attestation service HGS.

## SYNTAX

### NameSet (Default)
```
Get-HgsAttestationTpmHost [-Name <String>] [<CommonParameters>]
```

### File
```
Get-HgsAttestationTpmHost -Path <String> [<CommonParameters>]
```

### Console
```
Get-HgsAttestationTpmHost -Xml <XmlDocument> [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsAttestationTpmHost** cmdlet retrieves guarded hosts from the Attestation service in the Host Guardian Service (HGS).
Use this cmdlet for hosts that have trusted platform module (TPM) 2.0 hardware, and that were added by using the **Add-HgsAttestationTpmHost** cmdlet.

## EXAMPLES


## PARAMETERS

### -Name
Specifies the friendly name of the guarded host that this cmdlet gets from the Attestation service.

```yaml
Type: String
Parameter Sets: NameSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the full path of an .xml file for which this cmdlet gets hosts.
Create this file by using the **Get-PlatformIdentifier** cmdlet.
For more information, type `Get-Help Get-PlatformIdentifier`.

```yaml
Type: String
Parameter Sets: File
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Xml
Specifies the full path of an .xml file that contains binary data for which this cmdlet gets hosts.
Create this file by using **Get-PlatformIdentifier**.

```yaml
Type: XmlDocument
Parameter Sets: Console
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String[]
This cmdlet returns an array of strings.

## NOTES

## RELATED LINKS

[Add-HgsAttestationTpmHost](./Add-HgsAttestationTpmHost.md)

[Remove-HgsAttestationTpmHost](./Remove-HgsAttestationTpmHost.md)

