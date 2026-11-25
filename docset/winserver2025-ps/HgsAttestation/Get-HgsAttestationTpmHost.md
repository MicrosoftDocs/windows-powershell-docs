---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/get-hgsattestationtpmhost?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HgsAttestationTpmHost
---

# Get-HgsAttestationTpmHost

## SYNOPSIS
Gets guarded hosts with TPM 2.0 from the Attestation service HGS.

## SYNTAX

### NameSet (Default)
```
Get-HgsAttestationTpmHost [-Name <String>] [-PolicyVersion <PolicyVersion>] [-Stage] [<CommonParameters>]
```

### File
```
Get-HgsAttestationTpmHost [-Name <String>] -Path <String> [-PolicyVersion <PolicyVersion>] [-Stage]
 [<CommonParameters>]
```

### Console
```
Get-HgsAttestationTpmHost [-Name <String>] -Xml <XmlDocument> [-PolicyVersion <PolicyVersion>] [-Stage]
 [<CommonParameters>]
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
Parameter Sets: (All)
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

### -PolicyVersion
Reserved for future use.

```yaml
Type: PolicyVersion
Parameter Sets: (All)
Aliases:
Accepted values: None, PolicyVersion1503, PolicyVersion1704

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stage
Reserved for future use.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String[]
This cmdlet returns an array of strings.

## NOTES

## RELATED LINKS

[Add-HgsAttestationTpmHost](./Add-HgsAttestationTpmHost.md)

[Remove-HgsAttestationTpmHost](./Remove-HgsAttestationTpmHost.md)

