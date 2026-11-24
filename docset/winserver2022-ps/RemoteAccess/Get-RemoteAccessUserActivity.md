---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessUserActivity_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccessuseractivity?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessUserActivity
---

# Get-RemoteAccessUserActivity

## SYNOPSIS
Displays the resources accessed over the active DirectAccess (DA) and VPN connections and the resources accessed over historical DA and VPN connections.

## SYNTAX

### UserName (Default)
```
Get-RemoteAccessUserActivity [-ComputerName <String>] [-EndDateTime <DateTime>] [-StartDateTime <DateTime>]
 [-UserName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SessionId
```
Get-RemoteAccessUserActivity [-ComputerName <String>] -SessionId <UInt64> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### HostIP
```
Get-RemoteAccessUserActivity [-ComputerName <String>] -HostIPAddress <String> [-EndDateTime <DateTime>]
 [-StartDateTime <DateTime>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessUserActivity** cmdlet displays the resources accessed over the active DirectAccess (DA) and VPN connections and the resources accessed over historical DA and VPN connections.

The resources accessed over active and historical connections starting or ending on a Remote Access server are stored in the inbox accounting store on that server.
This cmdlet retrieves the resources accessed for a specific server.
The cmdlet is not impacted by multi-site deployment. 
                       
 -- If a start date nor an end date is specified, then the resources accessed over active connections are retrieved 
                       
 -- In order to retrieve the list of resources accessed over historical connections, a time duration needs to be specified such as a start date, an end date, or both.
If only one of them is specified, then the time stamp on the first or last record in the accounting database is used to fill the missing information and create a duration.

The statistics of active connections can be explicitly filtered by the user name of the user who originated the Remote Access connection and the tunnel IP address of the client computer such as the IP address assigned by the server, from which the connection originated.
However, only one of these filters can be used at a time.

## EXAMPLES

### EXAMPLE 1

```powershell
$startdate = Get-Date -Date "12/16/2011"



$startdate
16 December 2011 00:00:00


$enddate = Get-Date -Date "12/23/2011"



$enddate



Get-RemoteAccessUserActivity -StartDateTime $startdate -EndDateTime $enddate -UserName "corp.contoso.com\User1"
```

```output
ServerIpAddress                          ProtocolID                     ServerPort 
---------------                          ----------                     ---------- 
2001:4898:0:fff:0:5efe:10.57.36.131      6                              443 
2001:4898:0:fff:0:5efe:10.57.36.131      50                             0
```

This example shows historic access details for a particular user.
Query the accounting store for user activity details for User1 between the start date and end date.

### EXAMPLE 2

```powershell
Get-RemoteAccessUserActivity -UserName "contoso\User1" -ComputerName edge1.corp.contoso.com
```

```output
ServerIpAddress                          ProtocolID                     ServerPort 
---------------                          ----------                     ---------- 
2001:4898:0:fff:0:5efe:10.166.20.136     6                              80 
2001:4898:0:fff:0:5efe:172.27.97.57      6                              443 
2a01:110:10:1005:3e4a:92ff:fee0:1443     17                             500 
2a01:110:10:1005:3e4a:92ff:fee0:1443     17                             389 
2001:4898:a8:6001:3e4a:92ff:fedb:7104    17                             500 
2001:4898:a8:6001:3e4a:92ff:fedb:7104    17                             389 
2001:4898:0:fff:0:5efe:172.27.97.57      17                             500 
fdbd:8187:9fc9:7777::aa6:3609            17                             53 
2001:4898:0:fff:0:5efe:10.166.20.136     17                             500
```

This example shows the resources currently being accessed by the user named User1.
If the user is not active currently, then the cmdlet will not return any rows.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDateTime
Specifies the time duration for which the user activity needs to be retrieved and indicates the end date.

```yaml
Type: DateTime
Parameter Sets: UserName, HostIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HostIPAddress
Specifies the tunnel IP address of the connection.
This can be an IPv4 or IPv6 address.

```yaml
Type: String
Parameter Sets: HostIP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionId
Specifies an ID for a session for which to retrieve user activity data.

```yaml
Type: UInt64
Parameter Sets: SessionId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDateTime
Specifies the time duration for which the user activity needs to be retrieved and indicates the start date.

```yaml
Type: DateTime
Parameter Sets: UserName, HostIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UserName
Specifies the user whose activity needs to be retrieved.
This parameter uses the `DOMAIN\USERNAME` format.

```yaml
Type: String
Parameter Sets: UserName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.DateTime

### System.UInt64

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessUserActivity

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
For both real-time and accounting cases, the RemoteAccessUserActivity object consists of the following properties.
A separate instance of the RemoteAccessUserActivity object is output for every corporate network resource that is accessed over the connection. 
                         
 -- The IP address of the server in the corporate network. 
                         
 -- The identity of the protocol used to access the server. 
                         
 -- The port number used to access the server.

## NOTES

## RELATED LINKS

[Get-Date](https://go.microsoft.com/fwlink/p/?LinkId=113313)

