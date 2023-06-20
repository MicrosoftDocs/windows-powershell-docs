---
external help file: SMTasks_Cmdlets.xml
Module Name: ServerManagerTasks
online version: https://learn.microsoft.com/powershell/module/servermanagertasks/get-smserverbparesult?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SMServerBpaResult

## SYNOPSIS
To retrieve BPA results, use the Get-BpaResult cmdlet instead of this cmdlet.

## SYNTAX

```
Get-SMServerBpaResult [-AsJob] [-BatchSize <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -BpaXPath <String[]>
```

## DESCRIPTION
To retrieve BPA results, use the **Get-BpaResult** cmdlet instead of this cmdlet.

## EXAMPLES

### Example 1: Get the Best Practices Analyzer results
```
PS C:\>Get-SMServerBPAResult
```

This command gets the results of the Best Practices Analyzer.

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

### -BatchSize
Specifies the batch size that the command uses to stream results.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BpaXPath
Specifies an array of Bpa XPaths to query from the computer.
Specify the Bpa XPath in the following format: BpaModelName:BpaFilepath:BpaXPath.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
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

## OUTPUTS

## NOTES

## RELATED LINKS

