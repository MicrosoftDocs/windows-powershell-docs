---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmquota?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-FsrmQuota

## SYNOPSIS
Gets FSRM quotas on the server.

## SYNTAX

```
Get-FsrmQuota [[-Path] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmQuota** cmdlet gets a File Server Resource Manager (FSRM) quota or all FSRM quotas on the server.

## EXAMPLES

### Example 1: Get all quotas
```
PS C:\>Get-FsrmQuotaTemplate
```

This command gets all quotas on the server.

### Example 2: Get quotas by using a path
```
PS C:\>Get-FsrmQuotaTemplate -Path "C:\Shares\..."
```

This command gets all of the quotas in C:\Share01 plus all of the quotas in all subfolders of C:\Share01.

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
Specifies the local folder that contains the quota.

This parameter supports recursive and wildcard paths.
To specify a recursive path, add \...
to a path.
For example, C:\ Share01\...
indicates all of the quotas in C:\ Share1 plus all the quotas in any and all subfolders of C:\ Share01.
To specify a wildcard in a path, you can add the asterisk (*) and the question mark (?) to a path.
For example, C:\ Share01\*A indicates all of the quotas in C:\ Share01 plus all the quotas in subfolders of C:\ Share01 that have a name that begins with the letter A.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMQuota

## NOTES

## RELATED LINKS

[Set-FsrmQuotaTemplate](./Set-FsrmQuotaTemplate.md)

[New-FsrmQuotaTemplate](./New-FsrmQuotaTemplate.md)

[Remove-FsrmQuotaTemplate](./Remove-FsrmQuotaTemplate.md)

