---
external help file: DcbQos_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 5340F8AF-66D3-40F4-A9E7-E30511B7C5D3
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-NetQosDcbxSetting

## SYNOPSIS
Sets the data center bridging exchange (DCBX) settings.

## SYNTAX

```
Set-NetQosDcbxSetting [-AsJob] [-CimSession <CimSession[]>] [-InputObject <CimInstance[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -Willing <Boolean> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetQosDcbxSetting** cmdlet sets the data center bridging exchange (DCBX) settings.
The only setting that Windows Server® 2012 and later allows a user to set is that the network adapters in computers running Windows Server 2012 and later should accept data center bridging (DCB) configurations from Windows Server 2012 and later or from a remote device via the DCBX protocol, which is specified in the IEEE data center bridging (DCB) standard.

If the **Willing** parameter is set to True, then Windows Server 2012 or later will not send priority-based flow control (PFC) and traffic class settings to DCB-capable network adapters in the computer.
If the **Willing** parameter is set to False, then Windows Server 2012 or later will send the settings to the network adapters.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NetQosDcbxSetting -Willing $true
```

This example enables the DCBX willing state, so that a DCB-capable network adapter is willing to accept configurations from a remote peer.

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

### -Willing
Specifies that a DCB-capable network adapter should accept the configuration from a remote peer via the DCBX protocol.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosDcbxSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosDcbxSettingData object contains the DCBX setting configured in Windows Server 2012 and later.
Only when the **PassThru** parameter is specified will the command return the MSFT_NetQosDcbxSettingData object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosDcbxSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetQosDcbxSetting](./Get-NetQosDcbxSetting.md)

[Get-NetQosDcbxSetting](./Get-NetQosDcbxSetting.md)

