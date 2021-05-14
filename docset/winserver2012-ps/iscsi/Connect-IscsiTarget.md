---
external help file: Iscsi_Cmdlets.xml
Module Name: iSCSI
online version: https://docs.microsoft.com/powershell/module/iscsi/connect-iscsitarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Connect-IscsiTarget

## SYNOPSIS
Establishes a connection between the local iSCSI initiator, and the specified iSCSI target device.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Connect-IscsiTarget [-AsJob] [-AuthenticationType <String>] [-ChapSecret <String>] [-ChapUsername <String>]
 [-CimSession <CimSession[]>] [-InitiatorInstanceName <String>] [-InitiatorPortalAddress <String>]
 [-IsDataDigest <Boolean>] [-IsHeaderDigest <Boolean>] [-IsMultipathEnabled <Boolean>]
 [-IsPersistent <Boolean>] [-ReportToPnP <Boolean>] [-TargetPortalAddress <String>]
 [-TargetPortalPortNumber <UInt16>] [-ThrottleLimit <Int32>] -NodeAddress <String>
```

### UNNAMED_PARAMETER_SET_2
```
Connect-IscsiTarget [-AsJob] [-AuthenticationType <String>] [-ChapSecret <String>] [-ChapUsername <String>]
 [-CimSession <CimSession[]>] [-InitiatorInstanceName <String>] [-InitiatorPortalAddress <String>]
 [-IsDataDigest <Boolean>] [-IsHeaderDigest <Boolean>] [-IsMultipathEnabled <Boolean>] [-ReportToPnP <Boolean>]
 [-TargetPortalAddress <String>] [-TargetPortalPortNumber <UInt16>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Connect-IscsiTarget** cmdlet initiates a connection to the specified iSCSI target device.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-IscsiTarget
IsConnected NodeAddress 
----------- ----------- 
True iqn.1991-05.com.contoso:testiscsi-deepcore-target 


PS C:\>$Tar = Get-IscsiTarget



PS C:\>Disconnect-IscsiTarget -NodeAddress $Tar.NodeAddress
Confirm 
Are you sure you want to perform this action? 
Performing operation '' on Target ''.


[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):Y



PS C:\>Connect-IscsiTarget -NodeAddress $Tar.NodeAddress
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

This example connects an iSCSI target, collects information about the target, and stores it in a variable, disconnects, and then connects using this cmdlet

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

### -AuthenticationType
Specifies the type of authentication to use when logging into the target.
Valid values are **None**, **OneWayCHAP**, and **MutualCHAP**.

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

### -InitiatorInstanceName
Specifies the name of the initiator via which the **SendTargets** operation is performed.
If not specified, then the initiator used is selected by the iSCSI initiator service.

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
Specifies the IP address or DNS name associated with the portal.

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
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsDataDigest
Enables data digest when the initiator logs into the target portal.
By not specifying this parameter, the digest setting is determined by the initiator kernel mode driver.

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
Enables header digest when the initiator logs into the target portal.
By not specifying this parameter, the digest setting is determined by the initiator kernel mode driver.

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
Indicates that the initiator has enabled Multipath I/O (MPIO) and it will be used when logging into the target portal.

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
Specifies that the session is to be automatically connected after each restart.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeAddress
Represents the IQN of the discovered target.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportToPnP
Specifies that the operation is reported to PNP.

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
Represents the IP address or DNS name of the target portal.

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
By default, the port number is `3260`.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI Target Server Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh848272(v=ws.11))

