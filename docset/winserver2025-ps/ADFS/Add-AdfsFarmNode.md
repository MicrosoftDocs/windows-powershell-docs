---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsfarmnode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsFarmNode
---

# Add-AdfsFarmNode

## SYNOPSIS
Adds this computer to an existing federation server farm.

## SYNTAX

### AdfsFarmJoinWidGmsa (Default)
```
Add-AdfsFarmNode [-OverwriteConfiguration] [-CertificateThumbprint <String>]
 -GroupServiceAccountIdentifier <String> [-Credential <PSCredential>] -PrimaryComputerName <String>
 [-PrimaryComputerPort <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSFarmJoinWidSvcAcct
```
Add-AdfsFarmNode [-OverwriteConfiguration] [-CertificateThumbprint <String>]
 -ServiceAccountCredential <PSCredential> [-Credential <PSCredential>] -PrimaryComputerName <String>
 [-PrimaryComputerPort <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSFarmJoinSqlSvcAcct
```
Add-AdfsFarmNode [-CertificateThumbprint <String>] -ServiceAccountCredential <PSCredential>
 [-Credential <PSCredential>] -SQLConnectionString <String> [-FarmBehavior <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AdfsFarmJoinSqlGmsa
```
Add-AdfsFarmNode [-CertificateThumbprint <String>] -GroupServiceAccountIdentifier <String>
 [-Credential <PSCredential>] -SQLConnectionString <String> [-FarmBehavior <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsFarmNode** cmdlet adds this computer to an existing federation server farm.

## EXAMPLES

### Example 1: Add a farm node
```
PS C:\> $fscredential = Get-Credential
PS C:\> Add-AdfsFarmNode -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True"
```

This example adds the local server computer as a node in an existing federation server farm that uses a Microsoft SQL Server database installed on a computer named SQLHost.

### Example 2: Add a farm node and overwrite the existing configuration
```
PS C:\> $fscredential = Get-Credential
PS C:\> Add-AdfsFarmNode -OverwriteConfiguration -PrimaryComputerName "PrimaryWIDHost" -PrimaryComputerPort 80 -ServiceAccountCredential $fscredential -CertificateThumbprint "8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed"
```

This example overwrites an existing AD FS configuration database and adds the local server computer as a node in an existing federation server farm that uses Windows Internal Database (WID) and whose primary node is installed on a computer named PrimaryWIDHost.

Note that the *PrimaryComputerPort* is required even if the default HTTP port of 80 is used and that the *CertificateThumbprint* parameter is only required if it is not already configured as a binding in IIS.
Also, when specifying a value for the *CertificateThumbprint* parameter, the value you use must specify the thumbprint of a certificate that is currently installed in the local machine My store, and the certificate must be the same certificate that is used as the SSL certificate on the primary node.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint of a digital public key X.509 certificate of a user account that has permission to perform this action.

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
Specifies a **PSCredential** object.

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

### -FarmBehavior
```yaml
Type: Int32
Parameter Sets: ADFSFarmJoinSqlSvcAcct, AdfsFarmJoinSqlGmsa
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupServiceAccountIdentifier
Specifies the Group Managed Service Account under which the Active Directory Federation Services (AD FS) service runs.

```yaml
Type: String
Parameter Sets: AdfsFarmJoinWidGmsa, AdfsFarmJoinSqlGmsa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverwriteConfiguration
This parameter must be used to remove an existing AD FS configuration database and overwrite it with a new database.

```yaml
Type: SwitchParameter
Parameter Sets: AdfsFarmJoinWidGmsa, ADFSFarmJoinWidSvcAcct
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryComputerName
Specifies the name of the primary federation server in a federation server farm.
The cmdlet adds the computer to the federation server farm that has the primary federation server that you specify.

```yaml
Type: String
Parameter Sets: AdfsFarmJoinWidGmsa, ADFSFarmJoinWidSvcAcct
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryComputerPort
Specifies the primary computer port.
The computer uses the HTTP port that you specify to connect with the primary computer in order to synchronize configuration settings.
Specify a value of 80 for this parameter, or specify an alternate value if the HTTP port on the primary computer is not 80.
If this parameter is not specified, a default port value of 443 is assumed.

```yaml
Type: Int32
Parameter Sets: AdfsFarmJoinWidGmsa, ADFSFarmJoinWidSvcAcct
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountCredential
Specifies the Active Directory account under which the AD FS service runs.
All nodes in the farm must use the same service account.

```yaml
Type: PSCredential
Parameter Sets: ADFSFarmJoinWidSvcAcct, ADFSFarmJoinSqlSvcAcct
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLConnectionString
Specifies the SQL Server database that will store the AD FS configuration settings.
If not specified, AD FS uses Windows Internal Database to store configuration settings.

```yaml
Type: String
Parameter Sets: ADFSFarmJoinSqlSvcAcct, AdfsFarmJoinSqlGmsa
Aliases:

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Remove-AdfsFarmNode](./Remove-AdfsFarmNode.md)

