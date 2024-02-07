---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbShare.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/set-smbshare?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SmbShare
---

# Set-SmbShare

## SYNOPSIS
Modifies the properties of the SMB share.

## SYNTAX

### Query
```
Set-SmbShare [-Name] <String[]> [[-ScopeName] <String[]>] [-SmbInstance <SmbInstance>] [-Description <String>]
 [-ConcurrentUserLimit <UInt32>] [-CATimeout <UInt32>] [-ContinuouslyAvailable <Boolean>]
 [-FolderEnumerationMode <FolderEnumerationMode>] [-CachingMode <CachingMode>] [-SecurityDescriptor <String>]
 [-EncryptData <Boolean>] [-CompressData <Boolean>] [-LeasingMode <LeasingMode>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-SmbShare -InputObject <CimInstance[]> [-Description <String>] [-ConcurrentUserLimit <UInt32>]
 [-CATimeout <UInt32>] [-ContinuouslyAvailable <Boolean>] [-FolderEnumerationMode <FolderEnumerationMode>]
 [-CachingMode <CachingMode>] [-SecurityDescriptor <String>] [-EncryptData <Boolean>] [-CompressData <Boolean>]
 [-LeasingMode <LeasingMode>] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmbShare** cmdlet modifies the properties of the Server Message Block (SMB) share.

## EXAMPLES

### Example 1: Modify properties of an SMB share
```
PS C:\>Set-SmbShare -Name "VMFiles" -EncryptData $True
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Modify' on Target 'Contoso-SO,VMFiles'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command modifies the properties of an SMB share.

### Example 2: Modify properties of an SMB share without confirmation
```
PS C:\>Set-SmbShare -Name "VMFiles" -EncryptData $True -Force
```

This command modifies the properties of an SMB share without user confirmation.

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

### -CATimeout
Specifies the continuous availability time-out of the SMB share.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CachingMode
Specifies the caching mode of the offline files for the SMB share.
There are five caching modes:

- None.
Prevents users from storing documents and programs offline.
- Manual.
Allows users to identify the documents and programs that they want to store offline.
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
Accept pipeline input: True (ByPropertyName)
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

### -CompressData
Indicates that the shares being enumerated should request compression from clients.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConcurrentUserLimit
Specifies the maximum number of concurrently connected users that the SMB share may accommodate.
If this parameter is set to zero (0), then the number of users is unlimited.
By default, new SMB shares have no limit on the number of concurrent connections.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContinuouslyAvailable
Indicates whether the share is continuously available.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies an optional description of the SMB share.
A description of the share can be displayed by running the Get-SmbShare cmdlet.
Specify an empty string to clear the current description.
The description may not contain more than 256 characters.

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

### -EncryptData
Indicates whether the SMB share is encrypted.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FolderEnumerationMode
Specifies which files and folders in the new SMB share will be visible to the users.
The acceptable values for this parameter are:

- AccessBased.
SMB does not the display the files and folders for a share to a user unless that user has rights to access the files and folders.
By default, access-based enumeration is disabled for new SMB shares.
- Unrestricted.
SMB displays files and folders to a user even when the user does not have permission to access those items. 

The default value is Unrestricted.

```yaml
Type: FolderEnumerationMode
Parameter Sets: (All)
Aliases: 
Accepted values: AccessBased, Unrestricted

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```
### -LeasingMode

Specifies SMB leasing and oplock behaviors for application compatibility. The acceptable values for this parameter are: 

- `Full:` Use default lease and oplock behaviors from SMB3.
- `Shared:` Grant read-caching lease but not write or handle-caching.
- `None:` No oplocks or leases, behave like SMB1 (not recommended).

> [!IMPORTANT]
> We do not recommend disabling oplocks, but may be required in some scenarios. For more information, see [SMB1 Product Clearinghouse](https://techcommunity.microsoft.com/t5/Storage-at-Microsoft/SMB1-Product-Clearinghouse/ba-p/426008).

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
Specifies the name of one or more SMB shares.

```yaml
Type: String[]
Parameter Sets: Query
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
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

### -ScopeName
Specifies the scope name of the SMB share. For use with Windows Server failover cluster file server resources.

```yaml
Type: String[]
Parameter Sets: Query
Aliases: 

Required: False
Position: 2
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

### -SmbInstance
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: Query
Aliases: 
Accepted values: Default, CSV, SBL, SR

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
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare
This cmdlet returns a **MSFT_SmbShare** object that represents the modified share.

## NOTES

## RELATED LINKS

[Get-SmbShare](./Get-SmbShare.md)

[New-SmbShare](./New-SmbShare.md)

[Remove-SmbShare](./Remove-SmbShare.md)
