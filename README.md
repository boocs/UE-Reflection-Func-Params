# Unreal Reflection Function Parameters (`code completion`)
[https://github.com/boocs/UE-Reflection-Func-Params](https://github.com/boocs/UE-Reflection-Func-Params)

## Table of Contents
- [Info](#info)
- [Installation](#installation)
	- [Different Versions Warning](#different-versions-warning)
- [Branches](#branches)
- [Filtering](#filtering)


---

## Info
This extension adds all `Unreal Engine reflection func params` to code completion.
* Supports Unreal versions 4.27.2, 5.1.1, 5.2.0
    * Extension will work with any Unreal version.
    * Download the version which matches your version the closest
    * `Note:` If your version doesn't match, some paramaters, that you add to your code, may cause Build to fail
* Uses parsed params from the Unreal source code
    * Also contains parsed parameter `documentation` from source code
    * Manually added a couple missing params from UPROPERTY as well as params from UMETA and UPARAM
* This uses the VSCode snippets functionality
    * This allows for parameter filtering [see below](#filtering)
* Works with all VSCode extensions
    * `VSCode + Microsoft C++ extension` (See my [fixes](https://gist.github.com/boocs/f63a4878156295b6e854cac68672f305) extension)
    * `VSCode + clangd extension` (See my [unreal-clangd](https://github.com/boocs/unreal-clangd) extension)

## Installation

This extension is installed manually with a VSIX file downloaded from this github

To install the VSIX file in VSCode do the following:

![](https://user-images.githubusercontent.com/62588629/225083466-39ca4a93-e06a-4a04-83ba-82d60b548513.png)

1. Click the extensions icon
2. Click the ellipsis (3 dots)
3. Choose Install from VSIX...

## Different Versions Warning
You `can` install multiple versions of this extension

Because of this you should `disable these extensions globally` and only enable them for the Unreal Project workspaces you want.

`Note:` If you don't you'll have way too many code completions for parameters

## Branches
This github contains branches that lists all parameters the extension/Unreal version supports

## Filtering
Using snippets allow rudimentry filtering. Type the keyword + `a space` to filter code completion for parameters for a specific function.

When done correctly code completion will list all parameters for the keyword you specify. 

`Note:` Meta parameters have their own filter keyword. Some may show up when you type other keywords but it won't list all of them.

For example: 
* If you type 'up ' (`remember the space`) it'll list all the normal parameters for `UPROPERTY`.
* You'll need to type 'mup ' for a list of all `meta parameters` for UPROPERTY.

---
Here's a list of the specific filter keywords for all the reflection functions:

`Note:` You type these without quotes. Remember the `space` after. Capitalization doesn't matter.

* UPROPERTY: '`up `' , meta: '`mup `'
* UFUNCTION: '`uf `' , meta: '`muf `'
* UCLASS: '`uc `' , meta: '`muc `'
* UINTERFACE: '`ui `' , meta: '`mui `'
* USTRUCT: '`us `' , meta: '`mus `'
* UDELEGATE: '`ud `' , meta: '`mud `'
* UENUM: '`ue `' , meta: '`mue `'
* UMETA: '`um `' , meta: '`mum `'
* UPARAM: '`uparam `' , meta: '`muparam `'

`Note:` All filter keywords appear after the parameter during code completion. For example for the UPROPERTY `ToolTip` parameter:
```
ToolTip                                 - mUP [PropertyMetadata] rflparam UE5
```

https://github.com/boocs/UE-Reflection-Func-Params/assets/62588629/d50926b0-cf6b-4eee-9d8d-685bf57e8d11
