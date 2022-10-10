# Yaap

## Yet Another Argument Parser
**Yaap** is a simple argument parser for .NET. It is licensed as GPL-3.0-or-later.

CLASS: **KuiperZone.Utility.ArgumentParser**

Argument keys are to be prefixed with '-' or "--", as shown by the following command line example:

    APP value -size=100 -filename "Dir/Folder/File Name" --debug.

The "value" is a floating value. All other items are treated as key-value pairs. Above,
the "debug" flag will be interpreted as the key-value pair: -debug=True.

Usage 1:

    public static int Main(string[] args)
    {
        // With array construction
        var args = new KuiperZone.Utility.ArgumentParser(args);

        Console.WriteLine("VALUE: " + args.Value);

        if (args.GetOrDefault("v", false) || args.GetOrDefault("version", false))
        {
            Console.WriteLine("1.0.0");
            return 0;
        }
    }

Usage 2:

    // With string construction
    var args = new KuiperZone.Utility.ArgumentParser("value -size=100 -filename \"Dir/Folder/File Name\" --debug");

## Copyright & License

Copyright (C) Andy Thomas, 2022.
Website: https://kuiper.zone

Yaap is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License
as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

Yaap is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty
of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

### Attritubion
Yaap was originally based on MIT licensed work by Richard Lopes, although modifications have been substantial.
No formal copyright notice found, but see: https://www.codeproject.com/Articles/3111/C-NET-Command-Line-Arguments-Parser
