---
title: LayoutRoot
parent: Views
grand_parent: API
nav_order: 16
---

# LayoutRoot

Based on [UICanvas](UICanvas)

## Description

Represents a layout root canvas under which all UI views must reside.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| AdditionalShaderChannels | [AdditionalCanvasShaderChannels](http://docs.unity3d.com/ScriptReference/AdditionalCanvasShaderChannels.html) | Enum mask of possible shader channel properties that can also be included when the Canvas mesh is created. |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| BlockingObjects | [BlockingObjects](http://docs.unity3d.com/ScriptReference/BlockingObjects.html) | Type of objects that will block graphic raycasts. |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| CanvasScalerReferencePixelsPerUnit | float | If a sprite has 'Pixels Per Unit' setting, one pixel in the sprite will cover one unit in the UI. |
| CanvasScalerScaleFactor | float | Scales all children within the canvas by this factor. |
| DefaultSpriteDPI | float | The pixels per inch to use for sprites that have a 'Pixels Per Unit' setting that matches the 'Reference Pixels Per Unit' setting. |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| DynamicPixelsPerUnit | float | The amount of pixels per unit to use for dynamically created bitmaps in the UI, such as Text. |
| EnableScriptEvents | bool | Boolean indicating if unity script events (Update, LateUpdate, Awake, etc) should be relayed to the view code-behind through the corresponding methods that can be overriden. |
| FallbackScreenDPI | float | The DPI to assume if the screen DPI is not known. |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) | GameObject in the hierarchy that corresponds to the view. |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool | Boolean indicating if the view should be ignored. Ignored objects don't run any load logic and don't respond to property changed events. |
| IgnoreReversedGraphics | bool | Boolean indicating if graphics facing away from the raycaster should be ignored. |
| IsActive | bool | Boolean indicating if the view is active. Deactivated views deactivates corresponding game object, components, renderers and scripts. |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| LoadMode | [LoadMode](../Types/LoadMode) | Enum flags indicating when and how the view should be loaded by the framework. Can be changed when e.g. the view is to be loaded on-demand. |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| MatchWidthOrHeight | float | Setting to scale the Canvas to match the width or height of the reference resolution, or a combination. |
| NormalizedSortingGridSize | float | The normalized grid size that the canvas will split the renderable area into. |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverridePixelPerfect | bool | Allows for nested canvases to override pixelPerfect settings inherited from parent canvases. |
| OverrideSorting | bool | Override the sorting of canvas. |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| PhysicalUnit | [Unit](http://docs.unity3d.com/ScriptReference/Unit.html) | The physical unit to specify positions and sizes in. |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | The pivot point of the view. |
| PixelPerfect | bool | Force elements in the canvas to be aligned with pixels. Only applies with renderMode is Screen Space. |
| PlaneDistance | float | How far away from the camera is the Canvas generated. |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| ReferencePixelsPerUnit | float | The number of pixels per unit that is considered the default. |
| ReferenceResolution | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | The resolution the UI layout is designed for. |
| RenderCamera | string | ID of the world camera camera used when rendering the canvas. |
| RenderMode | [RenderMode](http://docs.unity3d.com/ScriptReference/RenderMode.html) | Enum indicating if the canvas is in world or overlay mode. |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| ScaleFactor | float | Used to scale the entire canvas, while still making it fit the screen. Only applies with renderMode is Screen Space. |
| ScreenMatchMode | [ScreenMatchMode](http://docs.unity3d.com/ScriptReference/ScreenMatchMode.html) | A mode used to scale the canvas area if the aspect ratio of the current resolution doesn't fit the reference resolution. |
| SortingLayerID | int | Unique ID of the Canvas sorting layer. |
| SortingLayerName | string | Name of the Canvas sorting layer. |
| SortingOrder | int | Canvas order within a sorting layer. |
| TargetDisplay | int | For Overlay mode, display index on which the UI canvas will appear. |
| UiScaleMode | [ScaleMode](http://docs.unity3d.com/ScriptReference/ScaleMode.html) | Determines how UI elements in the Canvas are scaled. |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
| WorldCamera | [Camera](http://docs.unity3d.com/ScriptReference/Camera.html) | Reference to the world camera, is automatically set if RenderCamera is set. |
