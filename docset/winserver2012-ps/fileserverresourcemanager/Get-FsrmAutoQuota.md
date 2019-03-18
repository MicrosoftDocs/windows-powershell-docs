---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: D1D3A53B-CFC3-47EB-A46E-39418A86F5D2
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-FsrmAutoQuota

## SYNOPSIS
Gets auto apply quotas on a server.

## SYNTAX

```
Get-FsrmAutoQuota [[-Path] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmAutoQuota** cmdlet gets an auto apply quota or all auto apply quota on a volume or folder.
An auto apply quota is a quota template that you assign to a parent volume or folder.

## EXAMPLES

### Example 1: Get all auto apply quotas
```
PS C:\>Get-FsrmAutoQuota
```

This command gets all the auto apply quotas on the local server.

### Example 2: Get auto apply quotas by using a path
```
PS C:\>Get-FsrmAutoQuota -Path "C:\Share01\..."
```

This command gets all the auto apply quotas in C:\ Share01 plus all the auto apply quotas in all subfolders of C:\Share01.

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
Specifies a valid local path to a folder.

This parameter supports recursive and wildcard paths.
To specify a recursive path, add \...
to a path.
For example, C:\ Share01\...
indicates all the auto apply quotas in C:\ Share1 plus all the auto apply quotas in any and all subfolders of C:\ Share01.To specify a wildcard in a path, you can add the asterisk (*) and the question mark (?) to a path.
For example, C:\ Share01\*A indicates all the auto apply quotas in C:\ Share01 plus all the auto apply quotas in subfolders of C:\ Share01 that have a name that begins with the letter A.

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

## NOTES

## RELATED LINKS

[Set-FsrmAutoQuota](./Set-FsrmAutoQuota.md)

[New-FsrmAutoQuota](./New-FsrmAutoQuota.md)

[Update-FsrmAutoQuota](./Update-FsrmAutoQuota.md)

[Remove-FsrmAutoQuota](./Remove-FsrmAutoQuota.md)

