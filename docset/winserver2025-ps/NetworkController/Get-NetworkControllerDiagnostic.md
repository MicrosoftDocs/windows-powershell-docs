---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerdiagnostic?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerDiagnostic
---

# Get-NetworkControllerDiagnostic

## SYNOPSIS
Gets network controller diagnostic settings.

## SYNTAX

```
Get-NetworkControllerDiagnostic [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerDiagnostic** cmdlet gets network controller diagnostic settings.
This cmdlet displays whether the network controller collects only cluster logs.
If a remote log location exists, this cmdlet displays it.

## EXAMPLES

### Example 1: Get diagnostic settings
```
PS C:\> Get-NetworkControllerDiagnostic -ComputerName "Node01.Contoso.com"
LogScope               : All
DiagnosticLogLocation  :
LogTimeLimitInDays     : 3
LogSizeLimitInMBs      :
LogLevel               : Verbose
```

This command gets the diagnostic settings for a cluster that contains the node named Node01.Contoso.com.
The cmdlet shows that network controller collects all diagnostic logs.
The network controller collects the logs locally on the nodes.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
Specify the certificate thumbprint of the certificate.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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
Specifies the name of the network controller node on which this cmdlet operates.

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

### -Credential
Specifies a user credential that has permission to perform this action.
The default is the current user.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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

### -UseSsl
Indicates that the remote computer uses the Secure Sockets Layer (SSL) protocol to establish a connection to the Network Controller node.
The default value of this parameter is false.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

This cmdlet returns an object that contains the following fields:

- Log scope
- Diagnostic log location
- Log aging time limit (in days)
- Log aging size limit (in MB)
- Log level

## NOTES

## RELATED LINKS

[Set-NetworkControllerDiagnostic](./Set-NetworkControllerDiagnostic.md)

