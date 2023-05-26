# Unreal Reflection Function Parameters (`code completion`)
[https://github.com/boocs/UE-Reflection-Func-Params](https://github.com/boocs/UE-Reflection-Func-Params)

## Table of Contents
- [Info](#info)
- [Installation](#installation)
	- [Different Versions Warning](#different-versions-warning)
- [Branches](#branches)
- [Filtering](#filtering)
- [Parse Log](#parse-log)

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

## Parse Log
```
UPROPERTY params:
	Params(39): Const, Config, GlobalConfig, Localized, Transient, DuplicateTransient, NonPIETransient, NonPIEDuplicateTransient, Ref, Export, NoClear, EditFixedSize, Replicated, NotReplicated, Interp, NonTransactional, Instanced, BlueprintAssignable, SimpleDisplay, EditAnywhere, EditInstanceOnly, EditDefaultsOnly, VisibleAnywhere, VisibleInstanceOnly, VisibleDefaultsOnly, BlueprintReadOnly, BlueprintReadWrite, AssetRegistrySearchable, SaveGame, BlueprintCallable, BlueprintAuthorityOnly, TextExportTransient, SkipSerialization, HideSelfPin, ReplicatedUsing = , Category = , AdvancedDisplay = , BlueprintGetter = , BlueprintSetter = 
	Meta Params(75): AllowAnyActor, AllowPreserveRatio, AllowPrivateAccess, AssetBundles, BlueprintBaseOnly, BlueprintCompilerGeneratedDefaults, ConfigHierarchyEditable, ContentDir, DeprecatedProperty, DisallowedClasses, EditConditionHides, EditFixedOrder, RelativeToGameDir, FixedIncrement, ForceShowEngineContent, ForceShowPluginContent, HideAlphaChannel, HideInDetailPanel, HideViewOptions, IgnoreForMemberInitializationTest, InlineEditConditionToggle, LongPackageName, MakeEditWidget, MakeStructureDefaultValue, MetaClass, MustImplement, Multiple, MultiLine, PasswordField, NoElementDuplicate, NoResetToDefault, NoSpinbox, OnlyPlaceable, RelativePath, RelativeToGameContentDir, ScriptNoExport, ShowOnlyInnerProperties, ShowTreeView, SliderExponent, TitleProperty, UIMin, UIMax, Untracked, DevelopmentOnly, NeedsLatentFixup, LatentCallbackTarget, NeverAsPin, PinHiddenByDefault, PinShownByDefault, AlwaysAsPin, CustomizeProperty, OverridingInputProperty, RequiredInput, Bitmask, ToolTip = , ShortTooltip = , DocumentationPolicy = , DeprecationMessage = , DisplayName = , ScriptName = , AllowAbstract = , AllowedClasses = , ArrayClamp = , ClampMin = , ClampMax = , DisplayAfter = , DisplayPriority = , DisplayThumbnail = , EditCondition = , ExactClass = , ExposeFunctionCategories = , ExposeOnSpawn = , FilePathFilter = , GetOptions = , BitmaskEnum = 
---------------------------------------------------------------------------------------

UFUNCTION params:
	Params(22): BlueprintImplementableEvent, BlueprintNativeEvent, SealedEvent, Exec, Server, Client, NetMulticast, Reliable, Unreliable, BlueprintPure, BlueprintCallable, BlueprintAuthorityOnly, BlueprintCosmetic, BlueprintInternalUseOnly, CallInEditor, CustomThunk, WithValidation, ServiceRequest, ServiceResponse, BlueprintGetter = , BlueprintSetter = , Category = 
	Meta Params(51): Variadic, ReturnDisplayName, ScriptNoExport, BlueprintInternalUseOnly, BlueprintProtected, CallableWithoutWorldContext, CommutativeAssociativeBinaryOperator, DefaultToSelf, DeprecatedFunction, ExpandBoolAsExecs, ScriptMethod, ScriptMethodSelfReturn, ScriptOperator, ScriptConstant, ScriptConstantHost, HideSpawnParms, Latent, MaterialParameterCollectionFunction, NativeBreakFunc, NativeMakeFunc, UnsafeDuringActorConstruction, BlueprintAutocast, NotBlueprintThreadSafe, DynamicOutputParam, DataTablePin, SetParam, MapParam, MapKeyParam, MapValueParam, Bitmask, ArrayParam, InternalUseParam = , ToolTip = , ShortTooltip = , DocumentationPolicy = , DeprecationMessage = , DisplayName = , ScriptName = , AdvancedDisplay = , ArrayParm = , ArrayTypeDependentParams = , AutoCreateRefTerm = , CompactNodeTitle = , CustomStructureParam = , ExpandEnumAsExecs = , HidePin = , Keywords = , LatentInfo = , WorldContext = , DeterminesOutputType = , BitmaskEnum = 
---------------------------------------------------------------------------------------

UCLASS params:
	Params(41): BlueprintType, NotBlueprintType, Blueprintable, NotBlueprintable, MinimalAPI, customConstructor, Intrinsic, noexport, placeable, notplaceable, DefaultToInstanced, Const, Abstract, deprecated, Transient, nonTransient, perObjectConfig, configdonotcheckdefaults, defaultconfig, editinlinenew, noteditinlinenew, hidedropdown, ComponentWrapperClass, collapseCategories, dontCollapseCategories, AdvancedClassDisplay, ConversionRoot, Experimental, EarlyAccessPreview, SparseClassDataType, CustomThunkTemplates, classGroup = , Within = , config = , showCategories = , hideCategories = , showFunctions = , hideFunctions = , autoExpandCategories = , autoCollapseCategories = , dontAutoCollapseCategories = 
	Meta Params(20): BlueprintSpawnableComponent, ChildCanTick, ChildCannotTick, IgnoreCategoryKeywordsInSubclasses, DeprecatedNode, ShowWorldContextPin, BlueprintThreadSafe, UsesHierarchy, ToolTip = , ShortTooltip = , DocumentationPolicy = , DeprecationMessage = , DisplayName = , ScriptName = , IsBlueprintBase = , KismetHideOverrides = , ProhibitedInterfaces = , RestrictedToClasses = , DontUseGenericSpawnObject = , ExposedAsyncProxy = 
---------------------------------------------------------------------------------------

UINTERFACE params:
	Params(4): MinimalAPI, Blueprintable, NotBlueprintable, ConversionRoot, 
	Meta Params(17): DynamicOutputParam, DataTablePin, SetParam, MapParam, MapKeyParam, MapValueParam, Bitmask, Bitflags, UseEnumValuesAsMaskValuesInEditor, AnimBlueprintFunction, ArrayParam, CannotImplementInterfaceInBlueprint, ToolTip = , ShortTooltip = , DocumentationPolicy = , DeterminesOutputType = , BitmaskEnum = 
---------------------------------------------------------------------------------------

USTRUCT params:
	Params(5): NoExport, Atomic, Immutable, BlueprintType, BlueprintInternalUseOnly, 
	Meta Params(7): HiddenByDefault, DisableSplitPin, ToolTip = , ShortTooltip = , DocumentationPolicy = , HasNativeBreak = , HasNativeMake = 
---------------------------------------------------------------------------------------

UDELEGATE params:
	Params(22): BlueprintImplementableEvent, BlueprintNativeEvent, SealedEvent, Exec, Server, Client, NetMulticast, Reliable, Unreliable, BlueprintPure, BlueprintCallable, BlueprintAuthorityOnly, BlueprintCosmetic, BlueprintInternalUseOnly, CallInEditor, CustomThunk, WithValidation, ServiceRequest, ServiceResponse, BlueprintGetter = , BlueprintSetter = , Category = 
	Meta Params(6): Variadic, ReturnDisplayName, InternalUseParam = , ToolTip = , ShortTooltip = , DocumentationPolicy = 
---------------------------------------------------------------------------------------

UMETA params:
	Params(3): Hidden, DisplayName = , ToolTip = 
	Meta Params(0): , 
---------------------------------------------------------------------------------------

UENUM params:
	Params(5): TooTip, BlueprintType, Blueprintable, BlueprintInternalUseOnly, Category = 
	Meta Params(6): Bitflags, UseEnumValuesAsMaskValuesInEditor, Experimental, DisplayName = , ScriptName = , Keywords = 
---------------------------------------------------------------------------------------

UPARAM params:
	Params(2): ref, DisplayName = 
	Meta Params(1): , AllowAbstract = 
---------------------------------------------------------------------------------------
```