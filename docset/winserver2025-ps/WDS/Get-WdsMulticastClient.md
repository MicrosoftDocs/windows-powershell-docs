---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsMulticastClient_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/get-wdsmulticastclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WdsMulticastClient
---

# Get-WdsMulticastClient

## SYNOPSIS
Gets a list of clients connected to a multicast transmission or namespace.

## SYNTAX

### InstallImageName
```
Get-WdsMulticastClient [-FileName <String>] [-ImageGroup <String>] -InstallImageName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BootImageName
```
Get-WdsMulticastClient [-FileName <String>] -Architecture <BootImageArchitecture> -BootImageName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BootImageObject
```
Get-WdsMulticastClient -BootImageObject <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### InstallImageObject
```
Get-WdsMulticastClient -InstallImageObject <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### MulticastTransmissionName
```
Get-WdsMulticastClient [-TransmissionName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdsMulticastClient** cmdlet gets a list of clients connected to a multicast transmission or namespace.
Use this cmdlet to return a list of multicast client IDs to use with the Disconnect-WdsMulticastClient cmdlet.
You can specify the transmission by any of the following:

- The transmission name.
- The name and architecture of the boot image, with the file name if it is required to identify the image uniquely, if the transmission is based on a boot image in the Windows Deployment Services image store.
- The boot image object directly, if the transmission is based on a boot image in the Windows Deployment Services image store.
- The file name, if it is required to identify the image uniquely, and, if the transmission is based on an install image in the Windows Deployment Services image store, the name and group name of the install image the transmission is based on.
- The install image object directly, if the transmission is based on an install image in the Windows Deployment Store image store.

## EXAMPLES

### Example 1: Return a list of multicast clients by boot image name
```
PS C:\> Get-WdsMulticastClient -Architecture x86 -BootImageName "Fabrikam Latest setup (x86)"
```

This command returns a list of multicast clients by using the boot image name.

### Example 2: Return a list of multicast clients by boot image object
```
PS C:\> $BootImageObject = Get-WdsBootImage -Architecture x86 -ImageName "Fabrikam Latest setup (x86)"
PS C:\> Get-WdsMulticastClient -BootImageObject $BootImageObject
```

This example returns a list of multicast clients by using a boot image object.

The first command uses the Get-WdsBootImage cmdlet to obtain a boot image object, and stores the object in the variable named $BootImageObject.

The second command returns a list of client for the boot image object.

### Example 3: Return a list of multicast clients by file name
```
PS C:\> Get-WdsMulticastClient -InstallImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim"
```

This command uses the *FileName* parameter to identify the clients for an install image.

### Example 4: Return a list of multicast clients by file name and object
```
PS C:\> $InstallImageObject = Get-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim"
PS C:\> Get-WdsMulticastClient -InstallImageObject $InstallImageObject
```

This example returns a list of multicast clients by using a file name to obtain an object, and then using that object to return a list of clients.

The first command uses the Get-WdsInstallImage cmdlet to obtain an object for an install image, and stores the object in the variable named $InstallImageObject.

The second command returns a list of clients for the object.

### Example 5: Return a list of multicast clients by transmission name
```
PS C:\>Get-WdsMulticastClient -TransmissionName "Custom WinPE multicast"
```

This command returns a list of multicast clients for a transmission named Custom WinPE multicast.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the image with the multicast transmission from which to return the client.
Since it is possible to have the same image name for boot images in different architectures, you should specify the architecture to ensure the correct image is used.

```yaml
Type: BootImageArchitecture
Parameter Sets: BootImageName
Aliases:
Accepted values: Unknown, X86, Ia64, X64, Arm

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -BootImageName
Specifies the name of the boot image with the multicast transmission to return.

```yaml
Type: String
Parameter Sets: BootImageName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -BootImageObject
Specifies the boot image object that has the multicast transmission to return.

```yaml
Type: CimInstance
Parameter Sets: BootImageObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -FileName
Specifies a file name.
Use this parameter to specify the file name for the image if the boot image or install image name does not uniquely identify the image.

```yaml
Type: String
Parameter Sets: InstallImageName, BootImageName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageGroup
Specifies the image group that contains the image from which to return the client.
If you do not specify an image group, and only one image group exists on the server, that image group is used by default.
If more than one image group exists on the server, you must specify an image group.

```yaml
Type: String
Parameter Sets: InstallImageName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallImageName
Specifies the name of the install image with the multicast transmission to return.

```yaml
Type: String
Parameter Sets: InstallImageName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InstallImageObject
Specifies the install image object that has the multicast transmission to return.

```yaml
Type: CimInstance
Parameter Sets: InstallImageObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -TransmissionName
Specifies a name for the multicast transmission.

```yaml
Type: String
Parameter Sets: MulticastTransmissionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsMulticastClient

## NOTES

## RELATED LINKS

[Disconnect-WdsMulticastClient](./Disconnect-WdsMulticastClient.md)

