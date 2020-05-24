---
title: Config
parent: Tutorials
has_children: false
nav_order: 10
---
# Config

1. TOC
{:toc}

## Config.txt

The config file `Content/Config.txt` allows you to configure the framework. Example config:

{: .config-file }

Config.txt

```
ServerUri: http://example.com
UseSimulatedUriInEditor: true
BuildTargets: Dev
AssetBundleVersion: 1
ContentFolders:
  MyContent/
  Example/Content/
DefaultContentFolder: MyContent/
StreamedBundles:
  Bundle1
  Bundle2
  Bundle3
Modules: 
  TextMeshPro
```

The following config values can be set:

| Name                    | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| ServerUri               | URI that points to where remote asset bundles are stored.    |
| BuildTargets            | Controls which model data is generated in the build.         |
| ContentFolders          | Specifies where additional Delight content (views, models, etc) resides. |
| DefaultContentFolder    | Specifies default content folder where new content is placed when created by the Delight Designer |
| StreamedBundles         | Specifies which bundles (by name) should be streamed locally rather than from remote URI. |
| ServerUriLocator        | Name of class that locates server URI based on bundle name. Used e.g. if URI should be determined during run-time. |
| UseSimulatedUriInEditor | Set to true/false indicating if a simulated server URI should be used in the editor. |
| Namespaces              | Namespaces to be included in the generated code and prioritized when infering types. |
| DelightPath             | Delight framework root path.                                 |
| DefaultBasedOn          | Default view all views are based on if the BasedOn attribute isn't specified (UIView if not specified). |
| BaseView                | Custom view all views will inherit from.                     |
| AssetBundleVersion      | Set to non-zero integer to enable caching of asset bundles. Increment to invalidate bundle caches and force new updates. |
| Modules                 | List of modules to activate. When a module is active the DELIGHT_MODULE_\<NAME\> preprocessor symbol is defined, allowing code to be activated/deactivated. In a view's  root element in the XML one can set *Module="Name"* to specify which module the view belongs to. |



