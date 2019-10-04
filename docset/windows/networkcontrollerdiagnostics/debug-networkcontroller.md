---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Debug-NetworkController-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Debug-NetworkController
ms.reviewer:
ms.assetid: 9A1D7CE0-77AC-4E62-BAA7-B24021EA0C73
---

# Debug-NetworkController

## SYNOPSIS
Queries a Network Controller for detailed diagnostic information.

## SYNTAX

```
Debug-NetworkController [-NetworkController] <String> [-SetupDiagnostics] [[-IncludeTraces] <Boolean>]
 [[-OutputDirectory] <String>] [[-Credential] <PSCredential>] [[-RestURI] <String>]
 [[-CertificateThumbprint] <String>] [[-DeviceCredentials] <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION
The **Debug-NetworkController** cmdlet queries a Network Controller for detailed diagnostic information.

You can run this cmdlet from a computer that has Layer-3 connectivity to the Representational State Transfer (REST) IP address of the Network Controller.
The computer must have the Network Controller REST certificate installed.

## EXAMPLES

### Example 1: Set up logging on nodes and hosts
```
PS C:\>Debug-NetworkController -NetworkController "NC-0.contoso.cloud.com" -SetupDiagnostics
```

This command sets up logging on all Network Controller nodes and hosts.

### Example 2: Collect diagnostics data and logs from all nodes and hosts
```
PS C:\>$Credential = Get-Credential
PS C:\> Debug-NetworkController -NetworkController "NC-0.contoso.cloud.com" -Credential $Credential -OutputDirectory "C:\DiagnosticsData"
```

The first command creates credentials by using the Get-Credential cmdlet, and then stores it in the $Credential variable.
The command prompts you for user name and password.

The second command collects diagnostics data and logs from all Network Controller nodes and hosts.

### Example 3: Collect diagnostics data only
```
PS C:\>$Credential = Get-Credential
PS C:\> Debug-NetworkController -NetworkController "NC-0.contoso.cloud.com" -Credential $Credential -OutputDirectory C:\DiagnosticsData -IncludeTraces:$False
```

The first command creates credentials, and then stores it in the $Credential variable.

The second command collects diagnostics data only.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint to use for the Network Controller.
Specify this parameter for certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential to use for the Network Controller.
Specify this parameter for Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceCredentials
List of device Credentials. Specify if device credentials are different then Network Controller.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeTraces
Indicates that this cmdlet includes Host Agent and Network Controller Traces.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkController
Specifies the name or IP address of a Network Controller node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputDirectory
Specifies the full path of a folder for the results.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestURI
Specifies the URI to use for Network Controller REST APIs.
Specify this parameter for wildcard certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetupDiagnostics
Indicates that logging is to be enabled.
If you do not specify this parameter, logs are to be collected, but logging is not enabled.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Debug-NetworkControllerConfigurationState](./Debug-NetworkControllerConfigurationState.md)

[Debug-ServiceFabricNodeStatus](./Debug-ServiceFabricNodeStatus.md)

