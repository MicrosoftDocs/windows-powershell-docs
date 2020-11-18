---
external help file: WDAC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: EF357356-FDCE-4016-AB5E-34F841B412CB
manager: dansimp
---

# Disable-WdacBidTrace

## SYNOPSIS
Disables Built-in Diagnostics Tracing (BidTrace) for troubleshooting WDAC components.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-WdacBidTrace [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-WdacBidTrace [-Path] <String> [-AsJob] [-CimSession <CimSession>] [-PassThru] [-Platform <String>]
 [-ProcessId <UInt32>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-WdacBidTrace [-AsJob] [-CimSession <CimSession>] [-PassThru] [-Platform <String>]
 [-ThrottleLimit <Int32>] -Folder <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Disable-WdacBidTrace [-AsJob] [-CimSession <CimSession>] [-PassThru] [-Platform <String>]
 [-ThrottleLimit <Int32>] [-IncludeAllApplications] [-Confirm] [-WhatIf]
```

## DESCRIPTION
For more information about data access tracing (Bidtrace), see Data Access Tracing (Windows 8)http://msdn.microsoft.com/en-us/library/hh829624(VS.85).aspx.

## EXAMPLES

### 1:
```
PS C:\> Disable-WdacBidTrace -Path "C:\temp\abc.exe" -Platform 32-bit
```

This command disables the BidTrace for the application "C:\temp\abc.exe" on the 32-bit platform:

### 2:
```
PS C:\> Disable-WdacBidTrace -Path "C:\temp\abc.exe" -ProcessId 1234 -Platform 32-bit
```

This command disables the BidTrace for the application "C:\temp\abc.exe" on the 32-bit platform and disables BidTrace for a particular instance of "abc.exe" (with Process ID = 1234):

### 3:
```
PS C:\> Disable-WdacBidTrace -Folder "C:\temp"
```

This command disables the BidTrace for all applications located inside C:\temp on the native platform:

### 4:
```
PS C:\> Disable-WdacBidTrace -IncludeAllApplications -Platform 64-bit
```

This command disables the BidTrace for all 64-bit applications:

### 5:
```
PS C:\> $bidSetting = Enable-WdacBidTrace -Path "C:\temp\abc.exe" -Platform 64-bit -PassThru
<use C:\temp\abc.exe>
Disable-WdacBidTrace $bidSetting
```

This command first enables the WDAC BidTrace for the 64-bit application "C:\temp\abc.exe".
It also saves the result into a PowerShell variable that can be reused in Disable-WdacBidTrace:

## PARAMETERS

### -InputObject
Disable the BidTrace represented by the specified BidTrace setting objects.
Enter a variable that contains the objects, or type a command or expression that gets the objects.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Disable BidTrace for this application full path.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProcessId
Disable BidTrace only for this process ID.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Folder
Disable BidTrace for all applications under this folder.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeAllApplications
Disable BidTrace for all applications.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Platform
The platform architecture of the WDAC BidTrace setting.
Possible values are '32-bit', '64-bit' or 'All'.
The default is '32-bit' on a 32-bit process and '64-bit' on a 64-bit process.
This is the platform architecture on the remote machine if this command is executed on a remote CIM session.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Passes the object created by this cmdlet through the pipeline.
By default, this cmdlet does not pass any objects through the pipeline.

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
Type: CimSession
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdacBidTrace[]

## NOTES

## RELATED LINKS

[Enable-WdacBidTrace](./Enable-WdacBidTrace.md)

[Get-WdacBidTrace](./Get-WdacBidTrace.md)



