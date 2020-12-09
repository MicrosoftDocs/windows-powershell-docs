---
external help file: MSFT_NetIpHTTPsConfiguration.cdxml-help.xml
Module Name: NetworkTransition
online version: 
schema: 2.0.0
title: Add-NetIPHttpsCertBinding
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 2F79CD8C-FF12-4BBB-ACC4-5600BF8318BF
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-NetIPHttpsCertBinding

## SYNOPSIS
Binds an SSL certificate to an IP-HTTPS server.

## SYNTAX

```
Add-NetIPHttpsCertBinding -CertificateHash <String> -ApplicationId <String> -IpPort <String>
 -CertificateStoreName <String> -NullEncryption <Boolean> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetIPHttpsCertBinding** cmdlet binds an SSL certificate to an IP-HTTPS server.

This cmdlet does not work if there is already a certificate binding on the computer.

This cmdlet is similar to the `netsh http add sslcert` command, but the cmdlet should only be used for IP-HTTPS.

## EXAMPLES

### Example 1: Add an SSL certificate
```
PS C:\>Add-NetIPHttpsCertBinding -IpPort "10.1.1.1:443" -CertificateHash "0102030405060708090A0B0C0D0E0F1011121314" -CertifcateStoreName "my" -ApplicationId "{3F2504E0-4F89-11D3-9A0C-0305E82C3301}" -NullEncryption $false
```

This command binds an SSL certificate with the specified IP port 10.1.1.1:443, SHA hash 0102030405060708090A0B0C0D0E0F1011121314, application ID {3F2504E0-4F89-11D3-9A0C-0305E82C3301}, and store name my to the IP-HTTPS server.

## PARAMETERS

### -ApplicationId
Specifies the GUID to identify the application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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

### -CertificateHash
Specifies the SHA hashing of the certificate.
This hash is 20 bytes long, and you must specify this value as a hexadecimal string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateStoreName
Specifies the store name for the certificate. 

This parameter defaults to MY for IP-based configurations. 

This parameter is required. 

You must store the certificate in the local system context.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpPort
Specifies the IP address and the port for the binding.
This parameter value should match the format `0.0.0.0:443`.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NullEncryption
Allows the usage of IP-HTTPS without SSL encryption, if the parameter value is True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Remove-NetIPHttpsCertBinding](./Remove-NetIPHttpsCertBinding.md)

