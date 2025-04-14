---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: iSCSIConnection.cdxml-help.xml
Module Name: iSCSI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsi/get-iscsiconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiConnection
---

# Get-IscsiConnection

## SYNOPSIS
Gets information about connected iSCSI initiator connections.

## SYNTAX

### ByConnectionIdentifier (Default)
```
Get-IscsiConnection [-ConnectionIdentifier <String[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorSideIdentifier
```
Get-IscsiConnection [-InitiatorSideIdentifier <String[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetSideIdentifier
```
Get-IscsiConnection [-TargetSideIdentifier <String[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorPortalAddress
```
Get-IscsiConnection [-InitiatorPortalAddress <String[]>] [-InitiatorPortalPortNumber <UInt16[]>]
 [-InititorIPAdressListNumber <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSITarget
```
Get-IscsiConnection [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>]
 [-IscsiTarget <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorPort
```
Get-IscsiConnection [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>]
 [-InitiatorPort <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSISession
```
Get-IscsiConnection [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>]
 [-IscsiSession <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSITargetPortal
```
Get-IscsiConnection [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>]
 [-iSCSITargetPortal <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByDisk
```
Get-IscsiConnection [-InitiatorPortalPortNumber <UInt16[]>] [-InititorIPAdressListNumber <UInt16[]>]
 [-Disk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiConnection** cmdlet returns information about active iSCSI initiator connections.

## EXAMPLES

### Example 1: Display information about a connected iSCI target
```
PS C:\> Get-IscsiConnection
ConnectionIdentifier : fffffa8005313020-2
InitiatorNodeAddress : 0.0.0.0
InitiatorPortNumber  : 41458
TargetNodeAddress    : 10.121.235.126
TargetPortNumber     : 3260
```

The command displays information returned by this cmdlet from a connected iSCSI target.

## PARAMETERS

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

### -ConnectionIdentifier
Specifies the connection identifier for an iSCSI session.

```yaml
Type: String[]
Parameter Sets: ByConnectionIdentifier
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disk
Accepts a MSFT disk object as an input.
The MSFT disk object is output from the **Get-Disk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InitiatorPort
Accepts a MSFT initiator port object as an input.
The MSFT initiator port object is output from the **Get-InitiatorPort** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByInitiatorPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InitiatorPortalAddress
Specifies the IP address or DNS name that is associated with the portal.

```yaml
Type: String[]
Parameter Sets: ByInitiatorPortalAddress
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
Parameter Sets: ByInitiatorSideIdentifier
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InititorIPAdressListNumber
Specifies the index to the initiator IP address list.

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
The MSFT iSCSI session object is output from the **Get-IscsiSession** cmdlet.

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

### -IscsiTarget
Accepts a MSFT iSCSI target object as an input.
The MSFT iSCSI target object is output from the **Get-IscsiTarget** cmdlet.

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

### -TargetSideIdentifier
Specifies the target side identifier.

```yaml
Type: String[]
Parameter Sets: ByTargetSideIdentifier
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
Accepts a MSFT iSCSI target portal CIM object as an input.
The MSFT iSCSI target portal CIM object is output from the **Get-IscsiTargetPortal** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByiSCSITargetPortal
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

[iSCSI on TechNet](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

[Get-IscsiSession](./Get-IscsiSession.md)

[Get-IscsiTarget](./Get-IscsiTarget.md)

[Get-IscsiTargetPortal](./Get-IscsiTargetPortal.md)

