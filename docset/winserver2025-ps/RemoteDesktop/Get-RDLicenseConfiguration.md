---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdlicenseconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDLicenseConfiguration
---

# Get-RDLicenseConfiguration

## SYNOPSIS
Retrieves the current settings for the RD Licensing server and the licensing mode of the Remote Desktop deployment.

## SYNTAX

```
Get-RDLicenseConfiguration [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDLicenseConfiguration** cmdlet retrieves the current settings for the Remote Desktop Licensing (RD Licensing) server and the licensing mode of the Remote Desktop deployment.

RD Licensing servers manage the Remote Desktop Services client access licenses (RDS CALs) that each device or user requires to connect to a Remote Desktop Session Host (RD Session Host) server.

## EXAMPLES

### Example 1: Get the Remote Desktop license configuration
```
PS C:\> Get-RDLicenseConfiguration -ConnectionBroker "Rdcb.Contoso.com"
```

This command gets the Remote Desktop license configuration for the RD Connection Broker server named Rdcb.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
- Mode (string). Remote Desktop licensing mode that you configured for the deployment. Valid values are PerUser and PerDevice.
- LicenseServer (string\[\]). FQDN of the Remote Desktop license server that you configured for the deployment.

## NOTES

## RELATED LINKS

[Set-RDLicenseConfiguration](./Set-RDLicenseConfiguration.md)

