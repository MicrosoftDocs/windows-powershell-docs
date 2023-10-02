---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmfilescreenexception?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-FsrmFileScreenException

## SYNOPSIS
Gets file screen exceptions.

## SYNTAX

```
Get-FsrmFileScreenException [[-Path] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmFileScreenException** cmdlet gets a file screen exception or all file screen exceptions on the server.

## EXAMPLES

### Example 1: Get all file screen exceptions
```
PS C:\>Get-FsrmFileScreenException
```

This command returns all file screen exceptions defined on the server.

### Example 2: Get file screen exceptions by using a path
```
PS C:\>Get-FsrmFileScreenException Path "C:\Shares\CtrShare03"
```

This command returns the file screen exception on the path C:\Shares\CtrShare03.

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

### -Path
Specifies a valid local path to a folder that is associated with a file screen exception.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileScreenException

## NOTES

## RELATED LINKS

[Set-FsrmFileScreenException](./Set-FsrmFileScreenException.md)

[New-FsrmFileScreenException](./New-FsrmFileScreenException.md)

[Remove-FsrmFileScreenException](./Remove-FsrmFileScreenException.md)

