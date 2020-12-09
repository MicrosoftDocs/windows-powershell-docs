---
external help file: Iscsi_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: E566D297-76AD-48D0-B5AF-11674F23B080
manager: dansimp
---

# Get-IscsiConnection

## SYNOPSIS
Gets information about connected iSCSI initiator connections.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-ConnectionIdentifier <String[]>]
 [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPort <CimInstance>]
 [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-iSCSITargetPortal <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-Disk <CimInstance>]
 [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-IscsiSession <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPortalAddress <String[]>]
 [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InitiatorSideIdentifier <String[]>] [-InititorIPAdressListNumber <UInt16[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_8
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-IscsiTarget <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_9
```
Get-IscsiConnection [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-TargetSideIdentifier <String[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-IscsiConnection** cmdlet returns information about active iSCSI initiator connections.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-IscsiConnection
ConnectionIdentifier : fffffa8005313020-2 
InitiatorNodeAddress : 0.0.0.0 
InitiatorPortNumber  : 41458 
TargetNodeAddress    : 10.121.235.126 
TargetPortNumber     : 3260
```

The example shows information returned by this cmdlet from a connected iSCSI target.

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

### -ConnectionIdentifier
Specifies the connection identifier for an iSCSI session.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disk
Accepts a MSFT disk object as an input.
The MSFT disk object is output from the Get-Disk cmdlet.

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

### -InitiatorPort
Accepts a MSFT initiator port object as an input.
The MSFT initiator port object is output from the Get-InitiatorPort cmdlet.

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

### -InitiatorPortalAddress
Represents the IP address or DNS name associated with the portal.

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

### -InitiatorPortalPortNumber
Specifies the TCP/IP port number for the initiator portal.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorSideIdentifier
Specifies the initiator side identifier.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InititorIPAdressListNumber
Represents the index to the initiator IP address list.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IscsiSession
Accepts a MSFT iSCSI session object as an input.
The MSFT iSCSI session object is output from the Get-IscsiSession cmdlet.

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

### -IscsiTarget
Accepts a MSFT iSCSI target object as an input.
The MSFT iSCSI target object is output from the Get-IscsiTarget cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetSideIdentifier
Specifies the target side identifier.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_9
Aliases: 

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

### -iSCSITargetPortal
Allows passing a MSFT iSCSI target portal CIM object as an input.
The MSFT iSCSI target portal CIM object is output from the Get-IscsiTargetPortal cmdlet.

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

## INPUTS

### System.String

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DISK
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_InitiatorPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTarget
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_iSCSIConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI Target Server Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh848272(v=ws.11))

[Get-IscsiSession](./Get-IscsiSession.md)

[Get-IscsiTarget](./Get-IscsiTarget.md)

[Get-IscsiTargetPortal](./Get-IscsiTargetPortal.md)

[Get-Disk](../storage/Get-Disk.md)

[Get-InitiatorPort](../storage/Get-InitiatorPort.md)
