---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/update-networkcontroller?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-NetworkController
---

# Update-NetworkController

## SYNOPSIS

Updates the Network Controller binaries.

## SYNTAX

```
Update-NetworkController [-Update <UpdateType>] [-Force] [-ComputerName <String>] [-UseSsl]
 [-Credential <PSCredential>] [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### -Update
Specifies the type of update. Valid values are:

- Default. Compares the inbox version with the running version. Updates only if the inbox version is higher.
  Cluster and Service Fabric are updated only if the cluster was deployed through **Install-NetworkController**.

  This is the default update type.

- Application. Updates only the application.
  Application is updated only if the inbox (template) version is higher than the running version.

- Cluster. Updates only the cluster.

  If the cluster was installed through **Install-NetworkController**, the cluster and Service Fabric are updated only if the inbox version is higher than the installed version.

  If the cluster was not installed through **Install-NetworkController**, Service Fabric is updated only if the inbox (CAB) version is higher than the installed version.

  The manifest is always updated.

```yaml
Type: UpdateType
Parameter Sets: (All)
Aliases:
Accepted values: Default, Application, Cluster

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

[Get-NetworkController](./Get-NetworkController.md)

[Install-NetworkController](./Install-NetworkController.md)

[Set-NetworkController](./Set-NetworkController.md)

[Uninstall-NetworkController](./Uninstall-NetworkController.md)
