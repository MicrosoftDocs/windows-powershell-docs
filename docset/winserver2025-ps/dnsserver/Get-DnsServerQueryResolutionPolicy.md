---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerQueryResolutionPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverqueryresolutionpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerQueryResolutionPolicy
---

# Get-DnsServerQueryResolutionPolicy

## SYNOPSIS
Gets policies for query resolution from a DNS server.

## SYNTAX

### Server (Default)
```
Get-DnsServerQueryResolutionPolicy [[-Name] <String>] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Zone
```
Get-DnsServerQueryResolutionPolicy [[-Name] <String>] [-ComputerName <String>] [-ZoneName] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerQueryResolutionPolicy** cmdlet gets policies for query resolution from a Domain Name System (DNS) server.
Specify a zone by name to get zone level policies.
If you do not specify a zone, this cmdlet gets server level policies.

## EXAMPLES

### Example 1: Get all zone level policies
```
PS C:\> Get-DnsServerQueryResolutionPolicy -ZoneName "contoso.com" | Format-List *
```

This command gets all the zone level policies for the zone named contoso.com.
The command uses the **Format-List** cmdlet to control the appearance of the output.
For more information, type `Get-Help Format-List`.

### Example 2: Get a specific zone level policy
```
PS C:\> Get-DnsServerQueryResolutionPolicy -Name "NorthAmericaPolicy" -ZoneName "contoso.com" | Format-List *
Action                : Allow
AppliesOn             : QueryProcessing
Condition             : And
Content               : {DnsServerPolicyContent}
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Zone
Name                  : NorthAmericaPolicy
ProcessingOrder       : 1
ZoneName              : contoso.com
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command gets the zone level policy named NorthAmericaPolicy in the domain named contoso.com.

### Example 3: Get all server level policies
```
PS C:\> Get-DnsServerQueryResolutionPolicy | Format-List *
Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : DropPolicy
ProcessingOrder       : 1
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : DropPolicyMalicious
ProcessingOrder       : 2
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : DropPolicyQType
ProcessingOrder       : 3
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Allow
AppliesOn             : Recursion
Condition             : And
Content               : {DnsServerPolicyContent}
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : SplitBrainPolicy
ProcessingOrder       : 1
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command gets all the server level policies.

### Example 4: Get a specific server level policy
```
PS C:\> Get-DnsServerQueryResolutionPolicy -Name "DropPolicy"
Name                                               ProcessingOrder                                    IsEnabled                                         Action
----                                               ---------------                                    ---------                                         ------
DropPolicy                                         1                                                  True                                              Ignore
```

This command gets the server level policy named DropPolicy.

### Example 5: Display all server level and zone level policies
```
PS C:\> $DnsServer = Get-DnsServer
PS C:\> $DnsServer.ServerPolicies | Format-List *
Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : DropPolicy
ProcessingOrder       : 1
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : DropPolicyMalicious
ProcessingOrder       : 2
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               :
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : DropPolicyQType
ProcessingOrder       : 3
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Allow
AppliesOn             : Recursion
Condition             : And
Content               : {DnsServerPolicyContent}
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : SplitBrainPolicy
ProcessingOrder       : 1
ZoneName              :
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Allow
AppliesOn             : QueryProcessing
Condition             : And
Content               : {DnsServerPolicyContent}
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Zone
Name                  : AmericaPolicy
ProcessingOrder       : 1
ZoneName              : contoso.com
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Allow
AppliesOn             : QueryProcessing
Condition             : And
Content               : {DnsServerPolicyContent}
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Zone
Name                  : EuropePolicy
ProcessingOrder       : 2
ZoneName              : contoso.com
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

Action                : Allow
AppliesOn             : QueryProcessing
Condition             : And
Content               : {DnsServerPolicyContent, DnsServerPolicyContent}
Criteria              : {DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Zone
Name                  : LBPolicy
ProcessingOrder       : 3
ZoneName              : contoso.com
PSComputerName        :
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

The first command gets configuration settings for the current DNS server by using Get-DnsServer cmdlet, and then stores those values in the **$DnsServer** variable.

The second command passes the **ServerPolicies** property of each object stored in **$DnsServer** to **Format-List** by using the pipeline operator.
This example displays both server level and zone level policies.

### Example 6: Display the criteria in a DNS policy
```
PS C:\> $Policy = Get-DnsServerQueryResolutionPolicy -Name "SamplePolicy" -ZoneName "contoso.com"
PS C:\> $Policy.Criteria
```

The first command gets a policy object, and then stores it in the $Policy variable.

The second command displays the CriteriaType and Criteria in $Policy.

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

### -Name
Specifies the name of the policy to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### -ZoneName
Specifies the name of a DNS zone from which to get the zone level policy.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPolicy[]

## NOTES

## RELATED LINKS

[Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)

[Remove-DnsServerQueryResolutionPolicy](./Remove-DnsServerQueryResolutionPolicy.md)

[Set-DnsServerQueryResolutionPolicy](./Set-DnsServerQueryResolutionPolicy.md)

[Get-DnsServer](./Get-DnsServer.md)

[Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)

