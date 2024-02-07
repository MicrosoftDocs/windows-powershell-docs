---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerQueryResolutionPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 01/03/2022
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverqueryresolutionpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerQueryResolutionPolicy
---

# Add-DnsServerQueryResolutionPolicy

## SYNOPSIS
Adds a policy for query resolution to a DNS server.

## SYNTAX

### Server (Default)
```
Add-DnsServerQueryResolutionPolicy [-PassThru] [-ComputerName <String>] [-Name] <String> [-Fqdn <String>]
 [-ECS <String>] [-ClientSubnet <String>] [-TimeOfDay <String>] [-TransportProtocol <String>] [-InternetProtocol <String>]
 [[-Action] <String>] [-ApplyOnRecursion] [-ServerInterfaceIP <String>] [-QType <String>]
 [-ProcessingOrder <UInt32>] [[-Condition] <String>] [-RecursionScope <String>] [-Disable]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Zone
```
Add-DnsServerQueryResolutionPolicy [-PassThru] [-ComputerName <String>] [-ZoneName] <String> [-Name] <String>
 [-Fqdn <String>] [-ECS <String>] [-ClientSubnet <String>] [-TimeOfDay <String>] [-TransportProtocol <String>]
 [-InternetProtocol <String>] [[-Action] <String>] [-ServerInterfaceIP <String>] [-QType <String>]
 [-ProcessingOrder <UInt32>] [[-Condition] <String>] [-Disable] [-ZoneScope <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Add-DnsServerQueryResolutionPolicy [-PassThru] [-ComputerName <String>] [-InputObject] <CimInstance>
 [[-ZoneName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerQueryResolutionPolicy** cmdlet adds a policy for query resolution to a Domain Name System (DNS) server.
A policy determines the resolution of queries based on criteria that you specify in the policy.

A policy consists of criteria, action, and scopes.

The criteria are a logical combination of client subnet, server interface IP address, fully qualified domain name (FQDN), Internet Protocol (IPv4/IPv6), transport protocol (UDP/TCP), time of day, and query type.

Specify criteria in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).

This cmdlet combines multiple criteria by using the value of the *Condition* parameter as the logical operator.
This parameter takes one of the following values:

- OR.
The policy evaluates criteria as multiple assertions which are logically combined (OR'd).
- AND.
The policy evaluates criteria as multiple assertions which are logically differenced (AND'd).

If a query meets the criteria of a policy, the action is the response that the policy requires.
You can specify ALLOW, DENY, or IGNORE.

If you specify an action of ALLOW in a policy for a server that is authoritative for a query, the policy determines which zone scopes to use to respond to the query and in what ratio.
If the answer for the query is cached, the policy determines which cache scopes to use and in what ratio.
Otherwise, the policy determines which recursion scope to use.

You can create policies for query resolution at either the server level or the zone level.
Server level policies apply on every query that comes to the DNS server.
Zone level policies apply only on the queries that can be resolved from a zone hosted on the DNS server.
Server level policies apply either on the incoming queries or on the recursive outgoing queries.
On the incoming queries, server level policies can only DENY or IGNORE.
The most common use for server level policies is to implement blocked or safe lists.

Recursion policies are a special class of server level policies.
Recursion policies control how the DNS server performs recursion for a query.
Recursion policies apply only when query processing reaches the recursion path.
You can chose a value of DENY or IGNORE for recursion for a set of queries.
Alternatively, you can choose a set of forwarders for a set of queries.
To configure this behavior, specify a recursion scope in the recursion policies.
You can use recursion policies to implement a Split-brain DNS configuration.
In this configuration, the DNS server performs recursion for a set of clients for a query, while the DNS server does not perform recursion for other clients for that query.

Zone level policies apply to the zone in which you create them.
Zone level policies apply only when that zone is found during the query lookup.
You cannot create a zone level policy without a zone.
If you remove a zone, that removal deletes the associated zone level policies.
In a zone level policy, you can specify a value of DENY or IGNORE for a set of queries for records in a zone.
Alternatively, if the action is Allow, zone level policies can decide which zone scopes to use to answer queries and in what ratio.
One use of such zone level policies is application load balancing by means of DNS.

The DNS server applies server level policies first, except for recursion policies.
Then, the DNS server applies zone level policies, and then recursion policies.
Each policy has a precedence value.
You can specify the precedence by using the *ProcessingOrder* parameter.
The DNS server evaluates queries against policies in the order of precedence for each type of policy.

If the criteria of a server level policy match a query, and if the action is DENY, the DNS server returns REFUSED.
If the action is IGNORE, the DNS server drops the query.
If the query does not match any server level policy, and if the server is authoritative for the zone for the query, the server evaluates the query with regard to the zone level policies.

If the criteria of a zone level policy in that zone match a query, and if the action is DENY, the server returns REFUSED.
If the action is IGNORE, the server drops the query.
If the action is ALLOW, the DNS server responds to the query from one of the zone scopes specified in the policy.
You can chose to distribute the responses from multiple zone scopes in a particular ratio.

For policy processing, the cache is treated as a zone.
The DNS server repeats the process for zone level policies for the cache.

If the server is not authoritative for the zone for which the query has been received, and the response is not found in the cache or the specified cache scope, the DNS server matches the query against the server level recursion policies in order of their precedence.
If the criteria of a recursion policy match a query and the action is DENY, the DNS server returns REFUSED.
If the action is IGNORE, the DNS server drops the query.
If the action is ALLOW, the DNS server gets settings from the configured recursion scope.
Based on those settings, the DNS server gets the response for the query by using recursion.

## EXAMPLES

### Example 1: Create traffic management policies
```
The first two commands create client subnets by using the **Add-DnsServerClientSubnet** cmdlet. The client subnets are for clients in North America and clients in Europe.
PS C:\> Add-DnsServerClientSubnet -Name "NorthAmericaSubnet" -IPv4Subnet "172.21.33.0/24" -PassThru
PS C:\> Add-DnsServerClientSubnet -Name "EuropeSubnet" -IPv4Subnet "172.17.44.0/24" -PassThru
Name                                             IPV4Subnet                                       IPV6Subnet
----                                             ----------                                       ----------
NorthAmericaSubnet                                    {172.21.33.0/24}
EuropeSubnet                                     {172.17.44.0/24}

The next two commands create zone scopes for North America and for Europe by using the **Add-DnsServerZoneScope** cmdlet.
PS C:\> Add-DnsServerZoneScope -ZoneName "Contoso.com" -Name "NorthAmericaZoneScope" -PassThru
PS C:\> Add-DnsServerZoneScope -ZoneName "Contoso.com" -Name "EuropeZoneScope" -PassThru
FileName       : NorthAmericaZoneScope.dns
ZoneName       : contoso.com
ZoneScope      : NorthAmericaZoneScope
PSComputerName :


FileName       : EuropeZoneScope.dns
ZoneName       : contoso.com
ZoneScope      : EuropeZoneScope
PSComputerName :

The next two commands add resource records for the zone Contoso.com by using the **Add-DnsServerResourceRecord** cmdlet. The name for both records is the same, career, but the two records point to different addresses. The records also have different scopes.
PS C:\> Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "career" -IPv4Address "172.17.97.97" -ZoneScope "EuropeZoneScope" -PassThru
PS C:\> Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "career" -IPv4Address "172.21.21.21" -ZoneScope "NorthAmericaZoneScope" -PassThru
DistinguishedName : career
HostName          : career
RecordClass       : IN
RecordData        : DnsServerResourceRecordA
RecordType        : A
Timestamp         :
TimeToLive        : 01:00:00
PSComputerName    :


DistinguishedName : career
HostName          : career
RecordClass       : IN
RecordData        : DnsServerResourceRecordA
RecordType        : A
Timestamp         :
TimeToLive        : 01:00:00
PSComputerName    :

The final two commands create two policies. The policies allow queries for members of different subnets. The policies differ in scope, so that some clients receive one response to a query, while other clients receive a different response to the same query.
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "NorthAmericaPolicy" -Action ALLOW -ClientSubnet "eq,NorthAmericaSubnet" -ZoneScope "NorthAmericaZoneScope,1" -ZoneName "Contoso.com" -PassThru
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "EuropePolicy" -Action ALLOW -ClientSubnet "eq,EuropeSubnet" -ZoneScope "EuropeZoneScope,1" -ZoneName contoso.com -PassThru
Action          : Allow
AppliesOn       : QueryProcessing
Condition       : And
Content         : {DnsServerPolicyContent}
Criteria        : {DnsServerPolicyCriteria}
IsEnabled       : True
Level           : Zone
Name            : NorthAmericaPolicy


ProcessingOrder : 1
ZoneName        : contoso.com
PSComputerName  :


Action          : Allow
AppliesOn       : QueryProcessing
Condition       : And
Content         : {DnsServerPolicyContent}
Criteria        : {DnsServerPolicyCriteria}
IsEnabled       : True
Level           : Zone
Name            : EuropePolicy
ProcessingOrder : 2
ZoneName        : contoso.com
PSComputerName  :
```

This example shows how to create traffic management policies to direct the customers from a certain subnet to a North American datacenter and from another subnet to a European datacenter.

### Example 2: Allow queries for a zone
```
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "LBPolicy" -ZoneName "contoso.com" -Action ALLOW -FQDN "EQ,career.contoso.com" -ZoneScope "NorthAmericaZoneScope,7;EuropeZoneScope,3" -PassThru
Name                                               ProcessingOrder                                    IsEnabled                                         Action
----                                               ---------------                                    ---------                                         ------
LBPolicy                                           3                                                  True                                              Allow
```

This command creates a policy named LBPolicy to allow queries for the contoso.com zone.
The policy includes two weighted zone scopes.

### Example 3: Add policies from one server to another
```
PS C:\> $Policies = Get-DnsServerQueryResolutionPolicy -ComputerName "Server01"
PS C:\> $Policies | Add-DnsServerQueryResolutionPolicy -ComputerName "Server07" -ThrottleLimit 1
```

The first command gets all the server level policies on the DNS server named Server01, and then stores the properties in the $Policies variable.

The second command adds the policies stored in $Policies to a different DNS server.
This command specifies a value of one (1) for the *ThrottleLimit* parameter.
This value maintains the order of processing policies in the pipeline.

### Example 4: Block queries for a domain
```
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "BlackholePolicy" -Action IGNORE -FQDN "EQ,*.contoso.com" -PassThru | Format-List *
Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : BlackholePolicy
ProcessingOrder       : 1
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command creates a policy that blocks queries from a particular domain.
The command uses the **Format-List** cmdlet to control the appearance of the output.
For more information, type `Get-Help Format-List`.

### Example 5: Block queries from a subnet
```
PS C:\> Add-DnsServerClientSubnet -Name "MaliciousSubnet06" -IPv4Subnet 172.0.33.0/24 -PassThru
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "BlackholePolicyMalicious06" -Action IGNORE -ClientSubnet  "EQ,MaliciousSubnet06" -PassThru | Format-List *
Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : BlackholePolicyMalicious
ProcessingOrder       : 2
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

The first command creates a client subnet named MaliciousSubnet06.

The second command creates a policy to block queries from the subnet named MaliciousSubnet06.
The policy takes an action of IGNORE, which drops those queries.

### Example 6: Block a type of query
```
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "BlackholePolicyQType" -Action IGNORE -QType "EQ,ANY" -PassThru | Format-List *
Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : BlackholePolicyQType
ProcessingOrder       : 3
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command creates a policy to block queries for a particular query type.
The policy drops ANY query.

### Example 7: Allow recursion for internal clients
```
PS C:\> Add-DnsServerRecursionScope -Name "InternalClients" -EnableRecursion $True
PS C:\> Set-DnsServerRecursionScope -Name . -EnableRecursion $False
PS C:\> Add-DnsServerQueryResolutionPolicy -Name "SplitBrainPolicy" -Action ALLOW -ApplyOnRecursion -RecursionScope "InternalClients" -ServerInterfaceIP  "EQ,10.0.0.34" -PassThru
Action          : Allow
AppliesOn       : Recursion
Condition       : And
Content         : {DnsServerPolicyContent}
Criteria        : {DnsServerPolicyCriteria}
IsEnabled       : True
Level           : Server
Name            : SplitBrainPolicy
ProcessingOrder : 1
ZoneName        :
PSComputerName  :
```

The first command creates a recursion scope called InternalClients.
Recursion is enabled for this scope.

The second command modifies the default recursion scope by using the **Set-DnsServerRecursionScope** cmdlet.
The default scope, identified by a dot (.), has recursion disabled.

The final command creates a policy that uses the InternalClients scope.
For that scope, on the specified server interface address, the policy allows recursion.

## PARAMETERS

### -Action
Specifies the action to take if a query matches this policy.
The acceptable values for this parameter are:

- ALLOW.
- DENY.
Respond with SERV_FAIL.
- IGNORE.
Do not respond.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:
Accepted values: ALLOW, DENY, IGNORE

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplyOnRecursion
Indicates that this policy is a server level recursion policy.

Recursion policies are special class of server level policies that control how the DNS server performs recursion for a query.
Recursion policies apply only when query processing reaches the recursion path.

```yaml
Type: SwitchParameter
Parameter Sets: Server
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ClientSubnet
Specifies the client subnet criterion.
This is a client subnet from which the query was sent.
For more information, see **Add-DnsServerClientSubnet**.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the subnet of the request matches one of the EQ values and does not match any of the NE values.

Example criterion: `"EQ,NorthAmerica,Asia,NE,Europe"`

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as an FQDN, host name, or NETBIOS name.

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

### -Condition
Specifies how the policy treats multiple criteria.
The acceptable values for this parameter are:

- OR.
The policy evaluates criteria as multiple assertions which are logically combined (OR'd).
- AND.
The policy evaluates criteria as multiple assertions which are logically differenced (AND'd).

The default value is AND.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:
Accepted values: AND, OR

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Disable
Indicates that this cmdlet disables the policy.
If you do not specify this parameter, the cmdlet creates the policy and enables it.

```yaml
Type: SwitchParameter
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ECS

This parameter is reserved for internal use.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Fqdn
Specifies the FQDN criterion.
This is the FQDN of record in the query.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the FQDN of the request matches one of the EQ values and does not match any of the NE values.
You can include the asterisk (*) as the wildcard character.
For example, `EQ,*.contoso.com,NE,*.fabrikam.com`.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternetProtocol
Specifies the Internet Protocol criterion.
This is the IP version of the query.
Valid values are: IPv4 and IPv6.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the IP address of the request matches one of the EQ values and does not match any of the NE values.

Example criteria: `"EQ,IPv4"` and `"EQ,IPv6"`

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the new policy.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: True
Position: 1
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

### -ProcessingOrder
Specifies the precedence of the policy.
Higher integer values have lower precedence.
By default, this cmdlet adds a new policy as the lowest precedence.

```yaml
Type: UInt32
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QType
Specifies the query type criterion.
This is the type of record that is being queried.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the type of query of the request matches one of the EQ values and does not match any of the NE values.

Example criterion: `"EQ,TXT,SRV;NE,MX"`

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecursionScope
Specifies the scope of recursion.
If the policy is a recursion policy, and if a query matches it, the DNS server uses settings from this scope to perform recursion for the query.

```yaml
Type: String
Parameter Sets: Server
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInterfaceIP
Specifies the IP address of the server interface on which the DNS server listens.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the IP address of the interface matches one of the EQ values and does not match any of the NE values.

Example criteria: `"EQ,10.0.0.1"` and `"NE,192.168.1.1"`

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -TimeOfDay
Specifies the time of day criterion.
This is when the server receives the query.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the time of day of the request matches one of the EQ values and does not match any of the NE values.

Example criterion: `"EQ,10:00-12:00,22:00-23:00"`

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TransportProtocol
Specifies the transport protocol criterion.
This is the transport protocol of the query.
Valid values are: TCP and UDP.
Specify a criterion in the following format:

operator, value01, value02, .
. .
; operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the string.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the transport protocol of the request matches one of the EQ values and does not match any of the NE values.

Example criteria: `"EQ,TCP"` and `"NE,UDP"`

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases:

Required: False
Position: Named
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

### -ZoneName
Specifies the name of a DNS zone on which this cmdlet creates a zone level policy.
The zone must exist on the DNS server.

```yaml
Type: String
Parameter Sets: Zone
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: InputObject
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneScope
Specifies a list of scopes and weights for the zone.
Specify the value as a string in this format:

Scope01, Weight01; Scope02, Weight02;

```yaml
Type: String
Parameter Sets: Zone
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPolicy

## NOTES

## RELATED LINKS

[Get-DnsServerQueryResolutionPolicy](./Get-DnsServerQueryResolutionPolicy.md)

[Remove-DnsServerQueryResolutionPolicy](./Remove-DnsServerQueryResolutionPolicy.md)

[Set-DnsServerQueryResolutionPolicy](./Set-DnsServerQueryResolutionPolicy.md)

[Add-DnsServerClientSubnet](./Add-DnsServerClientSubnet.md)

[Add-DnsServerZoneScope](./Add-DnsServerZoneScope.md)

[Add-DnsServerResourceRecord](./Add-DnsServerResourceRecord.md)

[Set-DnsServerRecursionScope](./Set-DnsServerRecursionScope.md)

[Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)

