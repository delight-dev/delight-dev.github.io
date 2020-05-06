---
title: LayoutRoot
parent: Views
grand_parent: API
nav_order: 13
---

# LayoutRoot

Based on [UICanvas](UICanvas)

## Description

Represents a layout root canvas under which all UI views must reside.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| AdditionalShaderChannels | [AdditionalCanvasShaderChannels](http://docs.unity3d.com/ScriptReference/AdditionalCanvasShaderChannels.html) |  |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| BlockingObjects | [BlockingObjects](http://docs.unity3d.com/ScriptReference/BlockingObjects.html) |  |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| CanvasScalerReferencePixelsPerUnit | float |  |
| CanvasScalerScaleFactor | float |  |
| DefaultSpriteDPI | float |  |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| DynamicPixelsPerUnit | float |  |
| EnableScriptEvents | bool |  |
| FallbackScreenDPI | float |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) |  |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool |  |
| IgnoreReversedGraphics | bool |  |
| IsActive | bool |  |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LoadMode | [LoadMode](../Types/LoadMode) |  |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| MatchWidthOrHeight | float |  |
| NormalizedSortingGridSize | float |  |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverridePixelPerfect | bool |  |
| OverrideSorting | bool |  |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| PhysicalUnit | [Unit](http://docs.unity3d.com/ScriptReference/Unit.html) |  |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | Changes the pivot point of the view. |
| PixelPerfect | bool |  |
| PlaneDistance | float |  |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| ReferencePixelsPerUnit | float |  |
| ReferenceResolution | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) |  |
| RenderCamera | string |  |
| RenderMode | [RenderMode](http://docs.unity3d.com/ScriptReference/RenderMode.html) |  |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| ScaleFactor | float |  |
| ScreenMatchMode | [ScreenMatchMode](http://docs.unity3d.com/ScriptReference/ScreenMatchMode.html) |  |
| SortingLayerID | int |  |
| SortingLayerName | string |  |
| SortingOrder | int |  |
| TargetDisplay | int |  |
| UiScaleMode | [ScaleMode](http://docs.unity3d.com/ScriptReference/ScaleMode.html) |  |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
| WorldCamera | [Camera](http://docs.unity3d.com/ScriptReference/Camera.html) |  |
