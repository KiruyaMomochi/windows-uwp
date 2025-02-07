---
title: search Command
description: Queries the sources for available applications that can be installed
ms.date: 04/28/2020
ms.topic: overview
ms.localizationpriority: medium
---

# search command (winget)


The **search** command of the [winget](index.md) tool queries the sources for available applications that can be installed.  

The **search** command can show all applications available, or it can be filtered down to a specific application. The **search** command is used typically to identify the string to use to install a specific application.

## Usage

`winget search [[-q] \<query>] [\<options>]`

![Screenshot of the Windows Power Shell window displaying the results of the winget search.](./images/search.png)

## Arguments

The following arguments are available.

| Argument  | Description |
 --------------|-------------|
| **-q,--query** |  The query used to search for an app. |
| **-?, --help** |  Gets additional help on this command. |

> [!NOTE]
> The query argument is positional. Wild-card style syntax is not supported. This is most often the string of characters you expect to help find the package you are searching for.

## Show all

If the search command includes no filters or options, it will display all available applications in the default source. You can also search for all applications in another source if you pass in just the **source** option.

## Search strings

Search strings can be filtered with the following options.

| Option  | Description |
 --------------|-------------|
| **--id**        |   Limits the search to the ID of the application. The ID includes the publisher and the application name. |
| **--name**      |  Limits the search to the name of the application. |
| **--moniker**  |    Limits the search to the moniker specified. |
| **--tag**    |  Limits the search to the tags listed for the application. |
| **--command**   |   Limits the search to the commands listed for the application. |
| **--verbose-logs** | Used to override the logging setting and create a verbose log. |

The string will be treated as a substring. The search by default is also case insensitive. For example, `winget search micro` could return the following:

* Microsoft
* Microscope
* MyMicro

## Search options

The search commands supports a number of options or filters to help limit the results.

| Option  | Description |
|--------------|-------------|
| **-e, --exact**  |     Uses the exact string in the query, including checking for case-sensitivity. It will not use the default behavior of a substring.  |  
| **-n, --count**      |  Restricts the output of the display to the specified count. |
| **-s, --source**     |  Restricts the search to the specified [source](source.md) name.  |
| **--header** | Optional Windows-Package-Manager REST source HTTP header. |
| **--accept-source-agreements** | Used to accept the source license agreement, and avoid the prompt. |

## Searching across multiple sources

If you want to narrow results down to a specific source, just pass the `--source` or `-s` parameter and specify what you want. For example, you might want to see if Visual Studio Code is in the store by running `winget search “Visual Studio Code” -s msstore`. This search uses "Visual Studio Code" as the query.

## Related topics

* [Use the winget tool to install and manage applications](index.md)
