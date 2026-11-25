---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/test-adfsfarmjoin?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-AdfsFarmJoin
---

# Test-AdfsFarmJoin

## SYNOPSIS
Runs prerequisite checks for adding the server computer to a federation server farm.

## SYNTAX

### AdfsFarmJoinWidGmsa (Default)
```
Test-AdfsFarmJoin [-CertificateThumbprint <String>] -GroupServiceAccountIdentifier <String>
 [-Credential <PSCredential>] -PrimaryComputerName <String> [-PrimaryComputerPort <Int32>] [<CommonParameters>]
```

### ADFSFarmJoinWidSvcAcct
```
Test-AdfsFarmJoin [-CertificateThumbprint <String>] -ServiceAccountCredential <PSCredential>
 [-Credential <PSCredential>] -PrimaryComputerName <String> [-PrimaryComputerPort <Int32>] [<CommonParameters>]
```

### ADFSFarmJoinSqlSvcAcct
```
Test-AdfsFarmJoin [-CertificateThumbprint <String>] -ServiceAccountCredential <PSCredential>
 [-Credential <PSCredential>] -SQLConnectionString <String> [-FarmBehavior <Int32>] [<CommonParameters>]
```

### AdfsFarmJoinSqlGmsa
```
Test-AdfsFarmJoin [-CertificateThumbprint <String>] -GroupServiceAccountIdentifier <String>
 [-Credential <PSCredential>] -SQLConnectionString <String> [-FarmBehavior <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-AdfsFarmJoin** cmdlet performs the checks that you must complete before you run the **Add-AdfsFarmNode** cmdlet to add the local server computer to an existing federation server farm.

## EXAMPLES

### Example 1: Test a server computer as a node in an existing federation server farm
```
PS C:\> $FScred = Get-Credential
PS C:\> Test-AdfsFarmJoin -ServiceAccountCredential $FScred -SQLConnectionString "Data Source=SQLHost;Integrated Security=True"
```

The first command uses the **Get-Credential** cmdlet to create a credential object for the Active Directory account under which the AD FS service runs.
The command stores the credential object in the $FScred variable.

The second command tests the joining of the local server computer as a node in an existing federation server farm that uses a SQL Server database that is installed on a computer named SQLHost.
The command specifies the credentials that are stored in the $FScred variable for the Active Directory account under which the AD FS service runs.

### Example 2: Test the overwrites of an existing AD FS configuration database
```
PS C:\> $FScred = Get-Credential
PS C:\> Test-AdfsFarmJoin -PrimaryComputerName "PrimaryWIDHost" -PrimaryComputerPort 80 -ServiceAccountCredential $FScred -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed
```

The first command uses the **Get-Credential** cmdlet to create a credential object for the Active Directory account under which the AD FS service runs.
The command stores the credential object in the $FScred variable.

The second command tests the overwrites of an existing AD FS configuration database and tests the joining of the local server computer as a node in an existing federation server farm that uses the Windows Internal Database.
The primary node of the farm is installed on a computer named PrimaryWIDHost.
The command specifies the credentials that are stored in $FScred for the Active Directory account under which the AD FS service runs.

The *CertificateThumbprint* parameter must specify the thumbprint of a certificate that is currently installed in the certificate store of the local computer.
The certificate must be the same certificate that is used as the service communications certificate on the primary node.

## PARAMETERS

### -CertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that the Secure Sockets Layer (SSL) binding of the default website uses in Internet Information Services (IIS).
This value must match the thumbprint of a valid certificate in the certificate store of the local computer.

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
Specifies a **PSCredential** object based on a user name and password.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

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
Specifies farm behavior.

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
Specifies the name of the group Managed Service Account that the Active Directory Federation Services (AD FS) service uses as the logon identity for the AD FS service.

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

### -PrimaryComputerName
Specifies the name of the primary federation server in a federation server farm.
The cmdlet checks the federation server farm that has the primary federation server that you specify.

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
Specify a value of 80 for this parameter, or specify an alternative value if the HTTP port on the primary computer is not 80.
If you do not specify this parameter, the cmdlet assigns the default port value of 443.

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
Specifies a **PSCredential** object based on a user name and password for the service account in Active Directory® Domain Services under which the AD FS service runs.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

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
Specifies the Microsoft SQL Server database that will store the AD FS configuration settings.
If you do not specify this parameter, AD FS uses the Windows Internal Database to store configuration settings.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-AdfsFarmNode](./Add-AdfsFarmNode.md)

[Test-AdfsFarmInstallation](./Test-AdfsFarmInstallation.md)

