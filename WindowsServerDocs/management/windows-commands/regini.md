---
title: regini
description: "Windows Commands topic for **** - "
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5ff18dc3-5bd8-400a-b311-fd73a3267e8c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---
# regini

>Applies To: Windows Server&reg; 2016, Windows Server&reg; 2012 R2, Windows Server&reg; 2012

Modifies the registry from the command line or a script, and applies changes that were preset in one or more text files. You can create, modify, or delete registry keys, in addition to modifying the permissions on the registry keys.
for details on the format and content of the text script file that regini.exe uses to make changes to the registry, see the regini reference document originally provided as part of the Windows Server 2000 Resource Kit, now available at the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=201803](http://go.microsoft.com/fwlink/?LinkId=201803).
## Syntax
```
regini [-m \\machinename | -h hivefile hiveroot][-i n] [-o outputWidth][-b] textFiles...
```
### Parameters
|-m <\\\computerName>|Specifies the remote computer name with a registry that is to be modified. Use the format **\\\computerName**.|
|-------------|----------------------------------------------------------|
|-h <hivefile hiveroot>|Specifies the local registry hive to modify. You must specify the name of the hive file and the root of the hive in the format **hivefile hiveroot**.|
|-i <n>|Specifies the level of indentation to use to indicate the tree structure of registry keys in the command output. The **regdmp.exe** tool (which gets a registry key s current permissions in binary format) uses indentation in multiples of four, so the default value is **4**.|
|-o <outputwidth>|Specifies the width of the command output, in characters. if the output will appear in the command window, the default value is the width of the window. if the output is directed to a file, the default value is **240** characters.|
|-b|Specifies that **regini.exe** output is backward compatible with previous versions of **regini.exe**. See the remarks section for details.|
|textfiles|Specifies the name of one or more text files that contain registry data. Any number of ANSI or Unicode text files can be listed.|
### remarks
The following guidelines apply primarily to the content of the text files that contain registry data that you apply by using **regini.exe**.
-   Use the semicolon as an end-of-line comment character. It must be the first non-blank character in a line.
-   Use the backslash to indicate continuation of a line. The command will ignore all characters from the backslash up to (but not including) the first non-blank character of the next line. if you include more than one space before the backslash, it is replaced by a single space.
-   Use hard-tab characters to control indentation. This indentation indicates the tree structure of the registry keys; however, these characters are converted to a single space regardless of their position.
### additional references
-   [Command-Line Syntax Key](command-line-syntax-key.md)