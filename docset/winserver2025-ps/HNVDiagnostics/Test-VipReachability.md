---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: VipReachability.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/test-vipreachability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-VipReachability
---

# Test-VipReachability

## SYNOPSIS
Tests whether DIPs are reachable.

## SYNTAX

```
Test-VipReachability [[-OperationId] <String>] [-SourceIP] <String> [[-CompartmentId] <String>]
 [-TargetVIP] <String> [-Muxes] <Hashtable[]> [-Dips] <Hashtable[]> [[-SequenceNumber] <Int32>]
 [[-PayloadSize] <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-VipReachability** cmdlet tests whether a list of datacenter IP addresses (DIPs) can be reached through the specified multiplexers (MUXes).

The test covers layer-3 connectivity to the MUX nodes, and from the MUX nodes to the DIP hosts.

The test first sends Internet Control Message Protocol (ICMP) echo requests to the virtual IP (VIP) address.
The MUX intercepts the echo requests and sends responses that appear to come from the targeted VIP.

The test then sends ICMP echo requests from the MUX host to the DIP host on the provider network.
The results of the test are reported in the output object.

## EXAMPLES

### Example 1: Test VIP reachability
```
PS C:\> for ($mux in $VipHostMapping.MuxList) {
    $secpasswd = ConvertTo-SecureString <plaintext password> -AsPlainText -Force
    $creds = New-Object System.Management.Automation.PSCredential (<username>, $secpasswd)
    $mux.Credentials = $creds
}
PS C:\> for ($dip in $VipHostMapping.DIPHosts) {
    $secpasswd = ConvertTo-SecureString <plaintext password> -AsPlainText -Force
    $creds = New-Object System.Management.Automation.PSCredential (<username>, $secpasswd)
    $dip.HostInfo.Credentials = $creds
}
PS C:\> Test-VIPReachability -OperationId 1 -SourceIP "10.123.176.108" -TargetVIP "10.123.177.110" -Muxes $VipHostMapping.MuxList -Dips $VipHostMapping.DIPHosts
```

The first command populates the credentials for the MUX nodes to test.

The second command populates the credentials for the DIPs to test.

The last command tests the VIP reachability for the specified MUXes and DIPs.

## PARAMETERS

### -CompartmentId
Specifies the ID of the network compartment to use to inject ICMP echo requests.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dips
Specifies an array of DIPs to test.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Muxes
Specifies an array of MUXes to load-balance the DIPs.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationId
Specifies an ID for the operation.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PayloadSize
Specifies the size of the payload to carry in ICMP messages.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SequenceNumber
Specifies the ICMP sequence number.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIP
Specifies the IP address of the source node.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetVIP
Specifies the IP address of the target VIP.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

