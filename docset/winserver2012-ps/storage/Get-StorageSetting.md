---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://learn.microsoft.com/powershell/module/storage/get-storagesetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-StorageSetting

## SYNOPSIS
Returns the StorageSetting object.

## SYNTAX

```
Get-StorageSetting [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-StorageSetting** cmdlet returns the StorageSetting object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>ipmo storage



PS C:\>Get-StorageSetting
NewDiskPolicy                                               PSComputerName 
-------------                                               -------------- 
OnlineAll
```

This example shows the current value of the New Disk Policy.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-StorageSetting](./Set-StorageSetting.md)

