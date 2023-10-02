---
external help file: iSCSITargetPortal.cdxml-help.xml
Module Name: iSCSI
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/iscsi/get-iscsitargetportal?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiTargetPortal
---

# Get-IscsiTargetPortal

## SYNOPSIS
Gives the list of target portals which have been set for discovery.

## SYNTAX

### ByTargetPortalAddress (Default)
```
Get-IscsiTargetPortal [-InitiatorPortalAddress <String[]>] [[-TargetPortalAddress] <String[]>]
 [-InitiatorInstanceName <String[]>] [-TargetPortalPortNumber <UInt16[]>] [-IsHeaderDigest <Boolean[]>]
 [-IsDataDigest <Boolean[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSISession
```
Get-IscsiTargetPortal [-iSCSISession <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByiSCSIConnection
```
Get-IscsiTargetPortal [-iSCSIConnection <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByiSCSITarget
```
Get-IscsiTargetPortal [-iSCSITarget <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiTargetPortal** cmdlet gets information about iSCSI target portals.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-IscsiTargetPortal -TargetPortalAddress testIscsi
InitiatorInstanceName      : 
InitiatorNodeAddress       : 
InitiatorPortalAddress     : 
InititorIPAdressListNumber : 4294967295 
IsDataDigest               : False 
IsHeaderDigest             : False 
TargetPortalAddress        : testIscsi 
TargetPortalPortNumber     : 3260
```

This example adds a new iSCSI target portal with the name testiSCSI to perform discovery.

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

### -InitiatorInstanceName
Specifies the name of the initiator instance that the iSCSI initiator service uses to send **SendTargets** requests to the target portal.
If no instance name is specified, the iSCSI initiator service chooses the initiator instance.

```yaml
Type: String[]
Parameter Sets: ByTargetPortalAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorPortalAddress
Represents the IP address or DNS name associated with the portal.

```yaml
Type: String[]
Parameter Sets: ByTargetPortalAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsDataDigest
Enables data digest when the initiator logs into the target portal.
By not specifying this parameter, the digest setting is determined by the initiator kernel mode driver.

```yaml
Type: Boolean[]
Parameter Sets: ByTargetPortalAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsHeaderDigest
Enables header digest when the initiator logs into the target portal.
By not specifying this parameter, the digest setting is determined by the initiator kernel mode driver.

```yaml
Type: Boolean[]
Parameter Sets: ByTargetPortalAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPortalAddress
Represents the IP address or DNS name of the target portal.

```yaml
Type: String[]
Parameter Sets: ByTargetPortalAddress
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPortalPortNumber
Specifies the TCP/IP port number for the target portal.
By default, the port number is `3260`.

```yaml
Type: UInt16[]
Parameter Sets: ByTargetPortalAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -iSCSIConnection
Accepts a MSFT iSCSI connection object as an input.
The MSFT iSCSI connection object is output from the Get-IscsiConnection cmdlet.

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

### -iSCSISession
Accepts a MSFT iSCSI session object as an input.
The MSFT iSCSI session object is output from the Get-IscsiSession cmdlet.

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

### -iSCSITarget
Accepts a MSFT iSCSI target object as an input.
The MSFT iSCSI target object is output from the Get-IscsiTarget cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTarget
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiTargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI on TechNet](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](https://go.microsoft.com/fwlink/?linkid=191356)

[Get-IscsiConnection](./Get-IscsiConnection.md)

[Get-IscsiSession](./Get-IscsiSession.md)

[Get-IscsiTarget](./Get-IscsiTarget.md)


