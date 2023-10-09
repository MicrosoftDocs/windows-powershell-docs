---
external help file: SmbShare_Cmdlets.xml
Module Name: SmbShare
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbshare?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-SmbShare

## SYNOPSIS
Creates a new Server Message Block (SMB) share.

## SYNTAX

```
New-SmbShare [-Name] <String> [-Path] <String> [[-ScopeName] <String>] [-AsJob] [-CachingMode <CachingMode>]
 [-CATimeout <UInt32>] [-ChangeAccess <String[]>] [-CimSession <CimSession[]>] [-ConcurrentUserLimit <UInt32>]
 [-ContinuouslyAvailable <Boolean>] [-Description <String>] [-EncryptData <Boolean>]
 [-FolderEnumerationMode <FolderEnumerationMode>] [-FullAccess <String[]>] [-NoAccess <String[]>]
 [-ReadAccess <String[]>] [-Temporary] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-SMBShare** cmdlet exposes a file system folder to remote clients as a new Server Message Block (SMB) share.

To delete a share that was created by this cmdlet, use the Remove-SMBShare cmdlet.

> [!NOTE]
> The **WhatIf** parameter does not work with this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-SmbShare -Name VMSFiles -Path C:\ClusterStorage\Volume1\VMFiles -FullAccess Contoso\Administrator, Contoso\Contoso-HV1$
Name                          ScopeName                     Path                          Description
----                          ---------                     ----                          -----------
VMSFiles                      Contoso-SO                    C:\ClusterStorage\Volume1\...
```

This example creates a new SMB share.

### EXAMPLE 2
```
PS C:\>New-SmbShare -Name Data -Path J:\Data -EncryptData $true
Name                          ScopeName                     Path                          Description
----                          ---------                     ----                          -----------
Data                          Contoso-FS                    J:\Data
```

This example creates a new encrypted SMB share.

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

### -CachingMode
Specifies the caching mode of the offline files for the SMB share.
There are five different caching modes:

 -- None: Prevents users from storing documents and programs offline.

 -- Manual: Allows users to identify the documents and programs they want to store offline.

 -- Programs: Automatically stores documents and programs offline.

 -- Documents: Automatically stores documents offline.

 -- BranchCache: Enables BranchCache and manual caching of documents on the shared folder.

```yaml
Type: CachingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CATimeout
Specifies the continuous availability timeout for the share.

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
Specifies which user will be granted modify permission to access the share.
Multiple users can be specified by using a comma-separated list.

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

### -ConcurrentUserLimit
Specifies the maximum number of concurrently connected users that the new SMB share may accommodate.
If this parameter is set to zero (0), then the number of users is unlimited.
The default value is zero (0).

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
Specifies an optional description of the new SMB share.
A description of the share is displayed by running the Get-SmbShare cmdlet.
The description may not contain more than 256 characters.
The default value no description, or an empty description

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
Specifies which files and folders in the new SMB share are visible to users.
The acceptable values for this parameter are:

 -- AccessBased: SMB will not display the files and folders for a share to a user unless that user has rights to access the files and folders.
By default, access-based enumeration is disabled for new SMB shares.

 -- Unrestricted: SMB will display files and folders to a user even when the user does not have permission to access the items.

The default value is Unrestricted.

```yaml
Type: FolderEnumerationMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullAccess
Specifies which accounts are granted full permission to access the share.
Use a comma-separated list to specify multiple accounts.
An account may not be specified more than once in the FullAccess, ChangeAccess, or ReadAccess parameter lists, but may be specified once in the FullAccess, ChangeAccess, or ReadAccess parameter list and once in the NoAccess parameter list.

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

### -Name
Specifies a name for the new SMB share.
The name may be composed of any valid file name characters, but must be less than 80 characters in length.
The names `pipe` and `mailslot` are reserved for use by the computer.

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

### -NoAccess
Specifies which accounts are denied access to the share.
Multiple accounts can be specified by supplying a comma-separated list.

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
Specifies the path to the location of the folder to share.
The path must be fully qualified; relative paths or paths that contain wildcard characters are not permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReadAccess
Specifies which user is granted read permission to access the share.
Multiple users can be specified by supplying a comma-separated list.

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
Specifies the scope name of the share.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Temporary
Specifies the lifetime of the new SMB share.
A temporary share does not persist beyond the next reboot of the computer.
By default, new SMB shares are persistent, and non-temporary.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_SmbShare object represents the new SMB share.

## NOTES

## RELATED LINKS

[Get-SmbShare](./Get-SmbShare.md)

[Remove-SmbShare](./Remove-SmbShare.md)

[Set-SmbShare](./Set-SmbShare.md)
