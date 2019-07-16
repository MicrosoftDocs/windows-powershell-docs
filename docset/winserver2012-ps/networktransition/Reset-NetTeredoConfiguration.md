---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 122D37C5-678E-4190-A1FB-9E4E37BBA4A9
manager: dansimp
---

# Reset-NetTeredoConfiguration

## SYNOPSIS
Resets the Teredo configuration elements in a Group Policy Object (GPO).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Reset-NetTeredoConfiguration [-AsJob] [-CimSession <CimSession[]>] [-ClientPort] [-DefaultQualified]
 [-GPOSession <String>] [-IPInterface <CimInstance>] [-PassThru] [-PolicyStore <String>]
 [-RefreshIntervalSeconds] [-ServerName] [-ServerShunt] [-ServerVirtualIP] [-ThrottleLimit <Int32>] [-Type]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Reset-NetTeredoConfiguration [-AsJob] [-CimSession <CimSession[]>] [-ClientPort] [-DefaultQualified]
 [-PassThru] [-RefreshIntervalSeconds] [-ServerName] [-ServerShunt] [-ServerVirtualIP] [-ThrottleLimit <Int32>]
 [-Type] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Reset-NetTeredoConfiguration** cmdlet resets the Teredo configuration elements in a Group Policy Object (GPO) configurations to the not configured state.
Group Policy settings have three possible states: not configured, enabled, and disabled.

If used with no parameters, this cmdlet resets all Teredo configurations on the specified store.

## EXAMPLES

### Example 1: Reset the Teredo configuration
```
PS C:\>Reset-NetTeredoConfiguration
```

This command resets the Teredo configuration to the not configured state.

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

### -ClientPort
Resets the UDP port of the client to not configured.

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

### -DefaultQualified
Resets the Teredo qualification configuration to false.
This parameter can only be specified on GPOs.

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

### -GPOSession
Specifies the Group Policy session that contains the Teredo configuration to reset. 

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO. 

You cannot use this parameter with the **PolicyStore** parameter.

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
Specifies the object which contains the Teredo configuration information to reset.

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

### -IPInterface
Specifies the interface on which to reset the Teredo configuration.
If the interface specified is not a Teredo interface, then the cmdlet does not return any configuration.

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
Specifies the policy store that contains the Teredo configuration to reset. 
The acceptable values for this parameter are:

 -- PersistentStore 

 -- ActiveStore 

 -- GPO 

To reset the configuration of a GPO, specify the GPO name using the following format: `Domain\GPOName`

You cannot use this parameter with the **GPOSession** parameter.

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

### -RefreshIntervalSeconds
Resets the client refresh interval to 30 (seconds).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: RefreshInterval

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Resets the server name to teredo.ipv6.contoso.com.

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

### -ServerShunt
Resets the server shunt configuration to False.

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

### -ServerVirtualIP
Resets the IPv4 address of the Teredo configuration to 0.0.0.0.

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

### -Type
Resets the type of the Teredo configuration to default.

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
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTeredoConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the **Passthru** parameter is specified, this cmdlet outputs a modified Windows Management Instrumentation (WMI) object.

## NOTES

## RELATED LINKS

[Get-NetTeredoConfiguration](./Get-NetTeredoConfiguration.md)

[Set-NetTeredoConfiguration](./Set-NetTeredoConfiguration.md)

