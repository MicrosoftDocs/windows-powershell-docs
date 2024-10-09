---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-VipConnectivityInfo.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/get-networkcontrollervipresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVipResource
---

# Get-NetworkControllerVipResource

## SYNOPSIS
Gets a VIP resource.

## SYNTAX

```
Get-NetworkControllerVipResource [[-RestURI] <String>] [[-CertificateThumbprint] <String>]
 [[-Credential] <PSCredential>] [[-Direction] <String>] [-IPAddress] <String> [[-DstPort] <String>]
 [[-Protocol] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVipResource** cmdlet gets information, such as the MUXes and DIP hosts, for the specified virtual IP address (VIP) resource.

## EXAMPLES

### Example 1: Get a Network Controller VIP resource
```
PS C:\> $Cred = Get-Credential
PS C:\> Get-NetworkControllerVipResource -Credential $Cred -DstPort 80 -IPAddress 10.123.176.108 -Direction "In"
```

The first command gets the credentials and stores them in the $Cred variable.

The second command gets the specified VIP resource using the credentials in $Cred.

## PARAMETERS

### -CertificateThumbprint
Specifies a certificate thumbprint for Network Controller.
Specify this parameter for a certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direction
Specifies the direction of the traffic flow.
The acceptable values for this parameter are:

- In
- Out

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Out, In

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DstPort
Specifies the port for the VIP resource to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies the IP address of the VIP resource to get.

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

### -Protocol
Specifies the protocol of the VIP resource to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Tcp, Udp, All

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestURI
Specifies the URI to use for Network Controller REST APIs.
Specify this parameter for a wild card certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

