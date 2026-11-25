---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_Dns.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualdns?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalDns
---

# Get-UalDns

## SYNOPSIS
Gets UAL records for a DNS server.

## SYNTAX

```
Get-UalDns [-ProductName <String[]>] [-RoleName <String[]>] [-RoleGuid <String[]>] [-IPAddress <String[]>]
 [-HostName <String[]>] [-LastSeen <DateTime[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalDns** cmdlet gets User Access Logging (UAL) records for a Domain Name System (DNS) server.
Use this cmdlet only for a DNS server.
Use the *CimSession* parameter to run the cmdlet on a remote DNS server.

UAL logs DNS name requests directed to DNS servers.
UAL gets this information from a DNS server only once a day.

For each client that accesses a service on a DNS server, this cmdlet returns a record that specifies the host name and the IP address of the requester.
The record also includes the server role that the client requested and the name of the server product, along with the time of the most recent DNS name request from the client.

You can specify parameter values to narrow the records that this cmdlet returns.
For instance, you can get records for only a specified IP address.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get name request information for a specific IP address
```
PS C:\>Get-UalDns -IPAddress "10.17.44.6"
```

This command gets UAL records of name requests for a client device with a specified IP address.

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

### -HostName
Specifies an array of names for clients that request a service.

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

### -IPAddress
Specifies an array of IP addresses for clients that request a service.

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

### -LastSeen
Specifies an array of dates, as **DateTime** objects.
A time represents when the client accessed the service for the most recent time.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductName
Specifies an array of names of products.
The installed role or specific product in the request is a component of this product.

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

### -RoleGuid
Specifies an array of GUIDs for roles that clients access.

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

### -RoleName
Specifies an array of names for roles that client's access.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UalOverview](./Get-UalOverview.md)

[Get-UalServerDevice](./Get-UalServerDevice.md)

[Get-UalServerUser](./Get-UalServerUser.md)

[Get-UalHyperV](./Get-UalHyperV.md)

[Get-Ual](./Get-Ual.md)

