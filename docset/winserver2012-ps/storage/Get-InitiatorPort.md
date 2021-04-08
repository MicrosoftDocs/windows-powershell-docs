---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-initiatorport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-InitiatorPort

## SYNOPSIS
Gets one or more host bus adapter (HBA) initiator ports.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-InitiatorPort [[-NodeAddress] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ConnectionType <ConnectionType[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-InitiatorPort [-AsJob] [-CimSession <CimSession[]>] [-iSCSITarget <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-InitiatorPort [-AsJob] [-CimSession <CimSession[]>] [-iSCSIConnection <CimInstance>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-InitiatorPort [-AsJob] [-CimSession <CimSession[]>] [-iSCSISession <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-InitiatorPort [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-InitiatorPort [-AsJob] [-CimSession <CimSession[]>] [-ConnectionType <ConnectionType[]>]
 [-InstanceName <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-InitiatorPort [-AsJob] [-CimSession <CimSession[]>] [-ObjectId <String[]>] [-ThrottleLimit <Int32>]
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

### -ConnectionType
Specifies the type of the connection.
Acceptable values are: Other, FibreChannel, iSCSI, and SAS.

To specify a custom connection type, specify the Other value and specify a non-NULL value for the **OtherConnectionTypeDescription** property.

```yaml
Type: ConnectionType[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_6
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Specifies the ObjectID of the initiator.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_7
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSIConnection
Specifies the iSCSIConnection object for which you want to get the initiator port.
Enter an iSCSIConnection CIM object, which is exposed by the Get-IscsiConnection cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSISession
Specifies the iSCSISession object for which you want to get the initiator port.
Enter an iSCSISession CIM object, which is exposed by the Get-IscsiSession cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSITarget
Specifies the iSCSITarget object for which you want to get the initiator port.
Enter an iSCSITarget CIM object, which is exposed by the Get-IscsiTarget cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiConnection
You can pipe an iSCSIConnection object to the **iSCSIConnection** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiSession
You can pipe an iSCSISession object to the **iSCSISession** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiTarget
You can pipe an IscsiTarget object to the **IscsiTarget** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the **VirtualDisk** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorPort
This cmdlet returns an object that represents the initiator port you specified.

## NOTES

## RELATED LINKS

[Format-Table](https://go.microsoft.com/fwlink/?LinkID=113303)

[Select-Object](https://go.microsoft.com/fwlink/?LinkID=113387)

[Set-InitiatorPort](./Set-InitiatorPort.md)

