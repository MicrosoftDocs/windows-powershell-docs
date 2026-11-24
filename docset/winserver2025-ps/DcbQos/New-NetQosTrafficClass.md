---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosTrafficClass.cdxml-help.xml
Module Name: DcbQos
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/dcbqos/new-netqostrafficclass?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetQosTrafficClass
---

# New-NetQosTrafficClass

## SYNOPSIS
Creates a traffic class.

## SYNTAX

### ByIfAlias (Default)
```
New-NetQosTrafficClass [-Name] <String> [-Algorithm] <Algorithm> [-BandwidthPercentage <Byte>]
 [-Priority] <Byte[]> [-InterfaceAlias <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByIfIndex
```
New-NetQosTrafficClass [-Name] <String> [-Algorithm] <Algorithm> [-BandwidthPercentage <Byte>]
 [-Priority] <Byte[]> [-InterfaceIndex <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This **New-NetQosTrafficClass** cmdlet creates a traffic class.
Traffic class is specified in the enhanced transmission selection (ETS) specification in the IEEE data center bridging (DCB) standard.
In creating a traffic class, the user specifies which types of traffic, differentiated by the IEEE 802.1p priority, are mapped to the traffic class, what transmission algorithm it uses, and how much bandwidth it gets.
If Windows Server® 2012 or later is set to be **not willing** to accept DCB configurations from a remote device, then Windows Server 2012 or later programs DCB capable network adapters to add this new traffic class.

For more information about remote device configurations, see the **Set-NetQosDcbxSetting** cmdlet.

There is a default traffic class created by Windows Server 2012 or later.
All 8 priorities are mapped to this default traffic class, which selects ETS as its transmission algorithm and has all of the total bandwidth.
Users cannot delete the default traffic class.
Since a traffic class must have at least one type of traffic mapped to it and there are 8 or less types of such traffic, which is limited by IEEE 802.1p, only 7 additional traffic classes can be created.

In reality, a network adapter that supports DCB may support less than 8 traffic classes.
If there are more traffic classes configured in Windows Server 2012 or later than what a network adapter can support, then Windows Server 2012 or later will not send the configurations to the network adapter.

## EXAMPLES

### Example 1: Create a traffic class
```
PS C:\> New-NetQosTrafficClass -Name "SMB" -Priority 3 -Algorithm ETS -BandwidthPercentage 60

Name                      Algorithm Bandwidth(%) Priority
----                      --------- ------------ --------
SMB                       ETS       60           3
```

This command creates a traffic class for traffic tagged with the 802.1p value of 3.
This traffic class, named as SMB, has 60 percent of the bandwidth.

## PARAMETERS

### -Algorithm
```yaml
Type: Algorithm
Parameter Sets: (All)
Aliases: tsa
Accepted values: Strict, ETS

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -BandwidthPercentage
```yaml
Type: Byte
Parameter Sets: (All)
Aliases: Bandwidth, bw

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

### -InterfaceAlias
```yaml
Type: String
Parameter Sets: ByIfAlias
Aliases: IfAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
```yaml
Type: UInt32
Parameter Sets: ByIfIndex
Aliases: IfIndex

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: p, pri

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
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

### System.String

### System.UInt32

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetQosTrafficClass](./Get-NetQosTrafficClass.md)

[Set-NetQosTrafficClass](./Set-NetQosTrafficClass.md)

