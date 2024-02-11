---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: iSCSITargetPortal.cdxml-help.xml
Module Name: iSCSI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsi/new-iscsitargetportal?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-IscsiTargetPortal
---

# New-IscsiTargetPortal

## SYNOPSIS
Configures an iSCSI target portal.

## SYNTAX

```
New-IscsiTargetPortal -TargetPortalAddress <String> [-TargetPortalPortNumber <UInt16>]
 [-InitiatorPortalAddress <String>] [-IsHeaderDigest <Boolean>] [-IsDataDigest <Boolean>]
 [-AuthenticationType <String>] [-InitiatorInstanceName <String>] [-ChapUsername <String>]
 [-ChapSecret <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-IscsiTargetPortal** cmdlet connects a new iSCSI target portal.

## EXAMPLES

### Example 1: Add an iSCSI target portal
```
PS C:\> New-IscsiTargetPortal -TargetPortalAddress "testIscsi"
InitiatorInstanceName      :
InitiatorNodeAddress       :
InitiatorPortalAddress     :
InititorIPAdressListNumber : 4294967295
IsDataDigest               : False
IsHeaderDigest             : False
TargetPortalAddress        : testIscsi
TargetPortalPortNumber     : 3260
```

This command adds a new iSCSI target portal named testIscsi to perform discovery.

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

Note: These values are case sensitive.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorPortalAddress
Specifies the IP address or DNS name that is associated with the portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IA

Required: False
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

### -TargetPortalAddress
Specifies the IP address or DNS name of the target portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TA

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI on TechNet](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

