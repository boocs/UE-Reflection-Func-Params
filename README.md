# Unreal Reflection Function Parameters (`code completion`)
[https://github.com/boocs/UE-Reflection-Func-Params](https://github.com/boocs/UE-Reflection-Func-Params)

This extension adds all `Unreal Engine reflection func params` to code completion.
* Supports Unreal versions 4.27.2, 5.1.1, 5.2.0
    * Extension will work with any Unreal version.
    * Download the version which matches your version the closest
    * `Note:` If your version doesn't match, some paramaters, that you add to your code, may cause Build to fail
* Parsed params from the Unreal source code
    * Also contains parsed  parameter `documentation` from source code
    * Manually added a couple missing params from UPROPERTY and well as params from UMETA and UPARAM
* This uses the VSCode snippets functionality 
* Works with all VSCode extensions
    * `VSCode + Microsoft C++ extension` (See my [fixes](https://gist.github.com/boocs/f63a4878156295b6e854cac68672f305) extension)
    * `VSCode + clangd extension` (See my [unreal-clangd](https://github.com/boocs/unreal-clangd) extension)

