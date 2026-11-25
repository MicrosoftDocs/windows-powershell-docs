---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdlicenseconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDLicenseConfiguration
---

# Set-RDLicenseConfiguration

## SYNOPSIS
Defines settings for the RD Licensing server and the licensing mode of the Remote Desktop deployment.

## SYNTAX

### ModePS (Default)
```
Set-RDLicenseConfiguration -Mode <LicensingMode> [-Force] [-ConnectionBroker <String>] [<CommonParameters>]
```

### BothPS
```
Set-RDLicenseConfiguration -Mode <LicensingMode> -LicenseServer <String[]> [-Force]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### LicenseServerPS
```
Set-RDLicenseConfiguration -LicenseServer <String[]> [-Force] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDLicenseConfiguration** cmdlet defines settings for the Remote Desktop Licensing (RD Licensing) server and the licensing mode of the Remote Desktop deployment.

RD Licensing manages the Remote Desktop Services client access licenses (RDS CALs) that each device or user requires to connect to a Remote Desktop Session Host (RD Session Host) server.

## EXAMPLES

### Example 1: Set the Remote Desktop license configuration
```
PS C:\> Set-RDLicenseConfiguration -LicenseServer @("Rdl-1.Contoso.com","Rdl-2.Contoso.com") -ConnectionBroker "Rdcb.Contoso.com"
```

This command sets the Remote Desktop license configuration with the servers named Rdl1-Contoso.com and Rdl-2.Contoso.com and the RD Connection Broker server named Rdcb.Contoso.com.

### Example 2: Set the Remote Desktop license configuration in PerUser mode
```
PS C:\> Set-RDLicenseConfiguration -LicenseServer @("Rdl-1.Contoso.com","Rdl-2.Contoso.com") -Mode PerUser -ConnectionBroker "Rdcb.Contoso.com"
```

This command sets the Remote Desktop license configuration in PerUser mode with the servers named Rdl-1.Contoso.com and Rdl-2.Contoso.com and the RD Connection Broker server named Rdcb.Contoso.com.

### Example 3: Set the Remote Desktop license configuration in PerDevice mode
```
PS C:\> Set-RDLicenseConfiguration -Mode PerDevice -ConnectionBroker "Rdcb.Contoso.com"
```

This command sets the Remote Desktop license configuration in PerDevice mode for the RD Connection Broker server named Rdcb.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local host.

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

### -LicenseServer
Specifies the FQDN of the RD Licensing server to configure.

```yaml
Type: String[]
Parameter Sets: BothPS, LicenseServerPS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Specifies the licensing mode to configure for the deployment.
Valid values are PerUser, PerDevice, and NotConfigured.

```yaml
Type: LicensingMode
Parameter Sets: ModePS, BothPS
Aliases:
Accepted values: PerDevice, PerUser, NotConfigured

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDLicenseConfiguration](./Get-RDLicenseConfiguration.md)

