---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetConnectionProfile.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetConnectionProfile
ms.reviewer:
ms.assetid: 526AB39C-AC87-4484-BFC8-48D3FCA7648A
---

# Get-NetConnectionProfile

## SYNOPSIS
Gets a connection profile.

## SYNTAX

```
Get-NetConnectionProfile [-Name <String[]>] [-InterfaceAlias <String[]>] [-InterfaceIndex <UInt32[]>]
 [-NetworkCategory <NetworkCategory[]>] [-IPv4Connectivity <IPv4Connectivity[]>]
 [-IPv6Connectivity <IPv6Connectivity[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetConnectionProfile** cmdlet gets a connection profile associated with one or more physical network adapters.
A connection profile represents a network connection.

## EXAMPLES

### Example 1: Get a connection profile
```
PS C:\>Get-NetConnectionProfile -InterfaceAlias "Ethernet1" | Set-NetConnectionProfile -NetworkCategory Public
```

This first part of this command gets the connection profile for the network adapter named Ethernet1.
The command passes the results to the Set-NetConnectionProfile cmdlet by using the pipe operator.
The second part of the command changes the value of the network category for the connection profile.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](http://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](http://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a N[New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -IPv4Connectivity
Specifies an array of IPv4 protocol connectivity status values.
The acceptable values for this parameter are:

- Disconnected
- NoTraffic
- Subnet
- LocalNetwork
- Internet

```yaml
Type: IPv4Connectivity[]
Parameter Sets: (All)
Aliases: 
Accepted values: Disconnected, NoTraffic, Subnet, LocalNetwork, Internet

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Connectivity
Specifies an array of IPv6 protocol connectivity status values.
The acceptable values for this parameter are:

- Disconnected
- NoTraffic
- Subnet
- LocalNetwork
- Internet

```yaml
Type: IPv6Connectivity[]
Parameter Sets: (All)
Aliases: 
Accepted values: Disconnected, NoTraffic, Subnet, LocalNetwork, Internet

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies an array of names of network adapters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of numerical index values associated with the network adapters.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of networks with which the connection is currently established.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkCategory
Specifies an array of category types of a network.
The acceptable values for this parameter are:

- Public
- Private
- DomainAuthenticated

```yaml
Type: NetworkCategory[]
Parameter Sets: (All)
Aliases: 
Accepted values: Public, Private, DomainAuthenticated

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-NetConnectionProfile](./Set-NetConnectionProfile.md)

