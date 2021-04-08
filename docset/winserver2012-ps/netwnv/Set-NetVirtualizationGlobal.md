---
author: Kateyanne
external help file: NetWNV_Cmdlets.xml
manager: dansimp
Module Name: NetWNV
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/netwnv/set-netvirtualizationglobal?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetVirtualizationGlobal

## SYNOPSIS
Changes per-host global settings of a Network Virtualization module.

## SYNTAX

```
Set-NetVirtualizationGlobal [-AsJob] [-CimSession <CimSession[]>] [-InputObject <CimInstance[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-UseExternalRouter <Boolean>]
```

## DESCRIPTION
The **Set-NetVirtualizationGlobal** cmdlet changes the per-host global settings of a hv_win8_1 Network Virtualization module.
You can use this cmdlet to change whether to use an external router.
For more information about Network Virtualization, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can use the Get-NetVirtualizationGlobal cmdlet to obtain global settings objects to modify.

## EXAMPLES

### Example 1: Direct VM traffic to external routers
```
PS C:\>Set-NetVirtualizationGlobal -UseExternalRouter $True
```

This command configures the Network Virtualization module on the current host to direct VM cross-subnet traffic to external routers.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Indicates whether the Network Virtualization module directs virtual machine (VM) cross-subnet traffic to external routers configured with Customer Routes for hv_win8_2 Network Visualization.

```yaml
Type: Boolean
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

[Get-NetVirtualizationGlobal](./Get-NetVirtualizationGlobal.md)

