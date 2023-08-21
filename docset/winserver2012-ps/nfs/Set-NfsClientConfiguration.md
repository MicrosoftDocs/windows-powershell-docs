---
external help file: NFS_Cmdlets.xml
Module Name: NFS
online version: https://learn.microsoft.com/powershell/module/nfs/set-nfsclientconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NfsClientConfiguration

## SYNOPSIS
Changes configuration settings for an NFS client.

## SYNTAX

```
Set-NfsClientConfiguration [-AsJob] [-Authentication <String[]>] [-CaseSensitiveLookup <Boolean>]
 [-CimSession <CimSession[]>] [-DefaultAccessMode <UInt32>] [-InputObject <CimInstance[]>]
 [-MountRetryAttempts <UInt32>] [-MountType <String>] [-PassThru] [-ReadBufferSize <UInt32>]
 [-RpcTimeoutSec <UInt32>] [-ThrottleLimit <Int32>] [-TransportProtocol <String[]>]
 [-UseReservedPorts <Boolean>] [-WriteBufferSize <UInt32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NfsClientConfiguration** cmdlet changes configuration settings for a Network File System (NFS) client.
You can use the **Get-NfsClientConfiguration** cmdlet to get a configuration object for an NFS client.

## EXAMPLES

### Example 1: Modify configuration settings for an NFS client
```
PS C:\> Set-NfsClientConfig -DefaultAccessMode 755 -ReadBufferSize 64 -WriteBufferSize 64
```

This command modifies configuration settings for an NFS client on the local computer.
This command sets the default permissions for newly created files to 755, and it sets the sizes of the read and write buffers to 64 kilobytes (KB).

The default permission of 755 sets read, write, and execute permissions (7 - rwx) for the owner, read and execute permissions (5 -- r-x) for the group, and read and execute permissions (5 -- r-x) for others.

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

### -Authentication
Specifies one or more authentication types that an NFS client can use to access NFS shares.

Valid values are: 
 -- Sys (AUTH_SYS authentication)
- Krb5 (Kerberos v5 authentication)
- Krb5i (Kerberos v5 authentication with integrity checking)
- Krb5p (Kerberos v5 authentication with privacy)
- All
- Default

If you specify **All**, Services for NFS configures Sys, Krb5, Krb5i, and Krb5p on the share.
If you specify **Default**, Services for NFS configures Sys, Krb5, and Krb5i on the share.

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

### -CaseSensitiveLookup
Specifies that the NFS client must perform case-sensitive lookups of file names for NFS shares that are mounted locally.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
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

### -DefaultAccessMode
Specifies the default permission mode that an NFS client assigns for newly created files, in UNIX-style mode bits.
The permissions that this property specifies are set for all new files created on mounted shares.

With UNIX-style mode bits (also known as the three-digit octal notation), each numeral represents a different component of the permission set: user class, group class, and "others" class.

Each of these digits is the sum of its component bits.
As a result, specific bits add to the sum:

The read bit adds 4 to its total (in binary 100).
The write bit adds 2 to its total (in binary 010).
The execute bit adds 1 to its total (in binary 001).

Individual octal digit values represent the following:
0 -- no permission
1 -- x     execute
2 -- w     write
3 -- wx   write and execute
4 -- r      read
5 -- r-x   read and execute
6 -- rw    read and write
7 - rwx   read, write, and execute

The following are examples of UNIX-style mode bits:

777 = "-rwxrwxrwx" = rwx for all

754 = "-rwxr-xr--" = rwx for owner, r-x for group, r-- for other

124 = "--x-w-r--" = x for owner, w for group, r for other

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MountRetryAttempts
Specifies the number of retries that the NFS client performs when it is attempting a soft mount.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountType
Specifies the type of mount that the NFS client uses when it is mounting a share that an NFS server exported.
Valid values are Hard and Soft.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
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

### -ReadBufferSize
Specifies the size of the read buffer (in kilobytes) that the NFS client uses.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -RpcTimeoutSec
Specifies the time-out for a remote procedure call (RPC), in seconds, that the NFS client enforces for outstanding RPC calls.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 8
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

### -TransportProtocol
Specifies the transport protocol that the NFS client uses for NFS, Network Lock Manager (NLM), Port Mapper (PMAP), or MAPSVR protocols.

Valid values are: 
- TCP
- UDP
- TCP+UDP

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseReservedPorts
Specifies whether the NFS client uses network ports less than 1024.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteBufferSize
Specifies the size of the write buffer (in kilobytes) that the NFS client uses.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 32
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsClientConfig

## NOTES

## RELATED LINKS

[Get-NfsClientConfiguration](./Get-NfsClientConfiguration.md)

