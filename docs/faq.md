# FAQ

## Comments failing to remember containing comments 

Check that the following settings have the correct values:

* `Save Comment Node Data to File` set to `true`
* `Save Comment Node Data on Saving Graph` OR `Save Comment Node Data on Exit` set to `true`

Check that the save file is being saved correctly: look at the `Cache Save Location` setting, there will be a `.json` file generated:
 
* **Plugin**: `PluginFolder/ASCCache/PROJECT_ID.json`
* **Project**: `ProjectFolder/Saved/AutoSizeComments/AutoSizeCommentsCache.json`

!!! info "Plugin folder location"

    If you installed from the marketplace the plugin folder will be located at 

    `C:/Program Files/Epic Games/UE_5.1/Engine/Plugins/Marketplace/AutoSizeComments`

