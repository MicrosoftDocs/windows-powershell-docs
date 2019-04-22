---
external help file: Iscsi_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 1DA7D3BB-FB1A-475E-B64D-1614E67AD941
manager: dansimp
---

# Register-IscsiSession

## SYNOPSIS
Registers an active iSCSI session to be persistent using the session identifier as input.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Register-IscsiSession [-AsJob] [-ChapSecret <String>] [-ChapUsername <String>] [-CimSession <CimSession[]>]
 [-IsMultipathEnabled <Boolean>] [-PassThru] [-ThrottleLimit <Int32>] -SessionIdentifier <String[]>
```

### UNNAMED_PARAMETER_SET_2
```
Register-IscsiSession [-AsJob] [-ChapSecret <String>] [-ChapUsername <String>] [-CimSession <CimSession[]>]
 [-IsMultipathEnabled <Boolean>] [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Register-IscsiSession** cmdlet registers an existing iSCSI session to make it persistent.
Once an iSCSI session is registered, it will automatically attempt to reconnect on reboot.

Note: Registering a connection multiple times will automatically re-establish multiple sessions for use with Multipath I/O (MPIO).

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Register-IscsiSession -SessionIdentifier fffffa800d008430-4000013700000001
```

This example registers the iSCSI session with the session ID fffffa800d008430-4000013700000001 to be persistent across reboots.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_IscsiSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[iSCSI on TechNet](HYPERLINK "/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10)" /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee338476(v=ws.10))

[Storage on TechNet](HYPERLINK "http://technet.microsoft.com/en-us/library/ee344838(WS.10).aspx" http://technet.microsoft.com/en-us/library/ee344838(WS.10).aspx)

[N:MPIO](00000000-0000-0000-0000-000000000000)

[N:Storage](00000000-0000-0000-0000-000000000000)

