---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/connect-virtualdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Connect-VirtualDisk

## SYNOPSIS
Connects a disconnected virtual disk to the specified computer when using the Storage Spaces subsystem.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Connect-VirtualDisk [-FriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Connect-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_3
```
Connect-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>] -Name <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
Connect-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -UniqueId <String[]>
```

## DESCRIPTION
The **Connect-VirtualDisk** cmdlet connects a disconnected virtual disk to the specified computer when using the Storage Spaces subsystem.

To connect to a virtual disk to a remote computer, use the **CimSession** parameter, or use the **Enter-PSSession** or **Invoke-Command** cmdlets in conjunction with **Connect-VirtualDisk**.

## EXAMPLES

### Example 1: Connect a virtual disk to the local computer
```
PS C:\>Connect-VirtualDisk -FriendlyName "VirtualDisk1"
```

This example connects the virtual disk named VirtualDisk1 to the local computer.

### Example 2: Connect all disconnected virtual disks on a remote server
```
PS C:\>Get-VirtualDisk -CimSession Srv2 | Where-Object -Filter { $_.OperationalStatus -eq "Detached" } | Connect-VirtualDisk
```

This example uses the **Get-VirtualDisk** cmdlet to get all virtual disk objects on the computer Srv2 (by using the **CimSession** parameter).
It then pipes the objects to the **Where-Object** cmdlet to filter out all virtual disks except those with the "Detached" operational status.
Finally, it pipes these objects to the **Connect-VirtualDisk** cmdlet.

### Example 3: Connect all disconnected virtual disks on two remote computers by using Invoke-Command
```
PS C:\>Invoke-Command -ComputerName Srv1, Srv2 -ScriptBlock { Get-VirtualDisk | Where-Object -Filter { $_.OperationalStatus -eq "Detached" } | Connect-VirtualDisk }
```

This example uses the Invoke-Command cmdlet to run the cmdlets specified in Example 2 (now specified in the **ScriptBlock** parameter) on multiple remote computers simultaneously, with all processing done in parallel on each computer and only the results being sent back to the local PowerShell session.

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

### -FriendlyName
Specifies the friendly name of the virtual disk that you want to connect.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies a VirtualDisk object or an array of VirtualDisk objects to connect.
Enter a VirtualDisk CIM object or an array of VirtualDisk objects.

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

### -Name
Specifies the name of the virtual disk that you want to connect.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing a virtual disk.
By default, this cmdlet does not generate any output.

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

### -UniqueId
Specifies the UniqueID of the virtual disk to connect.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe VirtualDisk objects to the InputObject parameter to specify one or more virtual disks to connect to the local computer.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The Connect-VirtualDisk cmdlet does not output objects unless you use the Passthru parameter, in which case it outputs objects that represent the virtual disks that you connected.

## NOTES

## RELATED LINKS

[Invoke-Command](https://go.microsoft.com/fwlink/p/?LinkID=135225)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)

