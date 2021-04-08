---
author: Kateyanne
external help file: MPIO_Cmdlets.xml
manager: dansimp
Module Name: MPIO
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/mpio/set-msdsmglobaldefaultloadbalancepolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-MSDSMGlobalDefaultLoadBalancePolicy

## SYNOPSIS
Sets the default load balance policy for MPIO devices.

## SYNTAX

```
Set-MSDSMGlobalDefaultLoadBalancePolicy [-Policy] <String>
```

## DESCRIPTION
The **Set-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet sets the default load balance policy for Microsoft Multipath I/O (MPIO) devices.
Microsoft Device Specific Module (MSDSM) applies this policy only to devices that it claims after you set the policy.

Use the **Get-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet to see the current default policy.

## EXAMPLES

### Example 1: Set round robin as default policy
```
PS C:\> Set-MSDSMGlobalLoadBalancePolicy -Policy RR
```

This command sets the default load balance policy to round robin.

### Example 2: Clear default policy
```
PS C:\>Set-MSDSMGlobalLoadBalancePolicy -Policy None
```

This command clears any current configured default load balance policy.

## PARAMETERS

### -Policy
Specifies a default value for load balance policy.
The acceptable values for this parameter are:

- None.
Clears any currently configured default load balance policy.
- FOO.
Fail Over Only. 
- RR.
Round Robin.
- LQD.
Least Queue Depth.
- LB.
Least Blocks.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### System.String

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MSDSMGlobalDefaultLoadBalancePolicy](./Get-MSDSMGlobalDefaultLoadBalancePolicy.md)

