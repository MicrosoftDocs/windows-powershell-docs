---
description: The Get-NetworkControllerBackup cmdlet gets the status of a backup operation started with the New-NetworkControllerBackup cmdlet
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 09/27/2021
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerbackup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerBackup
---

# Get-NetworkControllerBackup

## SYNOPSIS
Gets the status of a backup operation.

## SYNTAX

```
Get-NetworkControllerBackup [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerBackup** cmdlet gets the status of a backup operation started with the **New-NetworkControllerBackup** cmdlet

## EXAMPLES

### Example 1: Get all Network Controller backups
```powershell
Get-NetworkControllerBackup -ConnectionUri https://networkcontroller
```

This command gets the status of backups for the specified Network Controller.

### Example 2: Get a network controller backup
```powershell
$Credential = Get-Credential
Get-NetworkControllerBackup -ResourceId "BackupUser" -ConnectionUri https://networkcontroller -Credential $Credential
```

This command gets the Network Controller backup for the specified ID.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
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

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of a Network Controller.
The cmdlet gets backups for that controller.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.
The default value is the current user.

This user must be present in the security group provided in the **ClientSecurityGroup** parameter in the `Install-NetworkController` cmdlet.
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

### -PassInnerException
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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

### -ResourceId
Specifies the resource ID of the backup to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

[New-NetworkControllerBackup](New-NetworkControllerBackup.md)

[Remove-NetworkControllerBackup](Remove-NetworkControllerBackup.md)
