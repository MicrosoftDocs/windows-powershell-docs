---
external help file: SmbShare_Cmdlets.xml
Module Name: SmbShare
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbshareaccess?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SmbShareAccess

## SYNOPSIS
Retrieves the access control list (ACL) of the Server Message Block (SMB) share.

## SYNTAX

### Query (cdxml) (Default)
```
Get-SmbShareAccess [-Name] <String[]> [[-ScopeName] <String[]>] [-SmbInstance <SmbInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-SmbShareAccess -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMBShareAccess** cmdlet gets objects that represent the rights that have been granted to security principles to access the Server Message Block (SMB) share.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-SmbShareAccess -Name VMFiles
Name                    ScopeName               AccountName             AccessControlType       AccessRight 
----                    ---------               -----------             -----------------       ----------- 
VMFiles                 Contoso-SO                 Contoso\Administrator      Allow                   Full 
VMFiles                 Contoso-SO                 Contoso\Contoso-HV1$          Allow                   Full
```

This example retrieves the ACL of an SMB share named VMFiles.

### EXAMPLE 2
```
PS C:\>Get-SmbShareAccess -Name VMFiles -ScopeName Contoso-SO | Format-List

Name              : VMFiles 
ScopeName         : Contoso-SO 
AccountName       : Contoso\Administrator 
AccessControlType : Allow 
AccessRight       : Full 
 
Name              : VMFiles 
ScopeName         : Contoso-SO 
AccountName       : Contoso\Contoso-HV1$ 
AccessControlType : Allow 
AccessRight       : Full
```

This example displays the information about the ACL of an SMB share named VMFiles connected to the SMB server named Contoso-SO.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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
Specifies the name of the SMB share for which the access rights are retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeName
Specifies the scope of the share by name.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: Query (cdxml)
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbShareAccessControlEntry
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_SmbShareAccessControlEntry object is returned for the specified share.

## NOTES

## RELATED LINKS

[Block-SmbShareAccess](./Block-SmbShareAccess.md)

[Grant-SmbShareAccess](./Grant-SmbShareAccess.md)

[Revoke-SmbShareAccess](./Revoke-SmbShareAccess.md)

[Unblock-SmbShareAccess](./Unblock-SmbShareAccess.md)

