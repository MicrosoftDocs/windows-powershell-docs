---
external help file: MSFT_NetQosTrafficClass.cdxml-help.xml
Module Name: DcbQoS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/dcbqos/get-netqostrafficclass?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetQosTrafficClass
---

# Get-NetQosTrafficClass

## SYNOPSIS
Gets the traffic class settings.

## SYNTAX

```
Get-NetQosTrafficClass [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetQosTrafficClass** cmdlet retrieves network traffic classes configured in Windows Server 2012 and later.
A traffic class contains one or more types of traffic, each of which is differentiated by the IEEE 802.1p priority.

For more information on the traffic class, see the New-NetQosTrafficClass cmdlet.

This cmdlet only retrieves the traffic classes configured in Windows Server 2012 and later.
The traffic classes are not necessarily configured as-is on a network adapter in the computer.
To see the traffic class configuration on a network adapter, run the Get-NetAdapterQos cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetQosTrafficClass
Name                      Algorithm Bandwidth(%) Priority 
----                      --------- ------------ -------- 
[Default]                 ETS       40           0-2,4-7 
SMB                       ETS       60           3
```

This example displays all of the traffic classes.

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

### -Name
Specifies the name of the traffic class.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The MSFT_NetQosTrafficClassSettingData object contains a network traffic class.

## NOTES

## RELATED LINKS

[New-NetQosTrafficClass](./New-NetQosTrafficClass.md)

[Set-NetQosTrafficClass](./Set-NetQosTrafficClass.md)

