# Changelog

### 3.1.7
* Add setting: `GraphSettingsOverride` which allows you to specify a ResizingMode for a graph type
* Add feature `TaggedPresets` which will automatically apply a preset style when detecting the tag in the node title. [See more](../#tagged-presets)
* Ignore `ControlRig` graph by default
* Fix issue where changing to header comment would not update the comments size

### 3.1.6
* Removed setting `UseRandomColour`. Instead use the new setting `DefaultCommentColorMethod` which is set to `Random` by
  default.
* Comments now wrap node size accounting for their comment bubble bounds. See setting `Use Comment Bubble Bounds` (true
  by default)
* Add plugin icon
* Fix compile issue for non-unity builds, thanks @pladux :)
* Fix issue where plugin's color initialization would not be applied if the engine's default comment color was changed
* Fix crash when shutting down editor (#23)

### 3.1.5
* Add setting `Cache Save Location`. Choose to save the cache file in the `Project/Saved` or `Plugin` folder.
* Fix hitting assert when closing editor due to unloaded source control module

### 3.1.4
* Fix crash when closing editor with source control enabled (issue #23)

### 3.1.3
* Fix issue where AnchorBox corner brush was missing

### 3.1.2
* Show notification to enable Reactive resizing mode when source control is enabled

### 3.1.1
* Fix crash when previewing a collapsed graph node which contains comments
* Fix issue #20 fail to compile plugin on Linux

### 3.1.0
* Add setting `Resizing Mode`. Determines when the comments decide to resize to their containing nodes:
   * `Always (default)` On tick
   * `Reactive (experimental)` On detecting containing node movement
   * `Disabled`
   * If you have source control enabled it is recommended to use Reactive or Disabled resizing mode as even zooming in / out the graph can cause the comments to change.
* Add `Resize button` to the comment controls when Reactive or Disabled resizing mode is enabled. Resizes the comment to fit the containing nodes.
* Remove Global Comment Bubble settings and replace with `Default Comment Bubble` settings (now only applied once on creation)
* Add setting `Enabled Fix For Sort Depth Issue (experimental)`. Fix issue #18 where newly created comments and newly nested comments would not take input until recompiling.
* Add setting `Highlight Containing Nodes On Selection` (enabled by default)
* Header style comments are stored in the cache file instead of being detected by color
* Fix issue where highlighted state would not be reset when an offscreen comment was deselected
* Fix issue where nested comments would need to be selected twice before being able to be moved
* (Potential) Fix for issue where comments would forget containing nodes 
* Remove ignored control rig graph in UE5 and later (you may need to manually remove it from the setting `Ignored Graphs`)

### 3.0.6
* Fix compile issues with UE5 preview

### 3.0.5
* Fix issue #14 where users could not drag off pin on certain graphs

### 3.0.4
* Fix issue with auto insert comment behaviour not working
* Change plugin type to EditorNoCommandlet
* Potential fix for issue #13 where comments would lose the nodes inside

### 3.0.3
* Fix issue where node highlighting would not be reset after the comment was deleted

### 3.0.2
* Contained nodes are now highlighted when the comment is selected
* Fix `Global show bubble when zoomed` not applying correctly

### 3.0.1
* Fix issues when alt dragging nodes
* Fix issue #9: crash on editor startup

### 3.0.0

* Comment Node Cache file will save when saving a graph
    * Added setting `Save comment data on saving graph`
    * Added setting `Save comment data on exit`
* Newly created nodes will auto-insert into existing comment nodes depending on which node / pin you dragged off
    * Added setting `AutoInsertComment` with values `{ Never, Surrounded, Always (default) }`
* Improvements to issue where comments would temporarily disappear until you move them into viewport
* Node selection is cleared when starting to resize a comment

### 2.4.0
* Added setting `Resize Chord` which allows users to change the key chord required to resize the node
* The default keychord to resize nodes is now `SHIFT + Left Mouse Button`
* Fix issue where node would consume on drop mouse events
* Fix compile issues with 4.27

### 2.3.3
* Added Linux to Whitelist Platforms

### 2.3.2
* Fix issue where plugin was starting up when building the game

### 2.3.1

* Change suggested settings for the BlueprintAssist plugin to only `bIgnoreKnotNodesWhenPressingAlt: true`
* Fix issue with bad collision for comment corners

### 2.3.0 (31 May 2021)

* Added notification to suggest ASC settings when the BlueprintAssist plugin is enabled
* Added settings `bIgnoreKnotNodesWhenResizing`, `bIgnoreKnotNodesWhenPressingAlt`
* Fixed compile issues with UE5

### 2.2.0 (24 May 2021)

* Added setting `bDisableResizing`. Disables the auto resizing behavior.
* Fixed issue with [sharing your settings](https://github.com/fpwong/BlueprintAssistWiki/wiki/FAQ#sharing-plugin-settings-through-source-control) through source control.