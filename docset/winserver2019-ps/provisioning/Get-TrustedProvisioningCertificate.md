---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://docs.microsoft.com/powershell/module/provisioning/get-trustedprovisioningcertificate?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TrustedProvisioningCertificate
---

# Get-TrustedProvisioningCertificate

## SYNOPSIS
Lists all installed trusted provisioning certificates.

## SYNTAX

```
Get-TrustedProvisioningCertificate [[-Thumbprint] <String>] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

## DESCRIPTION
Lists all installed trusted provisioning certificates; use this cmdlet to get the certificate thumbprint to use with the `Uninstall-TrustedProvisioningCertificate` cmdlet.

## EXAMPLES

### Example 1: List installed trusted provisioning certificates
```powershell
PS C:\> Get-TrustedProvisioningCertificate
```
```output
The operation completed successfully.

No certificates found in the trusted provisioners store
```

List all installed trusted provisioning certificates.

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

## INPUTS

### None


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

