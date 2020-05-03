---
title: TabPanel
parent: Views
grand_parent: API
nav_order: 28
---

# TabPanel

Based on [Collection](Collection)

## Description

Arranges content in a series of tabs that can be switched between. Tabs can be oriented horizontallt/vertically and aligned topleft/bottom/etc. Tabs and headers can be static or generated dynamically.

{% capture TabPanelExamples %}{% include Examples/Views/TabPanelExamples.md %}{% endcapture %}
{{ TabPanelExamples | markdownify }}

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) |  |
| Alpha | float |  |
| BackgroundAlphaHitTestMinimumThreshold | float |  |
| BackgroundColor | [Color](http://docs.unity3d.com/ScriptReference/Color.html) |  |
| BackgroundFillAmount | float |  |
| BackgroundFillCenter | bool |  |
| BackgroundFillClockwise | bool |  |
| BackgroundFillMethod | [FillMethod](http://docs.unity3d.com/ScriptReference/FillMethod.html) |  |
| BackgroundFillOrigin | int |  |
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
| BubbleNotifyChildLayoutChanged | bool |  |
| DisableLayoutUpdate | bool |  |
| EnableScriptEvents | bool |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) |  |
| Height | [ElementSize](../Types/ElementSize) |  |
| IgnoreFlip | bool |  |
| IgnoreObject | bool |  |
| IsActive | bool |  |
| IsStatic | bool |  |
| IsVisible | bool |  |
| Items | [BindableCollection](../Types/BindableCollection) |  |
| LayoutRoot | [LayoutRoot](LayoutRoot) |  |
| LoadMode | [LoadMode](../Types/LoadMode) |  |
| Margin | [ElementMargin](../Types/ElementMargin) |  |
| Offset | [ElementMargin](../Types/ElementMargin) |  |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) |  |
| OverrideHeight | [ElementSize](../Types/ElementSize) |  |
| OverrideWidth | [ElementSize](../Types/ElementSize) |  |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) |  |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) |  |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) |  |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) |  |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) |  |
| SelectedTabIndex | int |  |
| TabHeaderHeight | [ElementSize](../Types/ElementSize) |  |
| TabHeaderWidth | [ElementSize](../Types/ElementSize) |  |
| TabSwitchMode | [SwitchMode](../Types/SwitchMode) |  |
| UseFastShader | bool |  |
| Width | [ElementSize](../Types/ElementSize) |  |
