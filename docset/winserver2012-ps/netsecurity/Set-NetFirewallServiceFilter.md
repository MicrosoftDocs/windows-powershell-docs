---
external help file: NetSecurity_Function.xml
Module Name: NetSecurity
online version: https://docs.microsoft.com/powershell/module/netsecurity/set-netfirewallservicefilter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetFirewallServiceFilter

## SYNOPSIS
Modifies service filter objects, thereby modifying the service conditions of the firewall rules.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetFirewallServiceFilter [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-PolicyStore <String>] [-Service <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetFirewallServiceFilter [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-Service <String>]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetFirewallServiceFilter** cmdlet modifies the service conditions associated with the input firewall rules.

See the Get-NetFirewallServiceFilter cmdlet for more information on the security filters.

To modify the service conditions, two methods can be used starting with the service filters returned by Get-NetFirewallServiceFilter cmdlet. 

 -- The network firewall service filter objects can be piped into the Get-NetFirewallRule cmdlet.
The Get-NetFirewallRule cmdlet returns the rules associated with the filters and piped the rules into the Set-NetFirewallRule cmdlet, which configures the service properties. 

 -- Alternatively, piping the network firewall service filter objects directly to this cmdlet modifies the **Service** parameter of the rules.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$nfServiceFilter = Get-FirewallRule -DisplayName "Wireless Portable Devices" | Get-NetFirewallServiceFilter



PS C:\>Set-NetFirewallServiceFilter -Service Any -InputObject $nfServiceFilter


This cmdlet can be run using only the pipeline.
PS C:\>Get-FirewallRule -DisplayName "Wireless Portable Devices" | Get-NetFirewallServiceFilter | Set-NetFirewallServiceFilter -Service Any


This cmdlet can be run without the pipeline.
PS C:\>Set-NetFirewallRule -DisplayName "Wireless Portable Devices" -Service Any
```

This example modifies the user field of a particular firewall rule.

### EXAMPLE 2
```
PS C:\>$nfServiceFilter = Get-NetFirewallRule -Group "@FirewallAPI.dll,-30502" | Get-NetFirewallServiceFilter -Service Any



PS C:\>Set-NetFirewallServiceFilter -Service Ssdpsrv -InputObject $nfServiceFilter


This cmdlet can be run using only the pipeline.
PS C:\>Get-NetFirewallRule -Group "@FirewallAPI.dll,-30502" | Get-NetFirewallServiceFilter -Service Any | Set-NetFirewallServiceFilter -Service Ssdpsrv
```

This example modifies the service associated with firewall rules in a specified group.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Specifies the network GPO from which to retrieve the rules to be modified. 

This parameter is used in the same way as the **PolicyStore** parameter.
When modifying GPOs in Windows PowerShell®, each change to a GPO requires the entire GPO to be loaded, modified, and saved back.
On a busy Domain Controller (DC), this can be a slow and resource-heavy operation.
A GPO Session loads a domain GPO onto the local computer and makes all changes in a batch, before saving it back.
This reduces the load on the DC and speeds up the Windows PowerShell cmdlets.
To load a GPO Session, use the Open-NetGPO cmdlet.
To save a GPO Session, use the Save-NetGPO cmdlet.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru


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

### -PolicyStore
Specifies the policy store from which to retrieve the rules to be modified. 

A policy store is a container for firewall and IPsec policy. 
The acceptable values for this parameter are:

 -- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically (during application installation) on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately.
This is the default value. 

 -- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
This is the resultant set of policy (RSOP) for the local computer (the sum of all GPOs that apply to the computer), and the local stores (the PersistentStore, the static Windows service hardening (WSH), and the configurable WSH). 

 ---- GPOs are also policy stores.
Computer GPOs can be specified as follows. 

 ------ `-PolicyStore hostname`. 

 ---- Active Directory GPOs can be specified as follows. 

 ------ `-PolicyStore domain.fqdn.com\GPO_Friendly_Namedomain.fqdn.comGPO_Friendly_Name`. 

 ------ Such as the following. 

 -------- `-PolicyStore localhost`

 -------- `-PolicyStore corp.contoso.com\FirewallPolicycorp.contoso.com\FirewallPolicy`

 ---- Active Directory GPOs can be created using the New-GPO cmdlet or the Group Policy Management Console. 

 -- RSOP: This read-only store contains the sum of all GPOs applied to the local computer. 

 -- SystemDefaults: This read-only store contains the default state of firewall rules that ship with Windows Server® 2012. 

 -- StaticServiceStore: This read-only store contains all the service restrictions that ship with Windows Server 2012.
Optional and product-dependent features are considered part of Windows Server 2012 for the purposes of WFAS. 

 -- ConfigurableServiceStore: This read-write store contains all the service restrictions that are added for third-party services.
In addition, network isolation rules that are created for Windows Store application containers will appear in this policy store. 
Note: The Set-NetIPsecRule cmdlet cannot be used to add an object to a policy store.
An object can only be added to a policy store at creation time with the Copy-NetIPsecRule cmdlet or with the New-NetIPsecRule cmdlet.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Specifies the short name of a Windows Server 2012 service to which the firewall rule applies.
If service is not specified, then network traffic generated by any program or service matches this rule. 
Note: Querying for rules with this parameter can only be performed using filter objects.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetServiceFilter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetServiceFilter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Copy-NetIPsecRule](./Copy-NetIPsecRule.md)

[Get-NetFirewallRule](./Get-NetFirewallRule.md)

[Get-NetFirewallServiceFilter](./Get-NetFirewallServiceFilter.md)

[Get-NetIPSecRule](./Get-NetIPsecRule.md)

[New-NetFirewallRule](./New-NetFirewallRule.md)

[New-NetIPSecRule](./New-NetIPsecRule.md)

[Open-NetGPO](./Open-NetGPO.md)

[Save-NetGPO](./Save-NetGPO.md)

[Set-NetFirewallRule](./Set-NetFirewallRule.md)

[Set-NetIPSecRule](./Set-NetIPsecRule.md)

[New-GPO](../grouppolicy/New-GPO.md)

