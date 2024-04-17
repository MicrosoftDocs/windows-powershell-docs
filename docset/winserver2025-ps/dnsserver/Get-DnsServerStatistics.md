---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerStatistics_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverstatistics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerStatistics
---

# Get-DnsServerStatistics

## SYNOPSIS
Retrieves DNS server statistics or statistics for zones.

## SYNTAX

### ServerStatistics (Default)
```
Get-DnsServerStatistics [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ZoneStatistics
```
Get-DnsServerStatistics [-ComputerName <String>] [-Clear] -ZoneName <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerStatistics** cmdlet retrieves statistics of a Domain Name System (DNS) server.
If the *ZoneName* parameter is specified, this cmdlet gets statistics for the zones specified by that parameter.
If the *ZoneName* parameter is not specified, the cmdlet gets aggregated server level statistics.

If the *Clear* parameter is specified along with the *ZoneName* parameter, the statistics for the specified zone will also be cleared.

## EXAMPLES

### Example 1: Get server statistics for a the local DNS server
```
PS C:\> Get-DnsServerStatistics
```

This command gets server statistics for the local DNS server.

### Example 2: Get server statistics for a specific zone
```
PS C:\> Get-DnsServerStatistics -ZoneName "contoso.com"
```

This command gets the statistics for the DNS zone named contoso.com.

### Example 3: Clear statistics for a specific zone
```
PS C:\> Get-DnsServerStatistics -ZoneName "contoso.com" -Clear
```

This command gets the current zone statistics and resets the statistics counter for the DNS zone named contoso.com.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Clear
Indicates that the cmdlet clears statistics for the zones that you specify in the *ZoneName* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: ZoneStatistics
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
Aliases: Cn

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

### -ZoneName
Specifies an array of names of DNS zones for which to get DNS statistics.
This parameter is mandatory for the ZoneStatistics parameter set.

