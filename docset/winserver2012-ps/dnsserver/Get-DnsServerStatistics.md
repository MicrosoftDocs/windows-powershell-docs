---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/get-dnsserverstatistics?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DnsServerStatistics

## SYNOPSIS
Retrieves DNS server statistics.

## SYNTAX

```
Get-DnsServerStatistics [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DnsServerStatistics** cmdlet retrieves statistics of a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Get server statistics for a DNS server
```
PS C:\> Get-DnsServerStatistics
```

This command gets server statistics for the local DNS server.

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

### 
class DNS_statistic

{

string DnsServerName; // Indicates the FQDN or IP address of a DNS Server.

string CollectionName;

uint32 CollectionId; // Numeric representation of **CollectionName**.
string Name; /

uint32 Value;

string StringValue;

};

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

## NOTES

## RELATED LINKS

[Clear-DnsServerStatistics](./Clear-DnsServerStatistics.md)

