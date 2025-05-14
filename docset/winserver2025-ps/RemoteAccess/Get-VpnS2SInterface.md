---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnS2SInterface_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-vpns2sinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VpnS2SInterface
---

# Get-VpnS2SInterface

## SYNOPSIS
Retrieves configuration details for a site-to-site (S2S) interface.

## SYNTAX

```
Get-VpnS2SInterface [[-Name] <String>] [[-RoutingDomain] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VpnS2SInterface** cmdlet retrieves details for a site-to-site (S2S) interface.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-VpnS2SInterface
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet
----                 -----------          -----------  --------------- ----------
edge1                {131.107.0.2}        True         Disconnected    {10.0.0.0/24:100}
```

This example retrieves all of the S2S VPN interfaces.

### EXAMPLE 2
```
PS C:\>Get-VpnS2SInterface | Format-List -Property *
Name                             : edge1
Destination                      : {131.107.0.2}
AdminStatus                      : True
ConnectionState                  : Disconnected
IPv4Subnet                       : {10.0.0.0/24:100}
IPv6Subnet                       : {2001:db8:1::/48:100}
Protocol                         : Ikev2
EncryptionType                   : RequireEncryption
AuthenticationMethod             : PSKOnly
EapMethod                        :
Certificate                      :
UserName                         :
ResponderAuthenticationMethod    : PSKOnly
NumberOfTries                    : 3
RetryInterval(s)                 : 60
SADataSizeForRenegotiation(KB)   : 33553408
SALifeTime(s)                    : 3600
NetworkOutageTime(s)             : 15
IdleDisconnect(s)                : 300
InternalIPv4                     : True
InternalIPv6                     : True
PromoteAlternate                 : False
LastError                        : 0
UnReachabilityReasons            :
CustomPolicy                     :
AuthenticationTransformConstants :
DHGroup                          :
CipherTransformConstants         :
EncryptionMethod                 :
IntegrityCheckMethod             :
PfsGroup                         :
```

This example retrieves all of the S2S VPN interfaces and displays the interfaces in list format.

### EXAMPLE 3
```
PS C:\>Get-VpnS2SInterface -Name edge1
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet
----                 -----------          -----------  --------------- ----------
edge1                {131.107.0.2}        True         Disconnected    {10.0.0.0/24:100}
```

This example retrieves details of interface named edge1.

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

### -Name
Specifies the name of the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ElementName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies an ID, as a string, for a routing domain.
The ID of a routing domain is a user-defined alphanumeric string.
Do not use this parameter with the **Name** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

Required: False
Position: 2
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

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#VpnS2SInterface

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

[Set-VpnS2SInterface](./Set-VpnS2SInterface.md)

