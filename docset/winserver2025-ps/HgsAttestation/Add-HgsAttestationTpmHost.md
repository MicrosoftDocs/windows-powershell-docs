---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/add-hgsattestationtpmhost?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HgsAttestationTpmHost
---

# Add-HgsAttestationTpmHost

## SYNOPSIS
Adds a guarded host with TPM 2.0 to the Attestation service in HGS.

## SYNTAX

### File
```
Add-HgsAttestationTpmHost [-Name <String>] [-ForeignKey <String>] [-Force] -Path <String>
 [-PolicyVersion <PolicyVersion>] [-Stage] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Console
```
Add-HgsAttestationTpmHost [-Name <String>] [-ForeignKey <String>] [-Force] -Xml <XmlDocument>
 [-PolicyVersion <PolicyVersion>] [-Stage] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HgsAttestationTpmHost** cmdlet adds a guarded host to the Attestation service in Host Guardian Service (HGS).
To use this cmdlet, this host must have trusted platform module (TPM) 2.0 hardware.

## EXAMPLES

### Example 1: Add a TPM host
```
PS C:\> Add-HgsAttestationTpmHost -Name "TpmHost21" -Path "C:\TpmHost21.xml"
```

This command adds a TPM host to the Attestation service.
This command uses an .xml file that is output of the **Get-PlatformIdentifier** cmdlet.

## PARAMETERS

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

### -ForeignKey
Specifies a foreign key.

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
Specifies the friendly name of the guarded host that this cmdlet adds to the Attestation service.
This host must have TPM 2.0 hardware.

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
Specifies the full path of an .xml file.
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
Specifies the full path of an .xml file that contains binary data.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns a string.

## NOTES

## RELATED LINKS

[Get-HgsAttestationTpmHost](./Get-HgsAttestationTpmHost.md)

[Remove-HgsAttestationTpmHost](./Remove-HgsAttestationTpmHost.md)

