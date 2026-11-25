---
external help file: NetworkControllerFc-help.xml
Module Name: NetworkControllerFc
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkcontrollerfc/install-networkcontrolleronfailovercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-NetworkControllerOnFailoverCluster
---

# Install-NetworkControllerOnFailoverCluster

## SYNOPSIS
Installs NetworkController on a FailOver cluster. The user running this should be a part of the
Cluster Administrators group.

## SYNTAX

### None (Default)

```
Install-NetworkControllerOnFailoverCluster [-PackagePath <String>] -DatabasePath <String>
 [-RestIPAddress <String>] [-ClientAuthentication <ClientAuthentication>]
 [-ClusterAuthentication <ClusterAuthentication>] [-RestCertificateThumbPrint <String>]
 [-RestClientCertificateSubjectNames <String[]>] [-RestName <String>] [-ClusterNetworkName <String>]
 [<CommonParameters>]
```

### Kerberos

```
Install-NetworkControllerOnFailoverCluster [-PackagePath <String>] -DatabasePath <String>
 [-RestIPAddress <String>] -ClientAuthentication <ClientAuthentication>
 [-ClusterAuthentication <ClusterAuthentication>] [-RestCertificateThumbPrint <String>]
 [-RestCertificateSubjectName <String>] [-RestClientCertificateThumbprints <String[]>]
 [-RestClientCertificateSubjectNames <String[]>] -RestClientSecurityGroup <String>
 [-RestName <String>] [-ClusterNetworkName <String>] [<CommonParameters>]
```

### X509

```
Install-NetworkControllerOnFailoverCluster [-PackagePath <String>] -DatabasePath <String>
 [-RestIPAddress <String>] -ClientAuthentication <ClientAuthentication>
 [-ClusterAuthentication <ClusterAuthentication>] [-RestCertificateThumbPrint <String>]
 [-RestCertificateSubjectName <String>] [-RestClientCertificateThumbprints <String[]>]
 [-RestClientCertificateSubjectNames <String[]>] [-RestName <String>] [-ClusterNetworkName <String>]
 [<CommonParameters>]
```

## DESCRIPTION

Installs Network Controller on a Windows FailOver Cluster..

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ClientAuthentication

This the Client authentication Mode.

```yaml
Type: ClientAuthentication
Parameter Sets: None
Aliases:
Accepted values: None, Kerberos, X509

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: ClientAuthentication
Parameter Sets: Kerberos, X509
Aliases:
Accepted values: None, Kerberos, X509

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterAuthentication

This the Cluster authentication Mode.

```yaml
Type: ClusterAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: None, Kerberos, X509

Required: False
Position: Named
Default value: X509
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterNetworkName

This is the name of the cluster network to be used for the REST server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabasePath

Specifies path to the database.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackagePath

This is a directory where the NetworkController installation package is present. By default this is
the NetworkController installation folder under %windir%\NetworkController. This can also be a
private package path.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $global:defaultBinaryDir
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestCertificateSubjectName

{{ Fill RestCertificateSubjectName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestCertificateThumbPrint

This is the REST Server certificate Thumbprint.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestClientCertificateSubjectNames

{{ Fill RestClientCertificateSubjectNames Description }}

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestClientCertificateThumbprints

{{ Fill RestClientCertificateThumbprints Description }}

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestClientSecurityGroup

This is the client security group for Kerberos authentication by the REST server.

```yaml
Type: System.String
Parameter Sets: Kerberos
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestIPAddress

This is the Floating IP for the rest server. This is needed if multinode Deployment is used. When
this is specified this has to be in the IP/MASKLength format. Ex 10.10.0.1/24

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestName

The DNS name of the REST endpoint.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [string]::Empty
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
