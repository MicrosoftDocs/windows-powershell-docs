---
external help file: LoggingFc.psm1-help.xml
Module Name: NetworkControllerFc
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkcontrollerfc/disable-networkcontrolleronfailoverclusterlogging?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetworkControllerOnFailoverClusterLogging
---

# Disable-NetworkControllerOnFailoverClusterLogging

## SYNOPSIS

## SYNTAX

### FetchDeviceNames (Default)

```
Disable-NetworkControllerOnFailoverClusterLogging -RestName <String> [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### SupplyDeviceName

```
Disable-NetworkControllerOnFailoverClusterLogging -DeviceName <String> -Type <String>
 [<CommonParameters>]
```

## DESCRIPTION

Disables logging on physical hosts, mux VMs and gateway VMs.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CertificateThumbprint

Specifies the digital public key X.509 certificate of a user account that has permission to perform
this action.

```yaml
Type: System.String
Parameter Sets: FetchDeviceNames
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

A credential to access the Network Controller REST endpoint and the physical host.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: FetchDeviceNames
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName

DeviceName necessary to create remote session.

```yaml
Type: System.String
Parameter Sets: SupplyDeviceName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestName

The DNS name of the REST endpoint.

```yaml
Type: System.String
Parameter Sets: FetchDeviceNames
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Device type.
Valid values: Server, Gateway, or Mux.

```yaml
Type: System.String
Parameter Sets: SupplyDeviceName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
