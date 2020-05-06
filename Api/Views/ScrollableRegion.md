---
title: ScrollableRegion
parent: Views
grand_parent: API
nav_order: 22
---

# ScrollableRegion

Based on [UICanvas](UICanvas)

## Description

Presents scrollable content with optional scrollbars. Behaves similar to the UGUI Panel component.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| AdditionalShaderChannels | [AdditionalCanvasShaderChannels](http://docs.unity3d.com/ScriptReference/AdditionalCanvasShaderChannels.html) |  |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| AutoSizeContentRegion | bool | Boolean indicating if the scrollable content region should be adjusted to the size of its content or not. |
| BlockingObjects | [BlockingObjects](http://docs.unity3d.com/ScriptReference/BlockingObjects.html) |  |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| CanScrollHorizontally | bool | Boolean indicating if the region can be scrolled horizontally. |
| CanScrollVertically | bool | Boolean indicating if the region can be scrolled vertically. |
| CanvasScalerReferencePixelsPerUnit | float |  |
| CanvasScalerScaleFactor | float |  |
| ContentAlignment | [ElementAlignment](../Types/ElementAlignment) | Alignment of the content. |
| DecelerationRate | float | Determines how fast the scroll speed decelerates once the user stops scrolling. |
| DefaultSpriteDPI | float |  |
| DisableInteractionScrollDelta | float | If set any interaction with child views (clicks, etc) are disabled when the specified amount of pixels has been scrolled. Used e.g. to disable items from being selected while scrolling a selectable list of items. |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| DisableMouseWheel | bool | Boolean indicating if the mouse wheel is disabled. |
| DynamicPixelsPerUnit | float |  |
| Elasticity | float | Determines how elastic the viewport is when scrolling outside the bounds of the scrollable content. |
| EnableScriptEvents | bool | Boolean indicating if unity script events (Update, LateUpdate, Awake, etc) should be relayed to the view code-behind through the corresponding methods that can be overriden. |
| FallbackScreenDPI | float |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) | GameObject in the hierarchy that corresponds to the view. |
| HasInertia | bool | Boolean indicating if the should stop immediatelly when the user stops scrolling (when set to False) or if it should decelerate based on DecelerationRate. |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| HorizontalScrollbarVisibility | [ScrollbarVisibilityMode](../Types/ScrollbarVisibilityMode) | Enum indicating the visibility mode of the horizontal scrollbar. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool | Boolean indicating if the view should be ignored. Ignored objects don't run any load logic and don't respond to property changed events. |
| IgnoreReversedGraphics | bool |  |
| IsActive | bool | Boolean indicating if the view is active. Deactivated views deactivates corresponding game object, components, renderers and scripts. |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LoadMode | [LoadMode](../Types/LoadMode) | Enum flags indicating when and how the view should be loaded by the framework. Can be changed when e.g. the view is to be loaded on-demand. |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| MaskContent | bool | Boolean indicating if any content outside the bounds of the viewport should be masked. |
| MatchWidthOrHeight | float |  |
| NormalizedSortingGridSize | float |  |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverridePixelPerfect | bool |  |
| OverrideSorting | bool |  |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| PhysicalUnit | [Unit](http://docs.unity3d.com/ScriptReference/Unit.html) |  |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | The pivot point of the view. |
| PixelPerfect | bool |  |
| PlaneDistance | float |  |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| ReferencePixelsPerUnit | float |  |
| ReferenceResolution | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) |  |
| RenderCamera | string | ID of the world camera camera used when rendering the canvas. |
| RenderMode | [RenderMode](http://docs.unity3d.com/ScriptReference/RenderMode.html) |  |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| ScaleFactor | float |  |
| ScreenMatchMode | [ScreenMatchMode](http://docs.unity3d.com/ScriptReference/ScreenMatchMode.html) |  |
| ScrollBounds | [ScrollBounds](../Types/ScrollBounds) | Enum indicating what type of bounds the scrollable region has (Clamped, Elastic or None). |
| ScrollEnabled | bool | Boolean indicating if scrolling by the user is enabled. |
| ScrollSensitivity | float | Sets the sensitivity of the scrolling using mouse wheel or track pad. |
| SortingLayerID | int |  |
| SortingLayerName | string |  |
| SortingOrder | int |  |
| TargetDisplay | int |  |
| UiScaleMode | [ScaleMode](http://docs.unity3d.com/ScriptReference/ScaleMode.html) |  |
| UnblockDragEventsInChildren | bool | Boolean indicating if draggable child views shouldn't block this scrollable region from being scrolled. |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| VerticalScrollbarVisibility | [ScrollbarVisibilityMode](../Types/ScrollbarVisibilityMode) | Enum indicating the visibility mode of the vertical scrollbar. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
| WorldCamera | [Camera](http://docs.unity3d.com/ScriptReference/Camera.html) |  |
