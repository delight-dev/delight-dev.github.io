---
title: Image
parent: Views
grand_parent: API
nav_order: 9
---

# Image

Based on [UIView](UIView)

## Description

View that displays an image sprite. Based on the UGUI ImageComponent. Adjusts its size and image type (spliced, etc) to the native sprite if not explicitly set.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| AlphaHitTestMinimumThreshold | float |  |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| Color | [Color](http://docs.unity3d.com/ScriptReference/Color.html) |  |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| EnableScriptEvents | bool |  |
| FillAmount | float |  |
| FillCenter | bool |  |
| FillClockwise | bool |  |
| FillMethod | [FillMethod](http://docs.unity3d.com/ScriptReference/FillMethod.html) |  |
| FillOrigin | int |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) |  |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool |  |
| IsActive | bool |  |
| IsMaskingGraphic | bool |  |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LoadMode | [LoadMode](../Types/LoadMode) |  |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| Maskable | bool |  |
| Material | [Material](http://docs.unity3d.com/ScriptReference/Material.html) |  |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OnCullStateChanged | [CullStateChangedEvent](http://docs.unity3d.com/ScriptReference/CullStateChangedEvent.html) |  |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverrideSprite | [Sprite](http://docs.unity3d.com/ScriptReference/Sprite.html) |  |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | Changes the pivot point of the view. |
| PixelsPerUnitMultiplier | float |  |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | TEST123: Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| PreserveAspect | bool |  |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| RaycastTarget | bool |  |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | TEST222: Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| Sprite | [Sprite](http://docs.unity3d.com/ScriptReference/Sprite.html) |  |
| Type | [Type](http://docs.unity3d.com/ScriptReference/Type.html) |  |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| UseSpriteMesh | bool |  |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
