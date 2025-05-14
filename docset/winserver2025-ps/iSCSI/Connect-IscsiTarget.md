---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: iSCSITarget.cdxml-help.xml
Module Name: iSCSI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsi/connect-iscsitarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-IscsiTarget
---

# Connect-IscsiTarget

## SYNOPSIS
Establishes a connection between the local iSCSI initiator and an iSCSI target device.

## SYNTAX

### ByNodeAddress (Default)
```
Connect-IscsiTarget -NodeAddress <String> [-TargetPortalAddress <String>] [-TargetPortalPortNumber <UInt16>]
 [-InitiatorPortalAddress <String>] [-IsDataDigest <Boolean>] [-IsHeaderDigest <Boolean>]
 [-IsPersistent <Boolean>] [-ReportToPnP <Boolean>] [-AuthenticationType <String>]
 [-IsMultipathEnabled <Boolean>] [-InitiatorInstanceName <String>] [-ChapUsername <String>]
 [-ChapSecret <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObject
```
Connect-IscsiTarget [-TargetPortalAddress <String>] [-TargetPortalPortNumber <UInt16>]
 [-InitiatorPortalAddress <String>] [-IsDataDigest <Boolean>] [-IsHeaderDigest <Boolean>]
 [-ReportToPnP <Boolean>] [-AuthenticationType <String>] [-IsMultipathEnabled <Boolean>]
 [-InitiatorInstanceName <String>] [-ChapUsername <String>] [-ChapSecret <String>] -InputObject <CimInstance[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Connect-IscsiTarget** cmdlet initiates a connection to the specified iSCSI target device.

## EXAMPLES

### Example 1: Disconnect and connect to an iSCSI target
```
The first command gets iSCSI targets by using the **Get-IscsiTarget** cmdlet.The second command gets iSCSI targets, and then stores them in the $Target variable. The third command disconnects the iSCSI target identified by its **NodeAddress** by using the **Disconnect-IscsiTarget** cmdlet. The final command connections the iSCSI target identified by its **NodeAddress**.
PS C:\> Get-IscsiTarget
IsConnected NodeAddress
----------- -----------
True iqn.1991-05.com.contoso:testiscsi-deepcore-target
PS C:\> $Target = Get-IscsiTarget
PS C:\> Disconnect-IscsiTarget -NodeAddress $Target.NodeAddress
Confirm
Are you sure you want to perform this action?
Performing operation '' on Target ''.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): **Y**
PS C:\> Connect-IscsiTarget -NodeAddress $Target.NodeAddress
AuthenticationType      : NONE
InitiatorInstanceName   : ROOT\ISCSIPRT\0000_0
InitiatorNodeAddress    : iqn.1991-05.com.contoso:deepcore.contoso.com
InitiatorPortalAddress  :
InitiatorSideIdentifier : 400001370000
IsConnected             : True
IsDataDigest            : False
IsDiscovered            : True
IsHeaderDigest          : False
IsMultipathEnabled      : False
IsPersistent            : True
NumberOfConnections     : 1
SessionIdentifier       : fffffa800d008430-400001370000000b
TargetNodeAddress       : iqn.1991-05.com.contoso:testiscsi-deepcore-target
TargetSideIdentifier    : 0100
```

This example connects an iSCSI target, collects information about the target, and stores it in a variable, disconnects, and then connects using this cmdlet.

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

### -AuthenticationType
Specifies the type of authentication to use when logging into the target.
The acceptable values for this parameter are:

- NONE
- ONEWAYCHAP
- MUTUALCHAP

The default value is None. Authentication type must be in uppercase.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChapSecret
Specifies the CHAP secret to use when establishing a connection authenticated by using CHAP.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChapUsername
Specifies the user name to use when establishing a connection authenticated by using Mutual CHAP.

```yaml
Type: String
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

### -InitiatorInstanceName
Specifies the name of the initiator instance that the iSCSI initiator service uses to send **SendTargets** requests to the target portal.
If no instance name is specified, the iSCSI initiator service chooses the initiator instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorPortalAddress
Specifies the IP address or DNS name that is associated with the portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsDataDigest
Indicates whether this cmdlet enables data digest when the initiator logs into the target portal.
If you do not specify this parameter, the digest setting is determined by the initiator kernel mode driver.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsHeaderDigest
Indicates whether this cmdlet enables header digest when the initiator logs into the target portal.
If you do not specify this parameter, the digest setting is determined by the initiator kernel mode driver.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsMultipathEnabled
Indicates whether the initiator has enabled Multipath I/O (MPIO) and uses it when logging into the target portal.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPersistent
Indicates whether the session is to be automatically connected after each restart.

```yaml
Type: Boolean
Parameter Sets: ByNodeAddress
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeAddress
Specifies the IQN of the discovered target.

```yaml
Type: String
Parameter Sets: ByNodeAddress
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportToPnP
Indicates whether the operation is reported to PNP.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPortalAddress
Specifies the IP address or DNS name of the target portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPortalPortNumber
Specifies the TCP/IP port number for the target portal.
By default, the port number is 3260.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI on TechNet](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

[Disconnect-IscsiTarget](./Disconnect-IscsiTarget.md)

[Get-IscsiTarget](./Get-IscsiTarget.md)

