---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-VipConnectivityInfo.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/get-viphostmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VipHostMapping
---

# Get-VipHostMapping

## SYNOPSIS
Gets VIP host mapping.

## SYNTAX

```
Get-VipHostMapping [-NetworkController] <String> [[-Credential] <PSCredential>] [-RestURI] <String>
 [[-CertificateThumbprint] <String>] [-VipEndPoint] <String> [-Type] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VipHostMapping** cmdlet gets information for a virtual IP (VIP) host, including its multiplexers (MUXes) and DIP hosts.

## EXAMPLES

### Example 1: Get a VIP host mapping
```
PS C:\> $Password = ConvertTo-SecureString -String $Pass -AsPlainText -Force
PS C:\> $Cred = New-Object PSCredential -ArgumentList (".\administrator", $Password)
PS C:\> $ncIPAddress = 55.1.1.3
PS C:\> $NCInfo = Get-NetworkControllerDeploymentInfo -NetworkController $ncIPAddress -Credential $Cred
PS C:\> $vipInfo = Get-NetworkControllerVipResource -RestURI $NCInfo.NetworkControllerURI -ClientCertificate $NCInfo.ClientCertificate -IPAddress "72.1.12" -DstPort "2003" -Protocol "Tcp"
PS C:\> Get-VipHostMapping -NetworkController $ncIPAddress -Credential $Cred -RestURI $NCInfo.NetworkControllerURI -CertificateThumbprint $NCInfo.ClientCertificate -VipEndPoint $vipInfo.ResourceRef -L3NAT $vipInfo.L3NAT
```

The first command creates a password, and then stores it in the $Password variable.

The second command creates a **PSCredential** object, and then stores it in the $Cred variable.

The third command assigns the specified Network Controller IP address to the $ncIPAddress variable.

The fourth command gets the Network Controller deployment information, and then stores it in the $NCInfo variable.

The fifth command gets the specified VIP resource, and then stores it in the $vipInfo variable.

The last command gets the VIP host mapping for the specified host.

## PARAMETERS

### -CertificateThumbprint
Specifies a certificate thumbprint for Network Controller.
Specify this parameter for a certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use for Network Controller.
Specify this parameter for a Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkController
Specifies a Network Controller node name or IP address.

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

### -RestURI
Specifies the URI to use for Network Controller REST APIs.
Specify this parameter for wild card certificate deployments.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type.
The acceptable values for this parameter are:

- L3Nat
- InboundNatRule
- LoadBalancingRule
- OutboundNatRule

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: L3Nat, InboundNatRule, LoadBalancingRule, OutboundNatRule

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VipEndPoint
Specifies the VIP endpoint REST resource.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
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

[Get-NetworkControllerVipResource](./Get-NetworkControllerVipResource.md)

