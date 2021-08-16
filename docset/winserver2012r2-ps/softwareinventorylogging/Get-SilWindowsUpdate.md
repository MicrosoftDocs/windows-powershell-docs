---
external help file: MsftSil_WindowsUpdate.cdxml-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/get-silwindowsupdate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SilWindowsUpdate
---

# Get-SilWindowsUpdate

## SYNOPSIS
Displays the point in time list of all Windows updates installed on the computer.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see https://support.microsoft.com/kb/3000850.

## SYNTAX

```
Get-SilWindowsUpdate [[-ID] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SilWindowsUpdate** cmdlet displays a list of Windows updates installed on a computer that runs the Windows Server operating system.
If you do not specify the **ID** parameter, the cmdlet displays all Windows updates installed on the system.
Software Inventory Logging collects the data at the point in time that you run the cmdlet.

## EXAMPLES

### Example 1: Display a list of Windows updates
```
PS C:\> Get-SilWindowsUpdate


ID             : KB280289
InstallDate    : 4/1/2013
```

This command displays a point in time list of Windows updates installed on the local computer.

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
Enter a computer name or a session object, such as the output of a New-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -ID
Specifies an array of IDs of software updates installed on the computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/InventoryLogging/MsftSil_WindowsUpdate
This cmdlet returns an object that encapsulates the updates installed on the computer.
That object includes the following properties: 

- **ID** (**System.String**)
- **InstallDate** (**System.DateTime**)

## NOTES

## RELATED LINKS

[Start-SilLogging](./Start-SilLogging.md)

[Get-SilUalAccess](./Get-SilUalAccess.md)

[Get-SilComputer](./Get-SilComputer.md)

[Get-SilData](./Get-SilData.md)

[Get-SilLogging](./Get-SilLogging.md)

