# .NET 8.0 Upgrade Plan

## Execution Steps

Execute steps below sequentially one by one in the order they are listed.

1. Validate that an .NET 8.0 SDK required for this upgrade is installed on the machine and if not, help to get it installed.
2. Ensure that the SDK version specified in global.json files is compatible with the .NET 8.0 upgrade.
3. Upgrade APDU\APDU.csproj
4. Upgrade U2FLib\U2FLib.csproj
5. Upgrade JustTest\JustTest.csproj
6. Upgrade SoftU2FDaemon\SoftU2FDaemon.csproj

## Settings

This section contains settings and data used by execution steps.

### Excluded projects

No projects are excluded from this upgrade.

### Aggregate NuGet packages modifications across all projects

NuGet packages used across all selected projects or their dependencies that need version update in projects that reference them.

| Package Name                                 | Current Version | New Version | Description                        |
|:---------------------------------------------|:---------------:|:-----------:|:-----------------------------------|
| Microsoft.EntityFrameworkCore.Design         |     7.0.3       |   8.0.27    | Recommended for .NET 8.0           |
| Microsoft.EntityFrameworkCore.Sqlite         |     7.0.3       |   8.0.27    | Recommended for .NET 8.0           |
| Microsoft.Extensions.DependencyInjection     |     7.0.0       |   8.0.1     | Recommended for .NET 8.0           |
| Microsoft.Extensions.Logging                 |     7.0.0       |   8.0.1     | Recommended for .NET 8.0           |
| Microsoft.Extensions.Logging.Console         |     7.0.0       |   8.0.1     | Recommended for .NET 8.0           |
| System.Security.Cryptography.ProtectedData   |     6.0.0       |   8.0.0     | Recommended for .NET 8.0           |

### Project upgrade details

This section contains details about each project upgrade and modifications that need to be done in the project.

#### APDU\APDU.csproj modifications

Project properties changes:
- Target framework should be changed from `net6.0` to `net8.0`

Other changes:
- No additional feature upgrades were identified.

#### U2FLib\U2FLib.csproj modifications

Project properties changes:
- Target framework should be changed from `net6.0-windows` to `net8.0-windows`

NuGet packages changes:
- `Microsoft.EntityFrameworkCore.Sqlite` should be updated from `7.0.3` to `8.0.27` (*recommended for .NET 8.0*)
- `System.Security.Cryptography.ProtectedData` should be updated from `6.0.0` to `8.0.0` (*recommended for .NET 8.0*)

Other changes:
- No additional feature upgrades were identified.

#### JustTest\JustTest.csproj modifications

Project properties changes:
- Target framework should be changed from `net6.0-windows7.0` to `net8.0-windows7.0`

NuGet packages changes:
- `System.Security.Cryptography.ProtectedData` should be updated from `6.0.0` to `8.0.0` (*recommended for .NET 8.0*)
- `Microsoft.EntityFrameworkCore.Design` should be updated from `7.0.3` to `8.0.27` (*recommended for .NET 8.0*)

Other changes:
- No additional feature upgrades were identified.

#### SoftU2FDaemon\SoftU2FDaemon.csproj modifications

Project properties changes:
- Target framework should be changed from `net6.0-windows10.0.17763.0` to `net8.0-windows`

NuGet packages changes:
- `Microsoft.Extensions.DependencyInjection` should be updated from `7.0.0` to `8.0.1` (*recommended for .NET 8.0*)
- `Microsoft.Extensions.Logging` should be updated from `7.0.0` to `8.0.1` (*recommended for .NET 8.0*)
- `Microsoft.Extensions.Logging.Console` should be updated from `7.0.0` to `8.0.1` (*recommended for .NET 8.0*)

Other changes:
- No additional feature upgrades were identified.
