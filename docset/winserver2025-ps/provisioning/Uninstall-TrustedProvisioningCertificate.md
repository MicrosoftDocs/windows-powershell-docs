---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/provisioning/uninstall-trustedprovisioningcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-TrustedProvisioningCertificate
---

# Uninstall-TrustedProvisioningCertificate

## SYNOPSIS
Removes a previously installed provisioning certificate.

## SYNTAX

```
Uninstall-TrustedProvisioningCertificate [-Thumbprint] <String> [-LogsDirectoryPath <String>]
 [-WprpFile <String>] [-ConnectedDevice] [<CommonParameters>]
```

## DESCRIPTION
Removes a previously installed provisioning certificate.

The **Uninstall-TrustedProvisioningCertificate** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1: Uninstall a trusted provisioning certificate
```powershell
PS C:\> Uninstall-TrustedProvisioningCertificate -Thumbprint fedd995b45e633d4ef30fcbc8f3a48b627e9a28b
```

Uninstall a trusted provisioning certificate with the specified thumbprint.

## PARAMETERS

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

### -Thumbprint
Specifies a certificate thumbprint.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
