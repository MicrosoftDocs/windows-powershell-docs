---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: iSCSISession.cdxml-help.xml
Module Name: iSCSI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsi/unregister-iscsisession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-IscsiSession
---

# Unregister-IscsiSession

## SYNOPSIS
Removes an active iSCSI session from being persistent using the session identifier as input.

## SYNTAX

### BySessionIdentifier (Default)
```
Unregister-IscsiSession -SessionIdentifier <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Unregister-IscsiSession -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-IscsiSession** cmdlet removes a registered iSCSI session to prevent it from automatically reconnection on restart.

## EXAMPLES

### Example 1: Remove a session
```
The first command gets information about all iSCSI sessions across all iSCSI connections by using the **Get-IscsiSession** cmdlet.
PS C:\> Get-IscsiSession
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

The second command removes the session that has the specified session ID.
PS C:\> Unregister-IscsiSession -SessionIdentifier "fffffa800d008430-4000013700000001"
```

This example gets a list of sessions, and then uses this cmdlet to remove the session.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Parameter Sets: BySessionIdentifier
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[iSCSI on TechNet](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

[Get-IscsiSession](./Get-IscsiSession.md)

