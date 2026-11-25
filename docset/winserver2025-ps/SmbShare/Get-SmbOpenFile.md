---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbOpenFile.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbopenfile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbOpenFile
---

# Get-SmbOpenFile

## SYNOPSIS
Retrieves basic information about the files that are open on behalf of the clients of the SMB server.

## SYNTAX

```
Get-SmbOpenFile [[-FileId] <UInt64[]>] [[-SessionId] <UInt64[]>] [[-ClientComputerName] <String[]>]
 [[-ClientUserName] <String[]>] [[-ScopeName] <String[]>] [[-ClusterNodeName] <String[]>] [-IncludeHidden]
 [-SmbInstance <SmbInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbOpenFile** cmdlet retrieves basic information about the files that are open on behalf of the clients of the Server Message Block (SMB) server.

## EXAMPLES

### Example 1: Get information about opened files
```
PS C:\>Get-SMBOpenFile
FileId              SessionId           Path                ShareRelativePath   ClientComputerName  ClientUserName
------              ---------           ----                -----------------   ------------------  --------------
4415226382229       4415226380377       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226382237       4415226380385       C:\ClusterStorag... VM4\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
4415226383517       4415226380393       C:\ClusterStorag... VM4\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
4415226383521       4415226380393       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226383529       4415226380393       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226383569       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
4415226383589       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813541326973       8813272891469       I:\VMS\VM1\VIRTU... VM1\VIRTUAL MACH... 192.168.101.13      Contoso\Contoso-HV1$
8813541326977       8813272891469       I:\VMS\VM1\Virtu... VM1\Virtual Mach... 192.168.101.13      Contoso\Contoso-HV1$
8813541326993       8813272891469       I:\VMS\VM1.VHDX     VM1.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813541326997       8813272891469       I:\VMS\VM1\Virtu... VM1\Virtual Mach... 192.168.101.13      Contoso\Contoso-HV1$
8813541327109       8813272891469       I:\VMS\VM1.VHDX     VM1.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813272891805       8813272891441       I:\VMS\VM1\Virtu... VM1\Virtual Mach... 192.168.101.13      Contoso\Contoso-HV1$
8813272891813       8813272891449       I:\VMS\VM1\VIRTU... VM1\VIRTUAL MACH... 192.168.101.13      Contoso\Contoso-HV1$
8813541327273       8813272891581       D:\VMS\VM5\VIRTU... VM5\VIRTUAL MACH... 192.168.102.13      Contoso\Contoso-HV1$
8813541327281       8813272891585       D:\VMS\VM5\VIRTU... VM5\VIRTUAL MACH... 192.168.102.13      Contoso\Contoso-HV1$
8813272892105       8813272891457       C:\ClusterStorag... VM3\Virtual Mach... 192.168.101.13      Contoso\Contoso-HV1$
8813272892113       8813272891461       C:\ClusterStorag... VM3\VIRTUAL MACH... 192.168.101.13      Contoso\Contoso-HV1$
8813541328145       8813272891517       J:\VMS\VM2\VIRTU... VM2\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
8813541328149       8813272891517       J:\VMS\VM2\Virtu... VM2\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
8813541328157       8813272891517       J:\VMS\VM2\Virtu... VM2\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
8813541328213       8813272891517       J:\VMS\VM2.VHDX     VM2.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813272892765       8813272891489       J:\VMS\VM2\Virtu... VM2\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
8813541328225       8813272891517       J:\VMS\VM2.VHDX     VM2.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813272892773       8813272891493       J:\VMS\VM2\VIRTU... VM2\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
8813541328421       8813272891609       D:\VMS\VM5\Virtu... VM5\Virtual Mach... 192.168.102.13      Contoso\Contoso-HV1$
8813541328425       8813272891609       D:\VMS\VM5\VIRTU... VM5\VIRTUAL MACH... 192.168.102.13      Contoso\Contoso-HV1$
8813541328457       8813272891609       D:\VMS\VM5\Virtu... VM5\Virtual Mach... 192.168.102.13      Contoso\Contoso-HV1$
8813541328501       8813272891613       C:\ClusterStorag... VM3.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813541328529       8813272891613       C:\ClusterStorag... VM3.VHDX            192.168.101.13      Contoso\Contoso-HV1$
```

This command retrieves basic information about the files that are open on behalf of the clients of the SMB server.

### Example 2: Get information about an opened file
```
PS C:\>Get-SmbOpenFile -FileId 4415226383569 | Select-Object -Property *
ClientComputerName    : 192.168.102.14
ClientUserName        : Contoso\Contoso-HV2$
ClusterNodeName       : Contoso-FS2
ContinuouslyAvailable : True
Encrypted             : False
FileId                : 4415226383569
Locks                 : 1
Path                  : C:\ClusterStorage\Volume2\VMS\VM4.VHDX
Permissions           : 1179785
ScopeName             : Contoso-SO
SessionId             : 4415226380393
ShareRelativePath     : VM4.VHDX
PSComputerName        :
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbOpenFile
CimInstanceProperties : {ClientComputerName, ClientUserName, ClusterNodeName, ContinuouslyAvailable...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command retrieves all information about the file identified as 4415226383569 that is open on behalf of the clients of the SMB server.

### Example 3: Get information about a file opened for an SMB client
```
PS C:\>Get-SmbOpenFile -SessionId 4415226380393
FileId              SessionId           Path                ShareRelativePath   ClientComputerName  ClientUserName
------              ---------           ----                -----------------   ------------------  --------------
4415226383517       4415226380393       C:\ClusterStorag... VM4\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
4415226383521       4415226380393       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226383529       4415226380393       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226383569       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
4415226383589       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
```

This command retrieves basic information about the files that are open on behalf of the SMB client identified as 4415226380393 of the SMB server.

### Example 4: Get information about a file opened for an SMB client on an SMB server
```
PS C:\>Get-SmbOpenFile -ScopeName "Contoso-SO"
FileId              SessionId           Path                ShareRelativePath   ClientComputerName  ClientUserName
------              ---------           ----                -----------------   ------------------  --------------
4415226382229       4415226380377       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226382237       4415226380385       C:\ClusterStorag... VM4\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
4415226383517       4415226380393       C:\ClusterStorag... VM4\VIRTUAL MACH... 192.168.102.14      Contoso\Contoso-HV2$
4415226383521       4415226380393       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226383529       4415226380393       C:\ClusterStorag... VM4\Virtual Mach... 192.168.102.14      Contoso\Contoso-HV2$
4415226383569       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
4415226383589       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813272892105       8813272891457       C:\ClusterStorag... VM3\Virtual Mach... 192.168.101.13      Contoso\Contoso-HV1$
8813272892113       8813272891461       C:\ClusterStorag... VM3\VIRTUAL MACH... 192.168.101.13      Contoso\Contoso-HV1$
8813541328501       8813272891613       C:\ClusterStorag... VM3.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813541328529       8813272891613       C:\ClusterStorag... VM3.VHDX            192.168.101.13      Contoso\Contoso-HV1$
```

This command retrieves basic information about the files that are open on behalf of the SMB client of the SMB server named Contoso-SO.

### Example 5: Get information about files that have a specified file name extension
```
PS C:\>Get-SmbOpenFile | Where-Object -Property ShareRelativePath -Match ".VHDX"
FileId              SessionId           Path                ShareRelativePath   ClientComputerName  ClientUserName
------              ---------           ----                -----------------   ------------------  --------------
4415226383569       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
4415226383589       4415226380393       C:\ClusterStorag... VM4.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813541326993       8813272891469       I:\VMS\VM1.VHDX     VM1.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813541327109       8813272891469       I:\VMS\VM1.VHDX     VM1.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813541328213       8813272891517       J:\VMS\VM2.VHDX     VM2.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813541328225       8813272891517       J:\VMS\VM2.VHDX     VM2.VHDX            192.168.102.14      Contoso\Contoso-HV2$
8813541328501       8813272891613       C:\ClusterStorag... VM3.VHDX            192.168.101.13      Contoso\Contoso-HV1$
8813541328529       8813272891613       C:\ClusterStorag... VM3.VHDX            192.168.101.13      Contoso\Contoso-HV1$
```

This command retrieves basic information about the files that have the file name extension of .VHDX that are open on behalf of the SMB client of the SMB server.

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

### -ClientComputerName
Specifies the filters for the returned open files so that only files opened from the specified client computer are returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientUserName
Specifies the name of the user whose open files are retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClusterNodeName
Specifies, in the case of a share hosted by a windows cluster, the name of the server which hosts the open files that are retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileId
Specifies the file identifier (ID) of the file for which the information is retrieved.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeHidden
Indicates that handles that are created and used internally are enumerated also.

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
Specifies the scope of the open files that are retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionId
Specifies a session ID.
This cmdlet returns only files that have been opened in the specified session.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: (All)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbOpenFile
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
This cmdlet return a **MSFT_SmbOpenFile** object that represents the files opened on the SMB server.

## NOTES

## RELATED LINKS

[Close-SmbOpenFile](./Close-SmbOpenFile.md)

