---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 12ED2919-A1F8-4108-9135-7F14435083FE
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-DnsServerSetting

## SYNOPSIS
Retrieves DNS server settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DnsServerSetting [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DnsServerSetting [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
 [-All]
```

## DESCRIPTION
The **Get-DnsServerSettings** cmdlet retrieves basic Domain Name System (DNS) server settings; that is, the default parameter set.
To get advanced DNS server settings, use the **All** parameter.

## EXAMPLES

### Example 1: Get all DNS server settings
```
PS C:\> Get-DnsServerSetting -All
ComputerName                            : WIN-OLPN33S5Q3M.mytest.contoso.com

MajorVersion                            : 6

MinorVersion                            : 2

BuildNumber                             : 8230

IsReadOnlyDC                            : False

EnableDnsSec                            : True

EnableIPv6                              : True

EnableOnlineSigning                     : True

NameCheckFlag                           : 2

AddressAnswerLimit                      : 0

XfrConnectTimeout(s)                    : 30

BootMethod                              : 3

AllowUpdate                             : True

UpdateOptions                           : 783

DsAvailable                             : True

DisableAutoReverseZone                  : False

AutoCacheUpdate                         : False

RoundRobin                              : True

LocalNetPriority                        : True

StrictFileParsing                       : False

LooseWildcarding                        : False

BindSecondaries                         : False

WriteAuthorityNS                        : False

ForwardDelegations                      : False

AutoConfigFileZones                     : 1

EnableDirectoryPartitions               : True

RpcProtocol                             : 5

EnableVersionQuery                      : 0

EnableDuplicateQuerySuppression         : True

LameDelegationTTL                       : 00:00:00

AutoCreateDelegation                    : 2

AllowCnameAtNs                          : True

RemoteIPv4RankBoost                     : 5

RemoteIPv6RankBoost                     : 0

EnableRsoForRodc                        : True

MaximumRodcRsoQueueLength               : 300

MaximumRodcRsoAttemptsPerCycle          : 100

OpenAclOnProxyUpdates                   : True

NoUpdateDelegations                     : False

EnableUpdateForwarding                  : False

MaxResourceRecordsInNonSecureUpdate     : 30

EnableWinsR                             : True

LocalNetPriorityMask                    : 255

DeleteOutsideGlue                       : False

AppendMsZoneTransferTag                 : False

AllowReadOnlyZoneTransfer               : False

MaximumUdpPacketSize                    : 4000

TcpReceivePacketSize                    : 65536

EnableSendErrorSuppression              : True

SelfTest                                : 4294967295

XfrThrottleMultiplier                   : 10

SilentlyIgnoreCnameUpdateConflicts      : False

EnableIQueryResponseGeneration          : False

SocketPoolSize                          : 2500

AdminConfigured                         : True

SocketPoolExcludedPortRanges            : {}

ForestDirectoryPartitionBaseName        : ForestDnsZones

DomainDirectoryPartitionBaseName        : DomainDnsZones

ServerLevelPluginDll                    :

EnableRegistryBoot                      :

PublishAutoNet                          : False

QuietRecvFaultInterval(s)               : 0

QuietRecvLogInterval(s)                 : 0

ReloadException                         : False

SyncDsZoneSerial                        : 2

EnableDuplicateQuerySuppression         : True

SendPort                                : Random

MaximumSignatureScanPeriod              : 2.00:00:00

MaximumTrustAnchorActiveRefreshInterval : 15.00:00:00

ListeningIPAddress                      : {172.23.90.136}

AllIPAddress                            : {172.23.90.136}
```

This command gets all settings of a DNS server.

## PARAMETERS

### -All
Gets all DNS server settings.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a DNS server.
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

```yaml
Type: String
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSetting

## NOTES

## RELATED LINKS

[Set-DnsServerSetting](./Set-DnsServerSetting.md)

