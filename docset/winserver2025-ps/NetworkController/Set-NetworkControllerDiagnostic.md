---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/set-networkcontrollerdiagnostic?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkControllerDiagnostic
---

# Set-NetworkControllerDiagnostic

## SYNOPSIS
Changes diagnostic settings for the Network Controller.

## SYNTAX

```
Set-NetworkControllerDiagnostic [-LogScope <LogScope>] [-DiagnosticLogLocation <String>]
 [-LogLocationCredential <PSCredential>] [-UseLocalLogLocation] [-LogTimeLimitInDays <UInt32>]
 [-LogSizeLimitInMBs <UInt32>] [-LogLevel <LogLevel>] [-PassThru] [-Force] [-ComputerName <String>] [-UseSsl]
 [-Credential <PSCredential>] [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkControllerDiagnostic** cmdlet changes diagnostic settings for the Network Controller.
You can specify whether to collect logs locally on the nodes, or in a single central remote location.
You can specify the central location and credentials to access that location.
You can specify whether to collect all logs or only cluster logs.

## EXAMPLES

### Example 1: Modify diagnostic settings
```
PS C:\> Set-NetworkControllerDiagnostic -LogScope All -UseLocalLogLocation -PassThru
LogScope               : All
DiagnosticLogLocation  :
```

This command changes the location for diagnostic logs to be the Network Controller nodes.
The command also starts logging both cluster and application logs.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
Specify the certificate thumbprint of the certificate.
Specify this parameter only if you run this cmdlet on a computer that is not part of the Network Controller cluster.

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

### -ComputerName
Specifies the name of the Network Controller node on which this cmdlet operates.

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

### -Credential
Specifies a user credential that has permission to perform this action.
The default is the current user.
Specify this parameter only if you run this cmdlet on a computer that is not part of the Network Controller cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiagnosticLogLocation
Specifies a central remote location for the logs.

If you do not specify a value for this parameter, the logs are stored locally on each node.
Application logs are stored locally in the %systemdrive%\Windows\tracing\SDNDiagnostics folder.
Cluster logs are stored locally in %systemdrive%\ProgramData\Microsoft\Service Fabric\log\Traces folder.

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

### -LogLevel
Specifies the level of the log.The acceptable values for this parameter are:

- Error
- Warning
- Informational
- Verbose

The default value is Verbose.

```yaml
Type: LogLevel
Parameter Sets: (All)
Aliases:
Accepted values: Error, Warning, Informational, Verbose

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogLocationCredential
Specifies the credentials required to access the log location.
Specify this parameter only if the log location restricts access.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogScope
Specifies whether Network Controller collects cluster logs or collects all logs.
All logs include cluster and application logs.
The acceptable values for this parameter are: Cluster and All.

```yaml
Type: LogScope
Parameter Sets: (All)
Aliases:
Accepted values: Cluster, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogSizeLimitInMBs
Specifies the maximum log size, in MB, to store.
Logs are stored in a circular fashion.
. If the *DiagnosticLogLocation* parameter is provided, the default value of this parameter is 40 GB.
If DiagnosticLogLocation is not provided, the logs are stored on the Network Controller nodes and the default value of this parameter is 15 GB.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogTimeLimitInDays
Specifies the duration, in days, that logs are stored.
Logs are stored in a circular fashion.
The default value of this parameter is 3 days.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -UseLocalLogLocation
Indicates that this cmdlet collects all diagnostic logs locally on each node in the Network Controller cluster.
To collect logs centrally in a remote location, specify the *DiagnosticLogLocation* parameter.

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

### -UseSsl
Indicates that the remote computer uses the Secure Sockets Layer (SSL) protocol to establish a connection to the Network Controller node.
The default value of this parameter is $False.
Specify this parameter only if you run this cmdlet on a computer that is not part of the Network Controller cluster.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

This cmdlet returns an object that contains the following fields:

- Log scope
- Diagnostic log location
- Log aging size limit in MBs
- Log aging time limit in days
- Log level

## NOTES

## RELATED LINKS

[Get-NetworkControllerDiagnostic](./Get-NetworkControllerDiagnostic.md)

