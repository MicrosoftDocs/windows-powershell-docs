---
external help file: MsftUal_Admin.cdxml-help.xml
Module Name: UserAccessLogging
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ual?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-Ual

## SYNOPSIS
Gets the startup status for UAL.

## SYNTAX

```
Get-Ual [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-Ual** cmdlet gets the startup status for User Access Logging (UAL). 

 -- Enabled.
UAL starts when Windows Server® 2012 starts. 
- Disabled.
UAL does not start when Windows Server 2012 starts.

You can use the **Disable-Ual** and **Enable-Ual** cmdlets to change the startup status.
The **Get-Ual** cmdlet does not check whether the UAL service itself is running.

For more information about UAL, see the User Access Logging Overviewhttp://technet.microsoft.com/library/hh849634.aspx topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get UAL startup configuration
```
PS C:\>Get-Ual
                                                    Enabled PSComputerName

                                                    ------- --------------

                                                      False
```

This command gets the startup status for the current server.
The next time you restart this server, it does not start UAL.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Ual](./Disable-Ual.md)

[Enable-Ual](./Enable-Ual.md)

[Get-UalOverview](./Get-UalOverview.md)

