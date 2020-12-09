---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Update-NetworkController
ms.reviewer:
ms.assetid: E98F7AF1-2D8E-4438-91B1-3E6AD959133D
---

# Update-NetworkController

## SYNOPSIS

Updates the Network Controller binaries.

## SYNTAX

```
Update-NetworkController [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION

The **Update-NetworkController** cmdlet updates the Network Controller binaries after a software update is installed or after the operating system is upgraded.

Network Controller automatically updates binaries after no longer than one hour. If you want the binaries to be updated immediately, run this cmdlet.

For this cmdlet to run, the software update has to be installed on all the computers in the Network Controller cluster. In case of an operating system upgrade, for this cmdlet to run, the operating system has to be upgraded on all computers in the Network Controller cluster.

## EXAMPLES

### Example 1

This command updates the Network Controller binaries on all the computers in the Network Controller cluster. Run this cmdlet on a Network Controller computer.

```
PS C:\> Update-NetworkController
```

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetworkController](./Get-NetworkController.md)

[Get-NetworkController](./Get-NetworkController.md)

[Set-NetworkController](./Set-NetworkController.md)

[Uninstall-NetworkController](./Uninstall-NetworkController.md)
