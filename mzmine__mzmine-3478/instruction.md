# Issue

**Title:** Accept double digit minor/misc versions in .NET detection regex

## Description

mzmine was failing to detect .NET on Ubuntu 26.04 LTS due to invalid regex.

With multiple .NET installations available, none was detected

```sh
$ dotnet --list-runtimes
Microsoft.AspNetCore.App 8.0.26 [/usr/lib/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 8.0.26 [/usr/lib/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 10.0.11 [/usr/lib/dotnet/shared/Microsoft.NETCore.App]
```

```sh
INFO   io.github.mzmine.taskcontrol.impl.WrappedTask run Processing of task Importing file [...].wiff. Launching WIFF API... done, status CANCELED
SEVERE io.github.mzmine.taskcontrol.AbstractTask error java.lang.RuntimeException: SCIEX Clearcore on Linux requires .NET 6.0.
java.lang.RuntimeException: java.lang.RuntimeException: SCIEX Clearcore on Linux requires .NET 6.0.
```

Invalid regex was only accepting single digit versions.

Message suggests installation of .NET 6 which on modern Linux needs to be done manually

```
wget https://dot.net/v1/dotnet-install.sh
chmod +x dotnet-install.sh
./dotnet-install.sh --runtime dotnet --channel 6.0 --install-dir "$HOME/.dotnet"
```

.NET installed this way fails for the same reason, extending the issue to multiple Linux distributions

```
$ dotnet --list-runtimes
Microsoft.NETCore.App 6.0.36 [/home/[...]/.dotnet/shared/Microsoft.NETCore.App]
```

One consequence of .NET being not detected was inability to read `.wiff2` files.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `04dbdb41def2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.