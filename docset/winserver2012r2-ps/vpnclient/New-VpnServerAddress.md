---
external help file: PS_VpnServerAddress_v1.0.cdxml-help.xml
Module Name: VpnClient
online version: 
schema: 2.0.0
title: New-VpnServerAddress
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 0C804810-353B-48E0-9F00-D88126FD0902
ms.author: v-anbarr
ms.reviewer: brianlic
---

# New-VpnServerAddress

## SYNOPSIS
Creates a VPN server address object.

## SYNTAX

```
New-VpnServerAddress [-ServerAddress] <String> [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-VpnServerAddress** cmdlet creates a virtual private network (VPN) server address object.
Specify a server by name or by IP address, and specify a friendly name for the address of the server.

## EXAMPLES

### Example 1: Create a VPN server address by using an FQDN
```
PS C:\>New-VpnServerAddress -ServerAddress "RAS.Washington.Contoso.com" -FriendlyName "Washington"
ServerAddress : RAS.Washington.Contoso.com 

FriendlyName  : Washington
```

This command creates a VPN server address object that has the FQDN RAS.Washington.Contoso.com.
The command specifies the name Washington for the server address.

### Example 2: Create a VPN server address by using an IP address
```
PS C:\>New-VpnServerAddress -ServerAddress "172.16.12.3" -FriendlyName "Singapore"
ServerAddress : 207.56.12.03

FriendlyName  : Singapore
```

This command creates a VPN server address object that has the IP address 172.16.12.3.
The command specifies the name Singapore for the server address.

## PARAMETERS

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

### -FriendlyName
Specifies a name for the VPN destination server.

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

### -ServerAddress
Specifies a DNS server.
You can specify either an IPv4 or an IPv6 address, or specify a fully qualified domain name (FQDN) that resolves to an IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnServerAddress

## NOTES

## RELATED LINKS

[Add-VpnConnection](./Add-VpnConnection.md)

