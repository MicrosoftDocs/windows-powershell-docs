---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SlbDatapathTracing.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/debug-slbdatapath?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-SlbDatapath
---

# Debug-SlbDatapath

## SYNOPSIS
Collects logs from an SLB MUX and DIP host.

## SYNTAX

```
Debug-SlbDatapath [[-OperationId] <String>] [-SourceIP] <String> [-TargetVIP] <String> [-PortNumber] <UInt16>
 [-Muxes] <Hashtable[]> [-Dips] <Hashtable[]> [[-TraceFolderPath] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Debug-SlbDatapath** cmdlet collects logs from the Software Load Balancing (SLB) Multiplexer (MUX) and dynamic IP address (DIP) host traversed by packets in the specified flow.

## EXAMPLES

### Example 1: Get MUX and DIP host logs
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
PS C:\> $out = Debug-SlbDatapath -OperationId "1" -SourceIP "10.123.176.108" -TargetVIP "10.123.177.110" -PortNumber 445 -Muxes $VipHostMapping.MuxList -Dips $VipHostMapping.DIPHosts
```

The first command creates a **PSCredential** object containing MUX credentials, and then stores it in the $mux.Credentials variable.

The second command creates a **PSCredential** object containing DIP host credentials, and then stores it in the $dip.HostInfo.Credentials variable.

The third command runs test traffic targeting the specified VIP endpoint from the specified source IP address.
You can use the command `$out | Format-Custom` to display the paths of the MUX and DIP logs that were collected.

## PARAMETERS

### -Dips
Specifies the DIPs that implement the virtual IP address (VIP) endpoint under test.

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
Specifies the MUXes that load balance the DIPs.

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
Specifies an operation ID.

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

### -PortNumber
Specifies the port number of the VIP endpoint this operation tests.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIP
Specifies the IP of the source node.

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
Specifies the IP of the VIP this operation tests.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TraceFolderPath
Specifies the path of the trace log folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
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

