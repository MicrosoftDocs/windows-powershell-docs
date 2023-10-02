---
external help file: MPIO_Cmdlets.xml
Module Name: MPIO
online version: https://learn.microsoft.com/powershell/module/mpio/get-msdsmglobaldefaultloadbalancepolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-MSDSMGlobalDefaultLoadBalancePolicy

## SYNOPSIS
Gets the default load balance policy for MPIO devices.

## SYNTAX

```
Get-MSDSMGlobalDefaultLoadBalancePolicy
```

## DESCRIPTION
The **Get-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet gets the default load balance policy for Microsoft Multipath I/O (MPIO) devices.
You can use the **Set-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet to change the policy.
Microsoft Device Specific Module (MSDSM) applies this policy only to devices that it claims after you set the policy.

The cmdlet returns a string that contains one of these values: 

- None.
No currently configured default load balance policy.
- FOO.
Fail Over Only. 
- RR.
Round Robin.
- LQD.
Least Queue Depth.
- LB.
Least Blocks.

## EXAMPLES

### Example 1: Get load balance policy
```
PS C:\> Get-MSDSMGlobalDefaultLoadBalancePolicy 
RR
```

This command gets the global default load balance policy, in this case, RR for round robin.

## PARAMETERS

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Set-MSDSMGlobalDefaultLoadBalancePolicy](./Set-MSDSMGlobalDefaultLoadBalancePolicy.md)

