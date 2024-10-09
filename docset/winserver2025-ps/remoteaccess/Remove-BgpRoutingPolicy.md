---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRoutingPolicy_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-bgproutingpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BgpRoutingPolicy
---

# Remove-BgpRoutingPolicy

## SYNOPSIS
Removes routing policies from the policy store.

## SYNTAX

```
Remove-BgpRoutingPolicy [-Name] <String[]> [-RoutingDomain <String>] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BgpRoutingPolicy** cmdlet removes Border Gateway Protocol (BGP) routing policies from the policy store.
Specify the names of the routing policies to remove.
When you remove a routing policy, the BGP router no longer uses the policy to learn and distribute routing information between autonomous systems (AS).

## EXAMPLES

### Example 1: Remove BGP routing policies
```
PS C:\> Remove-BgpRoutingPolicy -Name "RTPolicy01", "RTPolicy02"



Confirm
BGP routing policy RTPolicy01, RTPolicy02 could currently be active. Do you want to remove policy and restart
corresponding peerings?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
PS C:\Users\Administrator>
```

This command removes the BGP routing policies named RTPolicy01 and RTPolicy02.
The command prompts the user for confirmation before removing the policies from the policy store.

### Example 2: Remove BGP routing policies without confirmation
```
PS C:\> Get-BgpRoutingPolicy | Remove-BgpRoutingPolicy -Force
```

This command removes all the BGP routing policies from the policy store.
Because the cmdlet uses the **Force** parameter, the cmdlet removes the routing policies without prompting the user for confirmation.

### Example 3: Remove BGP routing policies for a routing domain
```
PS C:\> Remove-BgpRoutingPolicy -Name "RTPolicy04" -RoutingDomain "Rd_001"



Confirm
BGP routing policy RTPolicy04 could currently be active. Do you want to remove policy and restart corresponding
peerings for routing domain Rd_001?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes the routing policy named RTPolicy04 from the BGP router for the routing domain named Rd_001.
The command prompts the user for confirmation before removing the policy from the policy store.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -Name
Specifies an array of names of policies.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PolicyList, PolicyId, PolicyName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies a name, as a string, of a routing domain.
The name of a routing domain is a unique user-defined alphanumeric string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

Required: False
Position: Named
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

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-BgpRoutingPolicy](./Get-BgpRoutingPolicy.md)

[Set-BgpRoutingPolicy](./Set-BgpRoutingPolicy.md)

[Add-BgpRoutingPolicy](./Add-BgpRoutingPolicy.md)

