---
title: ComboBox
parent: Views
grand_parent: API
nav_order: 3
---

# ComboBox

Based on [UIView](UIView)

## Description

Presents a static or dynamic list of items in a drop-down.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| EnableScriptEvents | bool | Boolean indicating if unity script events (Update, LateUpdate, Awake, etc) should be relayed to the view code-behind through the corresponding methods that can be overriden. |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) | GameObject in the hierarchy that corresponds to the view. |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool | Boolean indicating if the view should be ignored. Ignored objects don't run any load logic and don't respond to property changed events. |
| IsActive | bool | Boolean indicating if the view is active. Deactivated views deactivates corresponding game object, components, renderers and scripts. |
| IsDropUp | bool | Boolean indicating if the combo box list should open above instead of below the button. |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
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
| ShowSelectedItem | bool | Boolean indicating if the selected item should be shown in the button. |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