```yaml
Type: String[]
Parameter Sets: ZoneStatistics
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## OUTPUTS

### DNSServer01.Infrastructure.CimInstance#DnsServerStatistics
**CacheStatistics** contains: FailedFreePasses,  PassesRequiringAggressiveFree, PassesWithNoFrees, and SuccessfulFreePasses.

**DatabaseStatistics** contains: NodeInUse, NodeMemory, NodeReturn, and NodeUsed.

**DnssecStatistics** contains:  FailedValidations,  RecursionFailures, and SuccessfulValidations.

**DsStatistics** contains: DsNodesAdded, DsNodesDeleted, DsNodesLoaded, DsNodesModified, DsNodesTombstoned, DsRecordsAdded, DsRecordsLoaded, DsRecordsReplaced, DsSerialWrites, DsTombstonesRead, DsTotalNodesRead, DsTotalRecordsRead, DsUpdateNodesRead, DsUpdateRecordsRead, DsUpdateSearches, DsWriteSuppressed, DsWriteType, FailedDeleteDsEntries, FailedLdapAdd, FailedLdapModify, FailedReadRecords, LdapReconnects, LdapSearchTime, LdapTimedWrites, LdapWriteAverage, LdapWriteBucket0, LdapWriteBucket1, LdapWriteBucket2, LdapWriteBucket3, LdapWriteBucket4, LdapWriteBucket5, LdapWriteMax, LdapWriteTimeTotal, PollingPassesWithDsErrors, UpdateAdmin, UpdateAgingOff, UpdateAgingOn, UpdateAginRefresh, UpdateAutoConfig, UpdateLists, UpdateNodes, UpdatePacket, UpdateRecordChange, UpdateScavenge, UpdatePacketPrecon, UpdateSuppressed, UpdateTombstones, and UpdateWrites.

**ErrorStatistics** contains: BadKey, BadSig, BadTime, FormError, Max, NoError, NotAuthoritative, NotImpl, NotZone, NxDomain, NxRRSet, Refused, ServFail, UnknownError, YxDomain, and YxRRSet.

**MasterStatistics** contains: AxfrLimit, AxfrRequest, AxfrSuccess, Failure, FormError, IxfrAxfr, IxfrNoVersion, IxfrRequest, IxfrTcpRequest, IxfrTcpSuccess, IxfrUdpForceAxfr, IxfrUdpForceTcp, IxfrUdpRequest, IxfrUdpSuccess, IxfrUpdateSuccess, NameError, NotifySent, Refused, RefuseLoading, RefuseNotAuth, RefuseReadOnly, RefuseSecurity, RefuseServerFailure, RefuseShutdown, RefuseZoneLocked, Request, and StubAxfrRequest.

**MemoryStatistics** contains: Alloc, Free, Memory, MemTags, StdBlockAlloc, StdBlockFreeList, StdBlockFreeListMemory, StdBlockInUse, StdBlockMemory, StdBlockReturn, StdBlockUsed, StdInUse, StdMemory, StdReturn, StdToHeapAlloc, StdToHeapFree, StdToHeapMemory, and StdUsed.

**NetBiosStatistics** contains: NbstatAlloc, NbstatFree, NbstatInFreeList, NbstatInUse, NbstatMemory, NbstatNetAllocs, NbstatReturn, NbstatUsed, and PSComputerName.

**PacketStatistics** contains: PacketsForNsListInUse, PacketsForNsListReturned, PacketsForNsListUsed, RecursePacketReturn, RecursePacketUsed, TcpAlloc, TcpFree, cpMemory, TcpNetAllocs, UdpAlloc, UdpFree, UdpInFreeList, UdpInUse, UdpMemory, UdpNetAllocs, UdpQueryReturn, UdpResponseReturn, UdpReturn, and UdpUsed.

**PrivateStatistics** contains: SecBigTimeSkewBypass, TcpConnect, TcpDisconnect, TcpQuery, UdpConnResetRetryOverflow, UdpConnResets, UdpErrorMessageSize, UdpGQCSConnReset, UdpGQCSFailure, UdpGQCSFailureWithContext, UdpIndicateRecvFailures, UdpRecvFailure, UdpRestartRecvOnSockets, UdpSocketPnpDelete, ZoneLoadInit, and PSComputerName.

**Query2Statistics** contains: Notify, Standard, TKeyNego, TotalQueries, TypeA, TypeAll, TypeAxfr, TypeIxfr, TypeMx, TypeNs, TypeOther, TypePtr, TypeSoa, TypeSrv, and Update.

**QueryStatistics** contains: TcpClientConnections, TcpQueries, TcpQueriesSent, TcpResponses, TcpResponsesReceived, UdpQueries, UdpQueriesSent, UdpResponses, and UdpResponsesReceived.

**RecordStatistics** contains: CacheCurrent, CacheTimeouts, CacheTotal, InUse, Memory, Return, SlowFreeFinished, SlowFreeQueued, and Used.

**RecursionStatistics** contains: AdditionalRecursed, CacheLockingDiscards, CacheUpdateAlloc, CacheUpdateFailure, CacheUpdateFree, CacheUpdateResponse, CacheUpdateRetry, ContinueCurrentLookup, ContinueCurrentRecursion, ContinueNextLookup, DiscardedDuplicateQueries, DuplicateCoalesedQueries, FailureReachAuthority, FailureReachPreviousResponse, FinalTimeoutExpired, FinalTimeoutQueued, Forwards, GnzLocalQuery, GnzRemoteQuery, GnzRemoteResponse, GnzRemoteResponseCacheFailure, GnzRemoteResponseCacheSuccess, LookupPasses, OriginalQuestionRecursed, PartialFailure, QueriesRecursed, RecursePassFailure, RecursionFailure, ReferalPasses, ResponseAnswer, ResponseAuthoritative, ResponseBadPacket, ResponseDelegation, ResponseEmpty, ResponseFromForwarder, ResponseNameError, ResponseNonZoneData, ResponseNotAuthoritative, ResponseRCode, Responses, ResponsesMismatched, ResponsesUnmatched, ResponseUnsecure, ResumeSuspendedQuery, Retries, RootNsQuery, RootNsResponse, SendResponseDirect, Sends, ServerFailure, SuspendedQuery, TcpConnect, TcpDisconnect, TcpQuery, TcpResponse, TcpTry, TimedoutQueries, and TotalQuestionsRecursed.

**SecondaryStatistics** contains: AxfrInvalid, AxfrRefused, AxfrRequest, AxfrResponse, AxfrSuccess, IxfrTcpAxfr, IxfrTcpFormError, IxfrTcpInvalid, IxfrTcpRefused, IxfrTcpRequest, IxfrTcpResponse, IxfrTcpSuccess, IxfrUdpFormError, xfrUdpInvalid, IxfrUdpNewPrimary, IxfrUdpNoUpdate, IxfrUdpRefused, IxfrUdpRequest, IxfrUdpResponse, IxfrUdpSuccess, IxfrUdpUseAxfr, IxfrUdpUseTcp, IxfrUdpWrongServer, NotifyCurrentVersion, NotifyInvalid, NotifyMasterUnknown, NotifyNewVersion, NotifyNonPrimary, NotifyNoVersion, NotifyOldVersion, NotifyPrimary, NotifyReceived, SoaRequest, SoaResponse, SoaResponseInvalid, StubAxfrInvalid, StubAxfrRefused, StubAxfrRequest, StubAxfrResponse, and StubAxfrSuccess.

**SecurityStatistics** contains: SecurityContextCreate, SecurityContextDequeue, SecurityContextFree, SecurityContextQueue, SecurityContextQueueInNego, SecurityContextQueueInNegoComplete, SecurityContextQueueLength, SecurityContextTimeout, SecurityPackAlloc, SecurityPackFree, SecurityTKeyBadTime, SecurityTKeyInvalid, SecurityTSigBadKey, SecurityTSigEcho, SecurityTSigFormError, SecurityTSigVerifyFailed, and SecurityTSigVerifySuccess.

**TimeoutStatistics** contains: ActiveRecord, AlreadyInSystem, ArrayBlocksCreated, ArrayBlocksDeleted, CanNotDelete, Checks, DelayedFreesExecuted, DelayedFreesExecutedWithFunction, DelayedFreesQueued, DelayedFreesQueuedWithFunction, Deleted, RecentAccess, SetDirect, SetFromChildDelete, SetFromDereference, and SetTotal.

**TimeStatistics** contains: LastClearTime, ServerStartTime, TimeElapsedSinceLastClearedStatistics, TimeElapsedSinceLastClearedStatisticsBetweenRestart, TimeElapsedSinceServerStart, and TimeElapsedSinceServerStartBetweenRestart.

**UpdateStatistics** contains: Completed, DsSuccess, DsWriteFailure, Empty, FormError, ForwardInQueue, ForwardResponses, Forwards, ForwardTimeouts, InQueue, NoOps, NotAuthoritative, NotImplemented, NotZone, NxDomain, NxRRset, Queued, Received, Refused, RefusedAccessDenied, RefusedNonSecure, Rejected, SecureDsWriteFailure, SecureFailure, SecureSuccess, TcpForwards, Timeout, UpdateType, YxDomain, and YxRRset.

**WinsStatistics** contains: WinsLookups, WinsResponses, WinsReverseLookups, and WinsReverseResponses.

### DNSServer01.Infrastructure.CimInstance#DnsServerStatistics
This cmdlet outputs this object for the ZoneStatistics parameter set.
This object contains the following properties:

**Name:** Name of the zone.

**StatsCollectionStartTime** contains the time at which the zone statistics collection started.

**ZoneQueryStatistics** contains: QueriesFailure, QueriesResponded, QueriesNameError.
and QueriesReceived.
Query information is provided for the following resource record types: A, AAAA, PTR, CNAME, MX, AFSDB, ATMA, DHCID, DNAME, HINFO, ISDN, MG (Mail Group), MB (Mail Box), MINFO (Mail Box Information), NAPTR (Naming Authority Pointer), NXT (Next Domain), KEY (Public Key), MR (Renamed Mailbox), RP (Responsible Person), RT (Route Through), SRV (Service Location), SIG (Signature), TXT (Text), WKS (Well Known Services), X.25, DNSKEY, DS, NS, and SOA.
The information for other records is collected under the record type OTHER.
The statistics for the record type ANY are collected under the record type ALL.

**ZoneTransferStatistics** contains: SuccessSent, ResponseReceived, RequestSent, RequestReceived, SuccessReceived, and TransferType: IXFR or AXR.

**ZoneUpdateStatistics** contains: DynamicUpdateReceived and DynamicUpdateRejected.

## NOTES

## RELATED LINKS

[Clear-DnsServerStatistics](./Clear-DnsServerStatistics.md)

