---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_Admin.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/enable-ual?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-Ual
---

# Enable-Ual

## SYNOPSIS
Enables UAL at the next restart.

## SYNTAX

```
Enable-Ual [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-Ual** cmdlet enables User Access Logging (UAL) at the next restart of the server.
You can use the *CimSession* parameter to run the cmdlet on a remote server.
This cmdlet does not start the UAL service.

You can use the **Get-Ual** cmdlet to check the startup status for UAL.
You can use the Disable-Ual and Enable-Ual cmdlets to change the startup status.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Enable UAL at restart
```
PS C:\>Enable-Ual
```

This command enables UAL for the local server.
The next time you restart the server, UAL logging begins.
You can use the **Get-Ual** cmdlet to check UAL startup status.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Ual](./Disable-Ual.md)

[Get-Ual](./Get-Ual.md)

[Get-UalOverview](./Get-UalOverview.md)

