---
external help file: MSFT_DAConnectionStatus.cdxml-help.xml
Module Name: NetworkConnectivityStatus
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/networkconnectivitystatus/get-daconnectionstatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAConnectionStatus
---

# Get-DAConnectionStatus

## SYNOPSIS
Returns an object detailing the DirectAccess status of the user.

## SYNTAX

```
Get-DAConnectionStatus [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAConnectionStatus** cmdlet returns an object with the status and sub-status of the DirectAccess connection for the computer.
The status reported here is the same as the status in the view-available-networks graphical user interface.

If no object is returned, then the computer is not configured for DirectAccess.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAConnectionStatus
```

This example gets the DirectAccess status of the local computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DAConnectionStatus
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NCSIPolicyConfiguration](./Get-NCSIPolicyConfiguration.md)

[Reset-NCSIPolicyConfiguration](./Reset-NCSIPolicyConfiguration.md)

[Set-NCSIPolicyConfiguration](./Set-NCSIPolicyConfiguration.md)

