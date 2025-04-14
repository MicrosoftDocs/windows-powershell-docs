---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbShare.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbshare?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbShare
---

# Get-SmbShare

## SYNOPSIS
Retrieves the SMB shares on the computer.

## SYNTAX

```
Get-SmbShare [[-Name] <String[]>] [[-ScopeName] <String[]>] [-Scoped <Boolean[]>] [-Special <Boolean[]>]
 [-ContinuouslyAvailable <Boolean[]>] [-ShareState <ShareState[]>]
 [-FolderEnumerationMode <FolderEnumerationMode[]>] [-CachingMode <CachingMode[]>]
 [-LeasingMode <LeasingMode[]>] [-ConcurrentUserLimit <UInt32[]>] [-AvailabilityType <AvailabilityType[]>]
 [-CaTimeout <UInt32[]>] [-EncryptData <Boolean[]>] [-CompressData <Boolean[]>] [-IncludeHidden]
 [-SmbInstance <SmbInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-SmbShare` cmdlet retrieves objects that represent the Server Message Block (SMB) shares
being displayed by the computer.

## EXAMPLES

### Example 1: Get SMB shares on a local computer

```powershell
Get-SMBShare
Name                          ScopeName                     Path                          Description
----                          ---------                     ----                          -----------
ADMIN$                        *                             C:\\Windows                   Remote Admin
C$                            *                             C:\\                          Default share
D$                            *                             D:\\                          Default share
F$                            *                             F:\                           Default share
IPC$                          *                                                           Remote IPC
VMS1                          *                             I:\VMS
```

This command retrieves the SMB shares on the computer.

### Example 2: Get a specific SMB share on the local computer

```powershell
Get-SmbShare -Name "VMS1"
Name                          ScopeName                     Path                          Description
----                          ---------                     ----                          -----------
VMS1                          *                             I:\VMS
```

This command retrieves information about the SMB share named `VMS1` on the local computer.

### Example 3: Display information about the SMB shares on a remote computer

```powershell
Get-SmbShare -CimSession "NEDFS1"

Name        ScopeName Path                Description   PSComputerName
----        --------- ----                -----------   --------------
ADMIN$      *         C:\\Windows          Remote Admin  ae-dfsr-sr-01
C$          *         C:\\                 Default share ae-dfsr-sr-01
D$          *         D:\\                 Default share ae-dfsr-sr-01
E$          *         E:\\                 Default share ae-dfsr-sr-01
IPC$        *                              Remote IPC    ae-dfsr-sr-01
IT dept     *         D:\\data\IT dept                   ae-dfsr-sr-01
procedures  *         D:\\hr\procedures                  ae-dfsr-sr-01
VHD and ISO *         D:\\data\VHD and ISO               ae-dfsr-sr-01
```

This command displays the information about the SMB shares on the remote computer `NEDFS1`.

### Example 4: Display all properties about a specific SMB share on the local computer in a list

```powershell
Get-SmbShare -Name "VMS1" | Format-List -Property *
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
ScopeName             : *
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

This command displays all of the information about the SMB share named `VMS1` on the local computer
as a formatted list.

### Example 5: Get shares on the local failover cluster computer that have scale out availability

```powershell
Get-SmbShare | Where-Object -Property AvailabilityType -Eq ScaleOut
Name                          ScopeName                     Path                          Description
----                          ---------                     ----                          -----------
ClusterStorage$               Contoso-SO                    C:\\ClusterStorage             Cluster Shared Volumes Def...
VMS3                          Contoso-SO                    C:\\ClusterStorage\Volume1\VMS
VMS4                          Contoso-SO                    C:\\ClusterStorage\Volume2\VMS
```

This command retrieves the SMB shares on the computer that have scaled out availability.

### Example 6: Get shares that are connected to a local failover cluster file server resource named "Contoso-FS"

```powershell
Get-SmbShare -ScopeName "Contoso-FS"
Name                          ScopeName                     Path                          Description
----                          ---------                     ----                          -----------
I$                            Contoso-FS                    I:\                           Cluster Default Share
J$                            Contoso-FS                    J:\                           Cluster Default Share
VMS1                          Contoso-FS                    I:\VMS
VMS2                          Contoso-FS                    J:\VMS
```

This command retrieves the SMB shares on the Windows Server failover cluster that are connected to
the clustered file server resource named `Contoso-FS`.

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

Specifies the continuous availability time-out of the shares being enumerated.

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
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

Indicates that the shares being enumerated should request compression from clients.

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

### -LeasingMode

Specifies SMB leasing and oplock behaviors.

```yaml
Type: LeasingMode[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Specifies the scope of the share by name. For use with Windows Server failover cluster file server
resources.

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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this
cmdlet.

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

### -Special

Indicates that the shares to be numerated should be special. Admin share, default shares, IPC$
share are examples of special shares.

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

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object. The **MSFT_SmbShare** object represents the
SMB shares on the computer.

## NOTES

## RELATED LINKS

[New-SmbShare](New-SmbShare.md)

[Remove-SmbShare](Remove-SmbShare.md)

[Set-SmbShare](Set-SmbShare.md)
