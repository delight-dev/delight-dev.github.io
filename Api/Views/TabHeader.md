---
title: TabHeader
parent: Views
grand_parent: API
nav_order: 27
---

# TabHeader

Based on [Button](Button)

## Description

Base view for tab headers displayed by the TabPanel.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| AutoSize | [AutoSize](../Types/AutoSize) |  |
| BackgroundAlphaHitTestMinimumThreshold | float |  |
| BackgroundColor | [Color](http://docs.unity3d.com/ScriptReference/Color.html) |  |
| BackgroundFillAmount | float |  |
| BackgroundFillCenter | bool |  |
| BackgroundFillClockwise | bool |  |
| BackgroundFillMethod | [FillMethod](http://docs.unity3d.com/ScriptReference/FillMethod.html) |  |
| BackgroundFillOrigin | int |  |
| BackgroundIsMaskingGraphic | bool |  |
| BackgroundMaskable | bool |  |
| BackgroundMaterial | [Material](http://docs.unity3d.com/ScriptReference/Material.html) |  |
| BackgroundOnCullStateChanged | [CullStateChangedEvent](http://docs.unity3d.com/ScriptReference/CullStateChangedEvent.html) |  |
| BackgroundOverrideSprite | [Sprite](http://docs.unity3d.com/ScriptReference/Sprite.html) |  |
| BackgroundPixelsPerUnitMultiplier | float |  |
| BackgroundPreserveAspect | bool |  |
| BackgroundRaycastTarget | bool |  |
| BackgroundSprite | [Sprite](http://docs.unity3d.com/ScriptReference/Sprite.html) |  |
| BackgroundType | [Type](http://docs.unity3d.com/ScriptReference/Type.html) |  |
| BackgroundUseSpriteMesh | bool |  |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| CanToggleOff | bool |  |
| CanToggleOn | bool |  |
| ContentTemplateData | [ContentTemplateData](../Types/ContentTemplateData) |  |
| DefaultWidth | [ElementSize](../Types/ElementSize) |  |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| EnableScriptEvents | bool |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) |  |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool |  |
| IsActive | bool |  |
| IsBackButton | bool |  |
| IsCloseButton | bool |  |
| IsDisabled | bool |  |
| IsMouseOver | bool |  |
| IsPressed | bool |  |
| IsToggleButton | bool |  |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LoadMode | [LoadMode](../Types/LoadMode) |  |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | Changes the pivot point of the view. |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | TEST123: Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | TEST222: Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| TabIndex | int |  |
| TextOffset | [ElementMargin](../Types/ElementMargin) |  |
| TextPadding | [ElementMargin](../Types/ElementMargin) |  |
| ToggleValue | bool |  |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
