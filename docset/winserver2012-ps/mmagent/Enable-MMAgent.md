---
external help file: MMAgent_Cmdlets.xml
Module Name: MMAgent
online version: https://docs.microsoft.com/powershell/module/mmagent/enable-mmagent?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-MMAgent

## SYNOPSIS
Enables application launch prefetching, operation recorder API functionality, and page combining.

## SYNTAX

```
Enable-MMAgent [-ApplicationLaunchPrefetching] [-AsJob] [-CimSession <CimSession[]>] [-OperationAPI]
 [-PageCombining] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Enable-MMAgent** cmdlet enables any or all of the following features:
- Application launch prefetching
- Operation recorder API functionality
- Page combining

Specify the **ApplicationLaunchPrefetching** parameter to help improve application startup performance.
Application launch prefetching causes the memory manager agent to monitor the data and code that applications access.
The memory management agent then uses that information to preload the data and code into physical memory for subsequent startups.

Specify the **OperationAPI** parameter to help speed up operations that repeatedly access the same file data.
Enabling this feature exposes the Windows prefetching mechanism as a public interface.

Specify the **PageCombining** parameter to help reduce the physical memory that the operating system uses.
Page combining causes the memory manager to periodically combine pages in physical memory that have identical content.

## EXAMPLES

### Example 1: Enable application launch prefetching
```
PS C:\> Enable-MMAgent -ApplicationLaunchPrefetching
```

This command enables application launch prefetching on the local computer.

## PARAMETERS

### -ApplicationLaunchPrefetching
Enables application launch prefetching.

If you do not specify this parameter, application launch prefetching remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: alp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -OperationAPI
Enables operation recorder API functionality.

If you do not specify this parameter, operation recorder API functionality remains in its current state, either enabled or disabled.

For more information about the Operation Recorder API, see Operation Recorderhttps://msdn.microsoft.com/library/windows/desktop/hh437575(v=VS.85).aspx on MSDN (https://msdn.microsoft.com/library/windows/desktop/hh437575(v=VS.85).aspx)

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: oa

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PageCombining
Enables page combining.

If you do not specify this parameter, page combining remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: pc

Required: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MMAgent](./Get-MMAgent.md)

[Set-MMAgent](./Set-MMAgent.md)

[Disable-MMAgent](./Disable-MMAgent.md)

