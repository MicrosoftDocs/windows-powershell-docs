---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VPNUser_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/disconnect-vpnuser?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-VpnUser
---

# Disconnect-VpnUser

## SYNOPSIS
Disconnects a VPN connection originated by a specific user or originating from a specific client computer.

## SYNTAX

### UserName (Default)
```
Disconnect-VpnUser [-ComputerName <String>] [-PassThru] [-UserName] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HostIP
```
Disconnect-VpnUser [-ComputerName <String>] [-PassThru] -HostIPAddress <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-VpnUser** cmdlet disconnects a VPN connection originated by a specific user or originating from a specific client computer.

The list of active VPN connections originating or ending on a VPN server is stored in the inbox accounting store on the server.
Therefore, this cmdlet would have to be run on the server where the connection starts or ends to disconnect a user.

A VPN connection can be disconnected in one of the following two ways.
Note: Only one of these methods can be used at a time.

 -- By user name of the user who originated the connection.

 -- By tunnel IP address assigned by the VPN server.

## EXAMPLES

### EXAMPLE 1
```
Disconnect-VpnUser -HostIPAddress 10.1.1.11 -PassThru 10.1.1.11
```

This example disconnects a VPN connection by specifying the host address.
There is one active VPN connection in this example.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.
When this parameter is specified the cmdlet looks for the specified user or host IP on that Remote Access server.

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

### -HostIPAddress
Specifies the list of tunnel IP addresses of the VPN connection.
These can be IPv4 or IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: HostIP
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Specifies the list of users that need to be disconnected.
The Remote Access login name of the user that is used may be a domain account.
If the user is a domain account, then it can be specified in `DOMAIN\USERNAME` format otherwise it is specified as a normal string.

```yaml
Type: String[]
Parameter Sets: UserName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.String[]
The array of strings consists of the list of user names or host addresses of the connections that were disconnected.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Get-RemoteAccessConnectionStatistics](./Get-RemoteAccessConnectionStatistics.md)

