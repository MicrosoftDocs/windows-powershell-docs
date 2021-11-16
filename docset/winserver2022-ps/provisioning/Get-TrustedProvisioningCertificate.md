---
description: The Get-TrustedProvisioningCertificate cmdlet gets a trusted provisioning certificate from the Trusted Certificate Store.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://docs.microsoft.com/powershell/module/provisioning/get-trustedprovisioningcertificate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TrustedProvisioningCertificate
---

# Get-TrustedProvisioningCertificate

## SYNOPSIS
Gets the specified certificate from the Trusted Certificate Store.

## SYNTAX

```
Get-TrustedProvisioningCertificate [[-Thumbprint] <String>] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice] [<CommonParameters>]
```

## DESCRIPTION
The **Get-TrustedProvisioningCertificate** cmdlet gets a trusted provisioning certificate from the Trusted Certificate Store.

## EXAMPLES

### Example 1: Get a certificate
```
Get-TrustedProvisioningCertificate -Thumbprint fedd995b45e633d4ef30fcbc8f3a48b627e9a28b
```

This example gets the trusted provisioning certificate with the specified thumbprint.

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
