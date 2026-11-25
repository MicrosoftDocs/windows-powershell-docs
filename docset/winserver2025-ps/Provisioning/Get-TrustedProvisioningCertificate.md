---
description: Lists all installed trusted provisioning certificates; use this cmdlet to get the certificate thumbprint to use with the Uninstall-TrustedProvisioningCertificate cmdlet.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/provisioning/get-trustedprovisioningcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TrustedProvisioningCertificate
---

# Get-TrustedProvisioningCertificate

## SYNOPSIS
Lists all installed trusted provisioning certificates.

## SYNTAX

```
Get-TrustedProvisioningCertificate [[-Thumbprint] <String>] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice] [<CommonParameters>]
```

## DESCRIPTION
Lists all installed trusted provisioning certificates; use this cmdlet to get the certificate thumbprint to use with the `Uninstall-TrustedProvisioningCertificate` cmdlet.

The **Get-TrustedProvisioningCertificate** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1: List installed trusted provisioning certificates
```powershell
PS C:\> Get-TrustedProvisioningCertificate
```
```output
The operation completed successfully.

No certificates found in the trusted provisioners store
```

Lists all installed trusted provisioning certificates.

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
Specifies the thumbprint of the certificate to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 0
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

### None
## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
