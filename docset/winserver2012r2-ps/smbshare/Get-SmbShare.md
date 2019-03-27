---
external help file: SmbShare.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Get-SmbShare
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3EC4687D-4FCB-4C2A-A221-8D5320DE24B2
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-SmbShare

## SYNOPSIS
Retrieves the Server Message Block (SMB) shares on the computer.

## SYNTAX

```
Get-SmbShare [[-Name] <String[]>] [[-ScopeName] <String[]>] [-Scoped <Boolean[]>] [-Special <Boolean[]>]
 [-ContinuouslyAvailable <Boolean[]>] [-ShareState <ShareState[]>]
 [-FolderEnumerationMode <FolderEnumerationMode[]>] [-CachingMode <CachingMode[]>]
 [-ConcurrentUserLimit <UInt32[]>] [-AvailabilityType <AvailabilityType[]>] [-CaTimeout <UInt32[]>]
 [-EncryptData <Boolean[]>] [-IncludeHidden] [-SmbInstance <SmbInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMBShare** cmdlet retrieves objects that represent the Server Message Block (SMB) shares being displayed by the computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-SMBShare
Name                          ScopeName                     Path                          Description 
----                          ---------                     ----                          ----------- 
ADMIN$                        *                             C:\Windows                    Remote Admin 
C$                            *                             C:\                           Default share 
ClusterStorage$               Contoso-SO                    C:\ClusterStorage             Cluster Shared Volumes Def... 
D$                            *                             D:\                           Default share 
F$                            *                             F:\                           Default share 
G$                            *                             G:\                           Default share 
H$                            *                             H:\                           Default share 
I$                            Contoso-FS                    I:\                           Cluster Default Share 
I$                            *                             I:\                           Default share 
IPC$                          *                                                           Remote IPC 
J$                            Contoso-FS                    J:\                           Cluster Default Share 
J$                            *                             J:\                           Default share 
K$                            *                             K:\                           Default share 
L$                            *                             L:\                           Default share 
M$                            *                             M:\                           Default share 
N$                            *                             N:\                           Default share 
VMS1                          Contoso-FS                    I:\VMS 
VMS2                          Contoso-FS                    J:\VMS 
VMS3                          Contoso-SO                    C:\ClusterStorage\Volume1\VMS 
VMS4                          Contoso-SO                    C:\ClusterStorage\Volume2\VMS 
VMS5                          *                             D:\VMS
```

This example retrieves the SMB shares on the computer.

### EXAMPLE 2
```
PS C:\>Get-SmbShare -Name VMS1
Name                          ScopeName                     Path                          Description 
----                          ---------                     ----                          ----------- 
VMS1                          Contoso-FS                    I:\VMS
```

This example retrieves the SMB shares on the computer named VMS1.

### EXAMPLE 3
```
PS C:\>Get-SmbShare -Name VMS1 | Format-List

Name        : VMS1 
ScopeName   : Contoso-FS 
Path        : I:\VMS 
Description :
```

This example displays the information about the SMB shares on the computer named VMS1.

### EXAMPLE 4
```
PS C:\>Get-SmbShare -Name VMS1 | Format-List -Property *
PresetPathAcl         : System.Security.AccessControl.DirectorySecurity 
ShareState            : Online 
AvailabilityType      : Clustered 
ShareType             : FileSystemDirectory 
FolderEnumerationMode : Unrestricted 
CachingMode           : Manual 
CATimeout             : 0 
ConcurrentUserLimit   : 0 
ContinuouslyAvailable : True 
CurrentUsers          : 3 
Description           : 
EncryptData           : False 
Name                  : VMS1 
Path                  : I:\VMS 
Scoped                : True 
ScopeName             : Contoso-FS 
SecurityDescriptor    : O:BAG:DUD:(A;;FA;;;S-1-5-21-219828122-4198910963-4161819395-500)(A;;FA;;;S-1-5-21-219828122-419 
                        8910963-4161819395-1106)(A;;FA;;;S-1-5-21-219828122-4198910963-4161819395-1109) 
ShadowCopy            : False 
Special               : False 
Temporary             : False 
Volume                : \\?\Volume{b02c4ba7-e6f1-11e1-93eb-0008a1c0ef0d}\ 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbShare 
CimInstanceProperties : {AvailabilityType, CachingMode, CATimeout, ConcurrentUserLimit...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This example displays all of the information about the SMB shares on the computer named VMS1.

### EXAMPLE 5
```
PS C:\>Get-SmbShare | Where-Object -Property AvailabilityType -Eq ScaleOut
Name                          ScopeName                     Path                          Description 
----                          ---------                     ----                          ----------- 
ClusterStorage$               Contoso-SO                    C:\ClusterStorage             Cluster Shared Volumes Def... 
VMS3                          Contoso-SO                    C:\ClusterStorage\Volume1\VMS 
VMS4                          Contoso-SO                    C:\ClusterStorage\Volume2\VMS
```

This example retrieves the SMB shares on the computer with scaled out availability.

### EXAMPLE 6
```
PS C:\>Get-SmbShare -ScopeName Contoso-FS
Name                          ScopeName                     Path                          Description 
----                          ---------                     ----                          ----------- 
I$                            Contoso-FS                    I:\                           Cluster Default Share 
J$                            Contoso-FS                    J:\                           Cluster Default Share 
VMS1                          Contoso-FS                    I:\VMS 
VMS2                          Contoso-FS                    J:\VMS
```

This example retrieves the SMB shares on the computer that are connect to the SMB server named Contoso-FS.

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

### -AvailabilityType
Specifies the cluster type of the shares being enumerated.

```yaml
Type: AvailabilityType[]
Parameter Sets: (All)
Aliases: 
Accepted values: NonClustered, Clustered, ScaleOut, CSV, DFS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CaTimeout
Specifies the continuous availability timeout of the shares being enumerated.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CachingMode
Specifies the caching mode of the shares being enumerated.

```yaml
Type: CachingMode[]
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

### -ConcurrentUserLimit
Specifies the concurrent user limit of the shares being enumerated.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContinuouslyAvailable
Indicates that the shares being enumerated should be continuously available.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptData
Indicates that the shares being enumerated should be encrypted.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FolderEnumerationMode
Specifies the folder enumeration mode of the shares being enumerated.

```yaml
Type: FolderEnumerationMode[]
Parameter Sets: (All)
Aliases: 
Accepted values: AccessBased, Unrestricted

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeHidden
Indicates that shares that are created and used internally are also enumerated.

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

### -Name
Specifies one or more SMB shares by share name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeName
Specifies the scope of the share by name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scoped
Indicates that the shares to be numerated should be scoped.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShareState
Specifies the state of the shares being enumerated.

```yaml
Type: ShareState[]
Parameter Sets: (All)
Aliases: 
Accepted values: Pending, Online, Offline

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
{{Fill SmbInstance Description}}

```yaml
Type: SmbInstance
Parameter Sets: (All)
Aliases: 
Accepted values: Default, CSV

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Special
Indicates that the shares to be numerated should be special.
Admin share, default shares, IPC$ share are examples of special shares.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_SmbShare object represents the SMB shares on the computer.

## NOTES

## RELATED LINKS

[New-SmbShare](./New-SmbShare.md)

[Remove-SmbShare](./Remove-SmbShare.md)

[Set-SmbShare](./Set-SmbShare.md)

