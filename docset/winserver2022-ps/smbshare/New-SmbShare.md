---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbShare.cdxml-help.xml
Module Name: SmbShare
ms.date: 10/20/2022
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbshare?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmbShare
---

# New-SmbShare

## SYNOPSIS
Creates an SMB share.

## SYNTAX

```
New-SmbShare [-Temporary] [-ContinuouslyAvailable <Boolean>] [-Description <String>]
 [-ConcurrentUserLimit <UInt32>] [-CATimeout <UInt32>]
 [-FolderEnumerationMode <FolderEnumerationMode>] [-CachingMode <CachingMode>]
 [-FullAccess <String[]>] [-ChangeAccess <String[]>] [-ReadAccess <String[]>] [-NoAccess <String[]>]
 [-SecurityDescriptor <String>] [-Path] <String> [-Name] <String> [[-ScopeName] <String>]
 [-EncryptData <Boolean>] [-CompressData <Boolean>] [-LeasingMode <LeasingMode>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `New-SmbShare` cmdlet exposes a file system folder to remote clients as a Server Message Block
(SMB) share.

To delete a share that was created by this cmdlet, use the `Remove-SmbShare` cmdlet.

> [!NOTE]
> The **WhatIf** parameter does not work with this cmdlet.

## EXAMPLES

### Example 1: Create an SMB share

```powershell
$Parameters = @{
    Name = 'Public'
    Path = 'D:\Public'
    FullAccess = 'Contoso\Administrator', 'Contoso\Contoso-HV1$'
}
New-SmbShare @Parameters
```

This command creates an SMB share named `VMSFiles` and grants Full Access permissions to
`Contoso\Administrator`, and `Contoso\Contoso-HV1$`.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 2: Create an encrypted SMB share

```powershell
New-SmbShare -Name "Data" -Path "J:\Data" -EncryptData $True
```

This command creates an encrypted SMB share.

### Example 3: Create an SMB share with Multiple Permissions

```powershell
$Parameters = @{
    Name = 'VMSFiles'
    Path = 'C:\ClusterStorage\Volume1\VMFiles'
    ChangeAccess = 'CONTOSO\Finance Users','CONTOSO\HR Users'
    FullAccess = 'Administrators'
}
New-SmbShare @Parameters
```

This command creates an SMB share named `VMSFiles` and grants Change permissions to the domain
groups `CONTOSO\Finance Users` and `CONTOSO\HR Users`. Full Access permissions to the builtin
`Administrators` group.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

### -CATimeout

Specifies the continuous availability time-out for the share.

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

### -CachingMode

Specifies the caching mode of the offline files for the SMB share. There are five caching modes:

- None.
Prevents users from storing documents and programs offline.
- Manual.
Allows users to identify the documents and programs they want to store offline.
- Programs.
Automatically stores documents and programs offline.
- Documents.
Automatically stores documents offline.
- BranchCache.
Enables BranchCache and manual caching of documents on the shared folder.

```yaml
Type: CachingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Manual, Documents, Programs, BranchCache, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CATimeout

Specifies the continuous availability time-out for the share.

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

### -ChangeAccess

Specifies which users are granted modify permission to access the share. Multiple users can be
specified by using a comma-separated list. Each entry in the comma-separated list must be contained
within single or double quotes, for example `'CONTOSO\Finance Users','CONTOSO\HR Users'`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

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

### -CompressData

Indicates that SMB compression is requested for all client connections that support it.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentUserLimit

Specifies the maximum number of concurrently connected users that the new SMB share may accommodate.
If this parameter is set to zero (0), then the number of users is unlimited. The default value is
zero (0).

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

### -ContinuouslyAvailable

Indicates that the share is continuously available.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Specifies an optional description of the SMB share. A description of the share is displayed by
running the `Get-SmbShare` cmdlet. The description may not contain more than 256 characters. The
default value is no description or an empty description.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptData

Indicates that the share is encrypted.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderEnumerationMode

Specifies which files and folders in the SMB share are visible to users. The acceptable values for
this parameter are:

- `AccessBased`. SMB doesn't display the files and folders for a share to a user unless that user
  has rights to access the files and folders. By default, access-based enumeration is disabled for
  new SMB shares.
- `Unrestricted`. SMB displays files and folders to a user even when the user doesn't have
  permission to access the items.

The default value is `Unrestricted`.

```yaml
Type: FolderEnumerationMode
Parameter Sets: (All)
Aliases:
Accepted values: AccessBased, Unrestricted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullAccess

Specifies which accounts are granted full permission to access the share. Use a comma-separated list
to specify multiple accounts. Each entry in the comma-separated list must be contained within single
or double quotes, for example `'CONTOSO\Finance Users','CONTOSO\HR Users'`.

An account may not be specified more than once in the **FullAccess**, **ChangeAccess**, or
**ReadAccess** parameter lists, but may be specified once in the **FullAccess**, **ChangeAccess**,
or **ReadAccess** parameter list and once in the **NoAccess** parameter list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LeasingMode

Specifies SMB leasing and oplock behaviors for application compatibility. The acceptable values for
this parameter are:

- `Full:` Use default lease and oplock behaviors from SMB3.
- `Shared:` Grant read-caching lease but not write or handle-caching.
- `None:` No oplocks or leases, behave like SMB1 (not recommended).

```yaml
Type: LeasingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies a name for the SMB share. The names `pipe` and `mailslot` are reserved for use by the
computer. Share names can be up to a maximum of 80 characters long. The SMB share name can use any
character allowed by Windows for files and directories. To learn more about naming conventions for
files read the [Naming Files, Paths, and Namespaces](/windows/win32/fileio/naming-a-file) articles.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoAccess

Specifies which accounts are denied access to the SMB share. Multiple accounts can be specified by
supplying a comma-separated list. Each entry in the comma-separated list must be contained within
single or double quotes, for example `'CONTOSO\Finance Users','CONTOSO\HR Users'`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies the path of the location of the folder to share. The path must be fully qualified.
Relative paths or paths that contain wildcard characters aren't permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReadAccess

Specifies which users are granted read permission to access the share. Multiple users can be
specified by supplying a comma-separated list. Each entry in the comma-separated list must be
contained within single or double quotes, for example `'CONTOSO\Finance Users','CONTOSO\HR Users'`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeName

Specifies the scope name of the share. For use with Windows Server failover cluster file server resources.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityDescriptor

Specifies the security descriptor for the SMB share in string format.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Temporary

Specifies the new SMB share is temporary and will not persist beyond the next restart of the
computer. By default, new SMB shares aren't temporary.

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

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet isn't run.

> [!NOTE]
> The **WhatIf** switch doesn't work with this cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object. This cmdlet returns a **MSFT_SmbShare**
object that represents the SMB share.

## NOTES

## RELATED LINKS

[Get-SmbShare](./Get-SmbShare.md)

[Remove-SmbShare](./Remove-SmbShare.md)

[Set-SmbShare](./Set-SmbShare.md)
