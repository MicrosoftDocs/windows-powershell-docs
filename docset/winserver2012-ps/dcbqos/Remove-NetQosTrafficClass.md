---
external help file: DcbQos_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 4CFFA115-7B8C-4C21-BA63-6DC4751A98E0
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Remove-NetQosTrafficClass

## SYNOPSIS
Removes a traffic class.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetQosTrafficClass [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetQosTrafficClass [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetQosTrafficClass** cmdlet removes traffic classes in Windows Server® 2012 and later.
If Windows Server 2012 or later is set to be not willing to accept configurations from a remote device, then Windows Server 2012 or later will program data center bridging (DCB)-capable network adapters to remove the specified traffic classes.

For more information on remote device configurations, see the Set-NetQosDcbxSetting cmdlet.

For more information on traffic class, see the New-NetQosTrafficClass cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-NetQosTrafficClass -Name SMB
```

This example removes the traffic class named SMB.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specified the object which will be modified by this cmdlet.
The object must be piped to the cmdlet.

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

### -Name
Specifies the name of the traffic class.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosTrafficClassSettingData object contains a network traffic class.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosTrafficClassSettingData object contains a network traffic class.
Only when the **PassThru** parameter is specified will the cmdlet return the MSFT_NetQosTrafficClassSettingData object.

## NOTES

## RELATED LINKS

[Get-NetQosTrafficClass](./Get-NetQosTrafficClass.md)

[New-NetQosTrafficClass](./New-NetQosTrafficClass.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)

[Set-NetQosTrafficClass](./Set-NetQosTrafficClass.md)

