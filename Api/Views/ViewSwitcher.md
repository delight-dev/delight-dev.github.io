---
title: ViewSwitcher
parent: Views
grand_parent: API
nav_order: 35
---

# ViewSwitcher

Based on [UIView](UIView)

## Description

Provides logic for switching between mutliple child views and displaying one at a time. By default the views are loaded when they are displayed, behavior can be changed through the SwitchMode property.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| ChildLoadMode | [LoadMode](../Types/LoadMode) | Sets the default LoadMode flag on children. Some flags may be overriden depending on the SwitchMode setting. |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| EnableScriptEvents | bool | Boolean indicating if unity script events (Update, LateUpdate, Awake, etc) should be relayed to the view code-behind through the corresponding methods that can be overriden. |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) | GameObject in the hierarchy that corresponds to the view. |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool | Boolean indicating if the view should be ignored. Ignored objects don't run any load logic and don't respond to property changed events. |
| IsActive | bool | Boolean indicating if the view is active. Deactivated views deactivates corresponding game object, components, renderers and scripts. |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LoadMode | [LoadMode](../Types/LoadMode) | Enum flags indicating when and how the view should be loaded by the framework. Can be changed when e.g. the view is to be loaded on-demand. |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | The pivot point of the view. |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| ShowFirstByDefault | bool | Boolean indicating if the first view in the view switcher should be displayed initially by default. |
| StartView | string | Sets the ID of the view that should be displayed initially. |
| SwitchMode | [SwitchMode](../Types/SwitchMode) | Enum indicating view switch mode, e.g. if views should be loaded on-demand or be pre-loaded. |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
