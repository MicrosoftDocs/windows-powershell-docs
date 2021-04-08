---
author: Kateyanne
external help file: Microsoft.FederationServices.Deployment.dll-Help.xml
manager: dansimp
Module Name: ADFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adfs/add-adfsfarmnode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-AdfsFarmNode

## SYNOPSIS
Adds this computer to an existing federation server farm.

## SYNTAX

### ADFSFarmJoin (Default)
```
Add-AdfsFarmNode [-CertificateThumbprint <String>] [-OverwriteConfiguration] -PrimaryComputerName <String>
 [-PrimaryComputerPort <Int32>] -ServiceAccountCredential <PSCredential> [<CommonParameters>]
```

### ADFSFarmJoinSQL
```
Add-AdfsFarmNode [-CertificateThumbprint <String>] -ServiceAccountCredential <PSCredential>
 -SQLConnectionString <String> [<CommonParameters>]
```

## DESCRIPTION
The Add-AdfsFarmNode cmdlet adds this computer to an existing federation server farm.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$fscredential = Get-Credential
C:\PS>Add-AdfsFarmNode -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True"
```

Description

-----------

Adds the local server computer as a node in an existing federation server farm that uses a Microsoft SQL Server database installed on a computer called "SQLHost".

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$fscredential = Get-Credential
C:\PS>Add-AdfsFarmNode -OverwriteConfiguration -PrimaryComputerName "PrimaryWIDHost" -PrimaryComputerPort 80 -ServiceAccountCredential $fscredential -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed
```

Description

-----------

Overwrites an existing AD FS configuration database and adds the local server computer as a node in an existing federation server farm that uses Windows Internal Database (WID) and whose primary node is installed on a computer called "PrimaryWIDHost".

Note that the PrimaryComputerPort is needed even if the default HTTP port of 80 is used and that the CertificateThumbprint parameter is only required if it is not already configured as a binding in IIS.
Also when specifying a value for the CertificateThumbprint parameter, the value you use must specify the thumbprint of a certificate that is currently installed in the local machine My store, and the certificate must be the same certificate that is used as the SSL certificate on the primary node.

## PARAMETERS

### -CertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used in the SSL binding of the Default Web Site in IIS.
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

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

### -OverwriteConfiguration
This parameter must be used to remove an existing AD FS configuration database and overwrite it with a new database.

```yaml
Type: SwitchParameter
Parameter Sets: ADFSFarmJoin
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryComputerName
Specifies the name of the primary federation server in the farm that this computer will join.

```yaml
Type: String
Parameter Sets: ADFSFarmJoin
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryComputerPort
Specifies the value of the HTTP port that this computer uses to connect with the primary computer in order to synchronize configuration settings.
Specify a value of 80 for this parameter, or specify an alternate value if the HTTP port on the primary computer is not 80.
If this parameter is not specified, a default port value of 443 is assumed.

```yaml
Type: Int32
Parameter Sets: ADFSFarmJoin
Aliases: 

Required: False
Position: Named
Default value: 80
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLConnectionString
Specifies the SQL Server database that will store the AD FS configuration settings.
If not specified, AD FS uses Windows Internal Database to store configuration settings

```yaml
Type: String
Parameter Sets: ADFSFarmJoinSQL
Aliases: 

Required: True
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
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Result object

## NOTES

## RELATED LINKS

