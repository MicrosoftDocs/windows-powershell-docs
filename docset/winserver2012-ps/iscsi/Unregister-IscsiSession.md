---
external help file: Iscsi_Cmdlets.xml
Module Name: iSCSI
online version: https://learn.microsoft.com/powershell/module/iscsi/unregister-iscsisession?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Unregister-IscsiSession

## SYNOPSIS
Removes an active iSCSI session from being persistent using the session identifier as input.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Unregister-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -SessionIdentifier <String[]>
```

### UNNAMED_PARAMETER_SET_2
```
Unregister-IscsiSession [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Unregister-IscsiSession** cmdlet removes a registered iSCSI session to prevent it from automatically reconnection on reboot.

## EXAMPLES

### Example 1
```
This information shows the output from the Get-iSCSISession. Since no additional switches or filters were used, this returns information about all iSCSI sessions across all iSCSI connections.
PS C:\>Get-IscsiSession
AuthenticationType      : NONE 
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0 
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com 
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


PS C:\>Unregister-IscsiSession -SessionIdentifier fffffa800d008430-4000013700000001
```

This example gets a list of sessions, and then uses this cmdlet to remove the session.

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

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output. 

                        
To send items from the interactive window down the pipeline, click to select the items and then click OK. 
Shift-click and Ctrl-click are supported.

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

### -SessionIdentifier
Specifies the session identifier.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[iSCSI Target Server Overview](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh848272(v=ws.11))

[Get-iSCSISession](./Get-IscsiSession.md)
