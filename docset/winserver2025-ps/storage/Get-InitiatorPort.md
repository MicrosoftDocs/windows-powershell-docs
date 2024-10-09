---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: InitiatorPort.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-initiatorport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InitiatorPort
---

# Get-InitiatorPort

## SYNOPSIS
Gets one or more host bus adapter (HBA) initiator ports.

## SYNTAX

### ByNodeAddress (Default)
```
Get-InitiatorPort [[-NodeAddress] <String[]>] [-ConnectionType <ConnectionType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectId
```
Get-InitiatorPort [-ObjectId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInstanceName
```
Get-InitiatorPort [-InstanceName <String[]>] [-ConnectionType <ConnectionType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-InitiatorPort [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSISession
```
Get-InitiatorPort [-iSCSISession <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSIConnection
```
Get-InitiatorPort [-iSCSIConnection <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByiSCSITarget
```
Get-InitiatorPort [-iSCSITarget <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-InitiatorPort** cmdlet gets and displays host bus adapter (HBA) initiator ports, such as SAS, FibreChannel, and iSCSI ports.
Typically used either for connection to an iSCSI target in the case of iSCSI, or for in the management of masking sets in the case of FibreChannel.

## EXAMPLES

### Example 1: Get all initiator ports
```
PS C:\>Get-InitiatorPort
InstanceName                  NodeAddress                   PortAddress                   ConnectionType
------------                  -----------                   -----------                   --------------
ROOT\ISCSIPRT\0000_0          iqn.1991-05.com.contoso:...   ISCSI ANY PORT                iSCSI
```

This example gets all available initiator ports.

### Example 2: Get all initiator ports, and filter the display
```
PS C:\>Get-InitiatorPort | Select-Object -Property NodeAddress,ConnectionType | Format-Table -AutoSize
NodeAddress                                                    ConnectionType
-----------                                                    --------------
iqn.1991-05.com.microsoft:johnj99-pc2.contoso.com              iSCSI
```

This example gets all available initiator ports.
selects only the NodeAddress and ConnectionType properties, and then displays this information.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -ConnectionType
Specifies the type of the connection.
Acceptable values are: Other, FibreChannel, iSCSI, and SAS.

To specify a custom connection type, specify the Other value and specify a non-NULL value for the **OtherConnectionTypeDescription** property.

```yaml
Type: ConnectionType[]
Parameter Sets: ByNodeAddress, ByInstanceName
Aliases:
Accepted values: Other, FibreChannel, iSCSI, SAS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceName
Specifies the instance name of the initiator.

```yaml
Type: String[]
Parameter Sets: ByInstanceName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeAddress
Specifies the node address for the initiator.

```yaml
Type: String[]
Parameter Sets: ByNodeAddress
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Specifies the ObjectID of the initiator.

```yaml
Type: String[]
Parameter Sets: ByObjectId
Aliases: Id

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

### -VirtualDisk
Specifies the VirtualDisk object for which you want to get the initiator port.
Enter a VirtualDisk CIM object, which is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSIConnection
Specifies the iSCSIConnection object for which you want to get the initiator port.
Enter an iSCSIConnection CIM object, which is exposed by the **Get-IscsiConnection** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByiSCSIConnection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSISession
Specifies the iSCSISession object for which you want to get the initiator port.
Enter an iSCSISession CIM object, which is exposed by the **Get-IscsiSession** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByiSCSISession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSITarget
Specifies the iSCSITarget object for which you want to get the initiator port.
Enter an iSCSITarget CIM object, which is exposed by the **Get-IscsiTarget** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByiSCSITarget
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiConnection
You can pipe an iSCSIConnection object to the *iSCSIConnection* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiSession
You can pipe an iSCSISession object to the *iSCSISession* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiTarget
You can pipe an IscsiTarget object to the *IscsiTarget* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the *VirtualDisk* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorPort
This cmdlet returns an object that represents the initiator port you specified.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Format-Table](https://go.microsoft.com/fwlink/?LinkID=113303)

[Select-Object](https://go.microsoft.com/fwlink/?LinkID=113387)

[Set-InitiatorPort](./Set-InitiatorPort.md)

