---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/set-kmslicenseinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/10/2026
PlatyPS schema version: 2024-05-01
title: Set-KmsLicenseInfo
---

# Set-KmsLicenseInfo

## SYNOPSIS
Sets the Key Management Services (KMS) license configuration.

## SYNTAX

### __AllParameterSets

```
Set-KmsLicenseInfo [[-ServerName] <String>] [[-Port] <Int32>] [[-Domain] <String>]
 [[-ActivationInterval] <Int32>] [[-RenewalInterval] <Int32>]
 [[-ListeningPort] <Int32>] [[-Priority] <String>] [[-DnsPublishing] <Boolean>]
 [[-HostCaching] <Boolean>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Set-KmsLicenseInfo` cmdlet changes Key Management Services (KMS) client and host settings on
the local computer. Specify only the settings that you want to change. Settings for omitted
parameters remain unchanged.

The cmdlet returns a structured object that indicates whether the operation succeeded. When an
operation fails, the cmdlet includes the available Windows error code and error message in the
object instead of writing an error to the console.

> [!NOTE]
> `Set-KmsLicenseInfo` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Configure a specific KMS host

This command configures the local KMS client to contact the fictitious host `kms01.example.com` on
TCP port `1688`. Setting a specific host disables KMS host autodiscovery. This command changes the
local computer's licensing configuration, so confirm the host name and port before you run it.

```powershell
Set-KmsLicenseInfo -ServerName 'kms01.example.com' -Port 1688
```

The command returns an object with a **Success** property that indicates whether the licensing service
applied the configuration.

### Example 2: Configure KMS host behavior

This command configures a KMS host to publish its DNS record, use normal priority, and listen on TCP
port `1688`. It also provides activation and renewal intervals to clients. The interval values are
in minutes.
Changing these settings can affect KMS discovery and activation across the environment, so review
the values before you run the command.

```powershell
$kmsConfiguration = @{
  DnsPublishing    = $true
  Priority         = 'Normal'
  ListeningPort    = 1688
  ActivationInterval = 120
  RenewalInterval  = 10080
}

Set-KmsLicenseInfo @kmsConfiguration
```

The KMS default activation interval is `120` minutes, and the default renewal interval is `10080`
minutes (seven days).

## PARAMETERS

### -ActivationInterval

Specifies, in minutes, how often unactivated KMS clients try to connect to a KMS host. KMS supports
values from `15` through `43200` minutes (30 days), and the default is `120` minutes (two hours).

The cmdlet doesn't define a range-validation attribute for this parameter. The licensing service
validates the value and returns failure details in the result object when it rejects a value. If you
omit this parameter, the current setting remains unchanged.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 3
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AsJob

Runs the command as a background job. The command returns a job object that you can use with the
PowerShell job cmdlets. The implicit remoting proxy provides this parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -DnsPublishing

Specifies whether the KMS host publishes its service resource (SRV) record in Domain Name System
(DNS). Specify `$true` to enable publishing or `$false` to disable it. By default, a KMS host
publishes its SRV record in DNS. If you omit this parameter, the current setting remains unchanged.

```yaml
Type: System.Boolean
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 7
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Domain

Specifies the DNS domain in which the KMS client searches for KMS SRV records. This setting has no
effect when you configure a specific KMS host with **ServerName**. If you omit this parameter, the
current setting remains unchanged.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 2
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -HostCaching

Specifies whether a KMS client caches a discovered KMS host. Specify `$true` to enable caching or
`$false` to disable it. The KMS client enables host caching by default. If you omit this parameter,
the current setting remains unchanged.

```yaml
Type: System.Boolean
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 8
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ListeningPort

Specifies the TCP port on which a KMS host listens for client activation requests. The KMS default
listening port is `1688`. The cmdlet doesn't define a range-validation attribute for this parameter;
the licensing service validates the value. If you omit this parameter, the current setting remains
unchanged.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 5
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Port

Specifies the TCP port that the KMS client uses to contact the KMS host that **ServerName**
specifies. The KMS default port is `1688`. The cmdlet doesn't define a range-validation attribute
for this parameter; the licensing service validates the value. If you omit this parameter, the
current setting remains unchanged.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 1
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Priority

Specifies the process priority for the KMS host. The default is `Normal`. Use `Low` with care
because other active applications or server roles can prevent a low-priority KMS host from
responding in a timely manner. If you omit this parameter, the current setting remains unchanged.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 6
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Normal
- Low
HelpMessage: ''
```

### -RenewalInterval

Specifies, in minutes, how often activated KMS clients try to renew their activation. KMS supports
values from `15` through `43200` minutes (30 days), and the default is `10080` minutes (seven days).

The cmdlet doesn't define a range-validation attribute for this parameter. The licensing service
validates the value and returns failure details in the result object when it rejects a value. If you
omit this parameter, the current setting remains unchanged.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 4
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ServerName

Specifies the host name of the KMS host that the client contacts. Configuring a specific KMS host
disables KMS host autodiscovery. If you omit this parameter, the current setting remains unchanged.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 0
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

## INPUTS

### None

This cmdlet doesn't accept input from the pipeline.

## OUTPUTS

### System.Management.Automation.PSCustomObject

When you run the cmdlet synchronously, it returns a structured result object. A successful result
contains **Success** set to `$true`. A failed result contains **Success** set to `$false`, an
**ErrorCode** value formatted as a hexadecimal Windows error code when one is available, and an
**ErrorMessage** value. The cmdlet can return `$null` if it can't obtain the licensing service.

### System.Management.Automation.Job

When you use **AsJob**, the implicit remoting proxy returns a job object that contains the command
result.

## NOTES

This cmdlet changes persistent KMS configuration on the local computer. Run it from an elevated
PowerShell session. Before changing settings, record the current configuration with
`Get-KmsLicenseInfo` so that you can restore it if necessary.

All configuration parameters are optional, and the cmdlet changes only parameters that you
specify. The integer parameters don't have `ValidateRange` attributes. **Priority** is the only
parameter with explicit value validation and accepts `Normal` or `Low`.

The source function doesn't define an **AsJob** parameter. The published command surface retains
**AsJob** because its implicit remoting proxy adds the parameter.

## RELATED LINKS

- [Key Management Services (KMS) activation planning for Windows Server](/windows-server/get-started/kms-activation-planning)
- [Activate using Key Management Service](/windows/deployment/volume-activation/activate-using-key-management-service-vamt)
- [Slmgr.vbs Options for Obtaining Volume Activation Information](/windows-server/get-started/activation-slmgr-vbs-options)
- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)
