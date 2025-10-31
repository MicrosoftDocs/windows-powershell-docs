---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/test-nfsmappingstore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-NfsMappingStore
---

# Test-NfsMappingStore

## SYNOPSIS
Verifies that an identity mapping store is configured correctly.

## SYNTAX

```
Test-NfsMappingStore [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Test-NfsMappingStore** cmdlet verifies that you correctly set up and configured an identity mapping store.
You can use **Get-NfsMappingStore** to get the mapping configuration of an NFS server.

For an Active Directory Lightweight Directory Services (AD LDS) store or any other Lightweight Directory Access Protocol (LDAP) mapping store, the **Test-NfsMappingStore** cmdlet verifies that a Network File System (NFS) server can reach a configured AD LDS server and that the identity mapping schema is applied.

For an Active Directory mapping store, the **Test-NfsMappingStore** cmdlet verifies that an NFS server can reach the relevant domain controller, and that the domain functional level is Windows Server 2003 R2 or later

## EXAMPLES

### Example 1: Test the configuration of an identity mapping store
```
PS C:\> Test-NfsMappingStore
```

This command tests the configuration of an identity mapping store on a local NFS server.

## PARAMETERS

### -AsJob
Indicates that this cmdlet runs the command as a background job on a remote computer.
Use this parameter to run commands that take an extensive time to finish.

When you use the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.
You can continue to work in the session while the job finishes.
To manage the job, use the **Job** cmdlets.
To get the job results, use the Receive-Job cmdlet.

The *AsJob* parameter resembles using the Invoke-Command cmdlet to run a Start-Job command remotely.
However, with *AsJob*, the job is created on the local computer, even though the job runs on a remote computer, and the results of the remote job are automatically returned to the local computer.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251) and [about_Remote_Jobs](https://go.microsoft.com/fwlink/?LinkID=135184).

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

### None

## NOTES

## RELATED LINKS

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

