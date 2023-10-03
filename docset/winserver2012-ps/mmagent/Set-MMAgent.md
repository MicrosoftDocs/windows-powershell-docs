---
external help file: MMAgent_Cmdlets.xml
Module Name: MMAgent
online version: https://learn.microsoft.com/powershell/module/mmagent/set-mmagent?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-MMAgent

## SYNOPSIS
Sets the maximum number of prefetch files for scenarios that the Operation Recorder API records.

## SYNTAX

```
Set-MMAgent [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -MaxOperationAPIFiles <UInt32>
```

## DESCRIPTION
The **Set-MMAgent** cmdlet sets the maximum number of prefetch files for scenarios that the Operation Recorder API records.
The Operation Recorder API stores prefetch files (.pf) specific to a particular Operation ID in the \Windows\Prefetch folder.

## EXAMPLES

### Example 1: Set the maximum number of prefetch files
```
PS C:\> Set-MMAgent -MaxOperationAPIFiles 128
```

This command sets the maximum number of prefetch files for scenarios that the Operation Recorder API records to 128.

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

### -MaxOperationAPIFiles
Sets the maximum number of prefetch files for scenarios that the Operation Recorder API records.
The maximum number of prefetch files must be in the range from 1 through 8192.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: moaf

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MMAgent](./Get-MMAgent.md)

[Enable-MMAgent](./Enable-MMAgent.md)

[Disable-MMAgent](./Disable-MMAgent.md)

