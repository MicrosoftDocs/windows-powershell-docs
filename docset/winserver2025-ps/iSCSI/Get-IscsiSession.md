---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: iSCSISession.cdxml-help.xml
Module Name: iSCSI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsi/get-iscsisession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiSession
---

# Get-IscsiSession

## SYNOPSIS
Retrieves information about established iSCSI sessions.

## SYNTAX

### BySessionIdentifier (Default)
```
Get-IscsiSession [<CommonParameters>]
```

### ByTargetSideIdentifier
```
Get-IscsiSession [-SessionIdentifier <String[]>] [-TargetSideIdentifier <String[]>]
 [-NumberOfConnections <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorSideIdentifier
```
Get-IscsiSession [-InitiatorSideIdentifier <String[]>] [-NumberOfConnections <UInt32[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByiSCSITarget
```
Get-IscsiSession [-NumberOfConnections <UInt32[]>] [-IscsiTarget <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInitiatorPort
```
Get-IscsiSession [-NumberOfConnections <UInt32[]>] [-InitiatorPort <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByiSCSITargetPortal
```
Get-IscsiSession [-NumberOfConnections <UInt32[]>] [-IscsiTargetPortal <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDisk
```
Get-IscsiSession [-NumberOfConnections <UInt32[]>] [-Disk <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByiSCSIConnection
```
Get-IscsiSession [-NumberOfConnections <UInt32[]>] [-IscsiConnection <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiSession** cmdlet returns information about iSCSI sessions.

There is an association between the iSCSI session and the disk object.
It is possible to return all disks connected by using a specific iSCSI session by running the following command:

PS C:\\\> `Get-iSCSISession | Get-Disk`

## EXAMPLES

### Example 1: Get information about iSCSI sessions
```
PS C:\> Get-IscsiSession
AuthenticationType      : NONE
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0
InitiatorNodeAddress    : iqn.1991-05.com.microsoft:deepcore.contoso.com
InitiatorPortalAddress  :
InitiatorSideIdentifier : 400001370001
IsConnected             : True
IsDataDigest            : False
IsDiscovered            : True
IsHeaderDigest          : False
IsMultipathEnabled      : False
IsPersistent            : True
NumberOfConnections     : 1
SessionIdentifier       : fffffa800d008430-4000013700000001
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target
TargetSideIdentifier    : 0200

AuthenticationType      : NONE
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com
InitiatorPortalAddress  :
InitiatorSideIdentifier : 400001370004
IsConnected             : True
IsDataDigest            : False
IsDiscovered            : True
IsHeaderDigest          : False
IsMultipathEnabled      : False
IsPersistent            : True
NumberOfConnections     : 1
SessionIdentifier       : fffffa800d008430-4000013700000002
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target
TargetSideIdentifier    : 0100

AuthenticationType      : NONE
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com
InitiatorPortalAddress  :
InitiatorSideIdentifier : 400001370002
IsConnected             : True
IsDataDigest            : False
IsDiscovered            : True
IsHeaderDigest          : False
IsMultipathEnabled      : False
IsPersistent            : True
NumberOfConnections     : 1
SessionIdentifier       : fffffa800d008430-4000013700000003
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target
TargetSideIdentifier    : 0300
```

This command returns information about iSCSI sessions.

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
Parameter Sets: ByTargetSideIdentifier, ByInitiatorSideIdentifier, ByiSCSITarget, ByInitiatorPort, ByiSCSITargetPortal, ByDisk, ByiSCSIConnection
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
Parameter Sets: ByTargetSideIdentifier, ByInitiatorSideIdentifier, ByiSCSITarget, ByInitiatorPort, ByiSCSITargetPortal, ByDisk, ByiSCSIConnection
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -IscsiConnection
Accepts a MSFT iSCSI connection object as an input.
The MSFT iSCSI connection object is output from the **Get-IscsiConnection** cmdlet.

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

### -IscsiTargetPortal
Accepts a MSFT iSCSI target portal object as an input.
The MSFT iSCSI target portal object is output from the **Get-IscsiTargetPortal** cmdlet.

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

### -NumberOfConnections
Specifies the number of connections.

```yaml
Type: UInt32[]
Parameter Sets: ByTargetSideIdentifier, ByInitiatorSideIdentifier, ByiSCSITarget, ByInitiatorPort, ByiSCSITargetPortal, ByDisk, ByiSCSIConnection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionIdentifier
Specifies the session identifier.

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
Parameter Sets: ByTargetSideIdentifier, ByInitiatorSideIdentifier, ByiSCSITarget, ByInitiatorPort, ByiSCSITargetPortal, ByDisk, ByiSCSIConnection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DISK
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_InitiatorPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTarget
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI on TechNet](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

[Get-IscsiConnection](./Get-IscsiConnection.md)

[Get-IscsiTarget](./Get-IscsiTarget.md)

[Get-IscsiTargetPortal](./Get-IscsiTargetPortal.md)

