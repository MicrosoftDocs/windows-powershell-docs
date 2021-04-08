---
author: Kateyanne
external help file: NetWNV_Cmdlets.xml
manager: dansimp
Module Name: NetWNV
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/netwnv/get-netvirtualizationglobal?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetVirtualizationGlobal

## SYNOPSIS
Gets per-host global information for a Network Virtualization module.

## SYNTAX

```
Get-NetVirtualizationGlobal [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-UseExternalRouter <Boolean[]>]
```

## DESCRIPTION
The **Get-NetVirtualizationGlobal** cmdlet gets per-host global configuration and states of a hv_win8_1 Network Virtualization module.
For more information about Network Virtualization, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

## EXAMPLES

### Example 1: Get external router value
```
PS C:\>Get-NetVirtualizationGlobal

UseExternalRouter : False
```

This command displays whether the Network Virtualization module on the current host uses external routers for cross-network traffic.

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

### -UseExternalRouter
Specifies an array of Boolean values.
The values indicate whether the Network Virtualization module directs virtual machine (VM) cross-subnet traffic to external routers configured with Customer Routes for hv_win8_2 Network Visualization.

```yaml
Type: Boolean[]
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

## NOTES

## RELATED LINKS

[Set-NetVirtualizationGlobal](./Set-NetVirtualizationGlobal.md)

