---
external help file: WDAC_Cmdlets.xml
Module Name: Wdac
online version: https://docs.microsoft.com/powershell/module/wdac/get-wdacbidtrace?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WdacBidTrace

## SYNOPSIS
Retrieves Built-in Diagnostics Tracing (BidTrace) for troubleshooting WDAC components.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WdacBidTrace [[-Path] <String>] [-AsJob] [-CimSession <CimSession>] [-Platform <String>]
 [-ProcessId <UInt32>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WdacBidTrace [-AsJob] [-CimSession <CimSession>] [-Platform <String>] [-ThrottleLimit <Int32>]
 -Folder <String>
```

### UNNAMED_PARAMETER_SET_3
```
Get-WdacBidTrace [-AsJob] [-CimSession <CimSession>] [-Platform <String>] [-ThrottleLimit <Int32>]
 [-IncludeAllApplications]
```

## DESCRIPTION
The Get-WdacBidTrace retrieves a list of BidTrace setting for different applications.

For more information about data access tracing (Bidtrace), see Data Access Tracing (Windows 8)http://msdn.microsoft.com/en-us/library/hh829624(VS.85).aspx.

## EXAMPLES

### 1:
```
C:\PS>Get-WdacBidTrace
```

Get all BidTrace settings for both 32-bit and 64-bit platform:

### 2:
```
C:\PS>Get-WdacBidTrace -Path "C:\temp\abc.exe" -Platform 32-bit
```

Gets the BidTrace setting for the application "C:\temp\abc.exe" and the specific settings for all of its process instances on the 32-bit platform:

### 3:
```
C:\PS>Get-WdacBidTrace -Path "C:\temp\abc.exe" -ProcessId 1234 -Platform 64-bit
```

Gets the BidTrace setting for the application "C:\temp\abc.exe" with Process ID = 1234 on the 64-bit platform:

### 4:
```
C:\PS>Get-WdacBidTrace -Path "C:\*\abc.exe" -Platform 64-bit
```

Gets the BidTrace setting for the application matching the wildcard pattern "C:\*\abc.exe" on the 64-bit platform:

### 5:
```
C:\PS>Get-WdacBidTrace -Folder "C:\temp" -Platform 32-bit
```

Gets the BidTrace setting for the application located inside "C:\temp" on the 32-bit platform:

### 6:
```
C:\PS>Get-WdacBidTrace -Folder "C:\t*mp" -Platform 32-bit
```

Gets the BidTrace setting for the application located inside a folder matching the wildcard pattern "C:\t*mp" on the 32-bit platform:

### 7:
```
C:\PS>Get-WdacBidTrace -IncludeAllApplications -Platform 32-bit
```

Gets the BidTrace setting (applied to all 32-bit applications) on the computer:

### 8:
```
C:\PS>$bidArray = Get-WdacBidTrace
```

Save the result into a PowerShell variable:

## PARAMETERS

### -Path
Gets only WDAC BidTrace settings that are associated with the specified application full path.
You can use wildcard characters.
The default is to return all WDAC BidTrace settings.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ProcessId
Gets only WDAC BidTrace settings that are associated with the specified Process ID.
The parameter ProcessId is optional.
The default is to return all WDAC BidTrace settings.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Folder
Gets only WDAC BidTrace settings that are associated with the specified folder.
You can use wildcard characters.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -IncludeAllApplications
Gets only WDAC BidTrace settings that are associated with 'all applications'.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
The default is 'All'.
This is the platform architecture on the remote machine if this command is executed on a remote CIM session.

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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdacBidTrace[]

## NOTES

## RELATED LINKS

[Disable-WdacBidTrace](./Disable-WdacBidTrace.md)

[Enable-WdacBidTrace](./Enable-WdacBidTrace.md)



