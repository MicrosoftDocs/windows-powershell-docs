---
external help file: MSFT_NetNatTransitionConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/networktransition/disable-netnattransitionconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetNatTransitionConfiguration
---

# Disable-NetNatTransitionConfiguration

## SYNOPSIS
Disables the NAT64 configuration on a computer.

## SYNTAX

### ByName (Default)
```
Disable-NetNatTransitionConfiguration [-InstanceName <String[]>] [-PolicyStore <PolicyStore[]>]
 [-Adapter <CimInstance>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disable-NetNatTransitionConfiguration -InputObject <CimInstance[]> [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
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
Parameter Sets: ByName
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

### -InputObject
Specifies the NAT64 configuration object to disable.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: ByName
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
Parameter Sets: ByName
Aliases: Store
Accepted values: PersistentStore, ActiveStore

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

