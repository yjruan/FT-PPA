### Use Precompiled Executable Files

For users who do not want to compile the source code, precompiled executable files for Linux and Windows are available from the [Releases](https://github.com/yjruan/Nexus/releases) page.

Users can download the appropriate executable file according to their operating system:

* Linux executable: `Nexus`
* [Windows executable](https://github.com/yjruan/Nexus/releases/Nexus-windows.zip)

After downloading and extracting the file, place `input.dat` in the same working directory as the executable file.

For Linux users, grant execution permission and run:

```bash
chmod +x Nexus
./Nexus
```

For Windows users, run the executable file from the command line:

```bash
Nexus.exe
```

In both cases, Nexus will automatically search for `input.dat`, read the analysis settings, and perform the corresponding calculation listed in the [Features Overview](../README.md#features-overview) section.
