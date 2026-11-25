---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/provisioning/install-trustedprovisioningcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-TrustedProvisioningCertificate
---

# Install-TrustedProvisioningCertificate

## SYNOPSIS
Adds a certificate to the Trusted Certificate Store.

## SYNTAX

```
Install-TrustedProvisioningCertificate [-CertificatePath] <String> [-ForceInstall]
 [-LogsDirectoryPath <String>] [-WprpFile <String>] [-ConnectedDevice] [<CommonParameters>]
```

## DESCRIPTION
Installs the specified certificate to the Trusted Certificate Store.

The **Install-TrustedProvisioningCertificate** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1: Install Trusted Provisioning Certificate
```powershell
PS C:\> Install-TrustedProvisioningCertificate -CertificatePath trustedCert.cer
```

Installs the specified certificate as a trusted provisioning certificate.

## PARAMETERS

### -CertificatePath
Path to .CER file

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConnectedDevice
If enabled, specifies that the device type is mobile.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Device

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceInstall
Specifies whether, if certificate already exists, it will be overwritten.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Force

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogsDirectoryPath
Specifies the logs directory path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Logs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WprpFile
Specifies the location of the WPR profile file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Wprp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
