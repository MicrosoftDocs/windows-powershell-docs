---
external help file: Iscsi_Cmdlets.xml
Module Name: iSCSI
online version: https://docs.microsoft.com/powershell/module/iscsi/get-iscsisession?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-IscsiSession

## SYNOPSIS
Retrieves information about established iSCSI sessions.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-IscsiTargetPortal <CimInstance>]
 [-NumberOfConnections <UInt32[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-NumberOfConnections <UInt32[]>]
 [-SessionIdentifier <String[]>] [-TargetSideIdentifier <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-IscsiTarget <CimInstance>]
 [-NumberOfConnections <UInt32[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-InitiatorSideIdentifier <String[]>]
 [-NumberOfConnections <UInt32[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-InitiatorPort <CimInstance>]
 [-NumberOfConnections <UInt32[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-Disk <CimInstance>] [-NumberOfConnections <UInt32[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-IscsiConnection <CimInstance>]
 [-NumberOfConnections <UInt32[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-IscsiSession** cmdlet returns information about iSCSI sessions.

Note: There is an association between the iSCSI session and the disk object, so it is possible to return all disks connected via a specific iSCSI session by running the following cmdlet. 

                      
 - `Get-iSCSISession | Get-Disk`

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-IscsiSession
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

### -Disk
Accepts a MSFT disk object as an input.
The MSFT disk object is output from the Get-Disk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_6
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IscsiConnection
Accepts a MSFT iSCSI connection object as an input.
The MSFT iSCSI connection object is output from the Get-IscsiConnection cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_7
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IscsiTargetPortal
Accepts a MSFT iSCSI target portal object as an input.
The MSFT iSCSI target portal object is output from the Get-IscsiTargetPortal cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: (All)
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

[iSCSI Target Server Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh848272(v=ws.11))

[Get-IscsiConnection](./Get-IscsiConnection.md)

[Get-IscsiTarget](./Get-IscsiTarget.md)

[Get-IscsiTargetPortal](./Get-IscsiTargetPortal.md)

[Get-Disk](../storage/Get-Disk.md)

[Get-InitiatorPort](../storage/Get-InitiatorPort.md)
