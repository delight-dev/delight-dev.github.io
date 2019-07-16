---
title: Button
parent: Views
grand_parent: API
nav_order: 1
---

# Button

Based on [UIImageView](UIImageView)

## Description

The button view is a clickable region with text. Has the additional states: Highlighted, Pressed and Disabled. The button can be set to toggle through IsToggleButton and to adjust its size to its text through the AutoSize field.

{% capture ButtonExamples %}{% include Examples/Views/ButtonExamples.md %}{% endcapture %}
{{ ButtonExamples | markdownify }}

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) |  |
| Alpha | float |  |
| AutoSize | [AutoSize](../Types/AutoSize) |  |
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
| BackgroundPreserveAspect | bool |  |
| BackgroundRaycastTarget | bool |  |
| BackgroundSprite | [Sprite](http://docs.unity3d.com/ScriptReference/Sprite.html) |  |
| BackgroundType | [Type](http://docs.unity3d.com/ScriptReference/Type.html) |  |
| BackgroundUseSpriteMesh | bool |  |
| BubbleNotifyChildLayoutChanged | bool |  |
| CanToggleOff | bool |  |
| CanToggleOn | bool |  |
| DefaultWidth | [ElementSize](../Types/ElementSize) |  |
| DisableLayoutUpdate | bool |  |
| EnableScriptEvents | bool |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) |  |
| Height | [ElementSize](../Types/ElementSize) |  |
| IgnoreFlip | bool |  |
| IgnoreObject | bool |  |
| IsActive | bool |  |
| IsBackButton | bool |  |
| IsCloseButton | bool |  |
| IsDisabled | bool |  |
| IsMouseOver | bool |  |
| IsPressed | bool |  |
| IsToggleButton | bool |  |
| IsVisible | bool |  |
| LayoutRoot | [LayoutRoot](LayoutRoot) |  |
| LoadMode | [LoadMode](../Types/LoadMode) |  |
| Margin | [ElementMargin](../Types/ElementMargin) |  |
| Offset | [ElementMargin](../Types/ElementMargin) |  |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) |  |
| OverrideHeight | [ElementSize](../Types/ElementSize) |  |
| OverrideWidth | [ElementSize](../Types/ElementSize) |  |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) |  |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) |  |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) |  |
| TextOffset | [ElementMargin](../Types/ElementMargin) |  |
| TextPadding | [ElementMargin](../Types/ElementMargin) |  |
| ToggleValue | bool |  |
| UseFastShader | bool |  |
| Width | [ElementSize](../Types/ElementSize) |  |
