---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: FFDA0575-BC77-4953-B73F-16C0B19F6570
manager: dansimp
---

# Disable-NetNatTransitionConfiguration

## SYNOPSIS
Disables the NAT64 configuration on a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-NetNatTransitionConfiguration [-Adapter <CimInstance>] [-AsJob] [-CimSession <CimSession[]>]
 [-InstanceName <String[]>] [-PassThru] [-PolicyStore <PolicyStore[]>] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-NetNatTransitionConfiguration [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-NetNatTransitionConfiguration** makes the NAT64 configuration ineffective on a computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NetNatTransitionConfiguration
```

This example makes the NAT64 configuration ineffective.

## PARAMETERS

### -Adapter
Specifies the network adapter on which to disable the NAT64.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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
Specifies the NAT64 configuration object to disable.

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

### -InstanceName
Specifies the instance of the NAT64 for which the configuration will be made ineffective.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
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

### -PolicyStore
Specifies to which policy store the NAT64 configuration is applied.
The acceptable values for this parameter are: Persistent and Active.
If this parameter is not specified, then the cmdlet operates on both active and persistent stores.

```yaml
Type: PolicyStore[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Store

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNatTransitionConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Enable-NetNatTransitionConfiguration](./Enable-NetNatTransitionConfiguration.md)

[Get-NetNatTransitionConfiguration](./Get-NetNatTransitionConfiguration.md)

[Get-NetNatTransitionMonitoring](./Get-NetNatTransitionMonitoring.md)

[New-NetNatTransitionConfiguration](./New-NetNatTransitionConfiguration.md)

[Remove-NetNatTransitionConfiguration](./Remove-NetNatTransitionConfiguration.md)

[Set-NetNatTransitionConfiguration](./Set-NetNatTransitionConfiguration.md)

