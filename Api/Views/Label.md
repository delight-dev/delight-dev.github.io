---
title: Label
parent: Views
grand_parent: API
nav_order: 11
---

# Label

Based on [UIView](UIView)

## Description

View that presents text. Based on TextMeshPro text component.

## Dependency Properties

| Name | Type | Description |
| --- | --- | --- |
| Alignment | [ElementAlignment](../Types/ElementAlignment) | Used to align the view relative to the layout parent region it resides in. |
| Alpha | float | Can be used to adjust the alpha color of this view and all its children. E.g. used for fade in/out animations. Is separate from and different from the background color of the view as it affects the children as well. |
| AutoSize | [AutoSize](../Types/AutoSize) |  |
| AutoSizeTextContainer | bool |  |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| CharacterSpacing | float |  |
| CharacterWidthAdjustment | float |  |
| ColorGradient | VertexGradient |  |
| ColorGradientPreset | TMP_ColorGradient |  |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| EnableAutoSizing | bool |  |
| EnableCulling | bool |  |
| EnableKerning | bool |  |
| EnableScriptEvents | bool |  |
| EnableVertexGradient | bool |  |
| EnableWordWrapping | bool |  |
| ExtraPadding | bool |  |
| FaceColor | [Color32](http://docs.unity3d.com/ScriptReference/Color32.html) |  |
| FirstVisibleCharacter | int |  |
| Font | [TMP_FontAsset](../Types/TMP_FontAsset) |  |
| FontColor | [Color](http://docs.unity3d.com/ScriptReference/Color.html) |  |
| FontMaterial | [Material](http://docs.unity3d.com/ScriptReference/Material.html) |  |
| FontMaterials | [Material[]](http://docs.unity3d.com/ScriptReference/Material[].html) |  |
| FontSharedMaterial | [Material](http://docs.unity3d.com/ScriptReference/Material.html) |  |
| FontSharedMaterials | [Material[]](http://docs.unity3d.com/ScriptReference/Material[].html) |  |
| FontSize | float |  |
| FontSizeMax | float |  |
| FontSizeMin | float |  |
| FontStyle | FontStyles |  |
| FontWeight | FontWeight |  |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) |  |
| GeometrySortingOrder | VertexSortingOrder |  |
| HavePropertiesChanged | bool |  |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| HorizontalMapping | TextureMappingOptions |  |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool |  |
| IgnoreRectMaskCulling | bool |  |
| IgnoreVisibility | bool |  |
| IsActive | bool |  |
| IsLinkedTextComponent | bool |  |
| IsMaskingGraphic | bool |  |
| IsOrthographic | bool |  |
| IsOverlay | bool |  |
| IsRightToLeftText | bool |  |
| IsUsingLegacyAnimationComponent | bool |  |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| IsVolumetricText | bool |  |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LineSpacing | float |  |
| LineSpacingAdjustment | float |  |
| LinkedTextComponent | TMP_Text |  |
| LoadMode | [LoadMode](../Types/LoadMode) |  |
| MappingUvLineOffset | float |  |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| Maskable | bool |  |
| MaskOffset | [Vector4](http://docs.unity3d.com/ScriptReference/Vector4.html) |  |
| Material | [Material](http://docs.unity3d.com/ScriptReference/Material.html) |  |
| MaxVisibleCharacters | int |  |
| MaxVisibleLines | int |  |
| MaxVisibleWords | int |  |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OnCullStateChanged | [CullStateChangedEvent](http://docs.unity3d.com/ScriptReference/CullStateChangedEvent.html) |  |
| OutlineColor | [Color32](http://docs.unity3d.com/ScriptReference/Color32.html) |  |
| OutlineWidth | float |  |
| OverflowMode | TextOverflowModes |  |
| OverrideColorTags | bool |  |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| PageToDisplay | int |  |
| ParagraphSpacing | float |  |
| ParseCtrlCharacters | bool |  |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | Changes the pivot point of the view. |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| RaycastTarget | bool |  |
| RenderMode | TextRenderFlags |  |
| RichText | bool |  |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| SpriteAsset | [TMP_SpriteAsset](../Types/TMP_SpriteAsset) |  |
| Text | string |  |
| TextAlignment | TextAlignmentOptions |  |
| TextMargin | [Vector4](http://docs.unity3d.com/ScriptReference/Vector4.html) |  |
| TextMeshProUGUIAlpha | float |  |
| TintAllSprites | bool |  |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| UseMaxVisibleDescender | bool |  |
| VertexBufferAutoSizeReduction | bool |  |
| VerticalMapping | TextureMappingOptions |  |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
| WordSpacing | float |  |
| WordWrappingRatios | float |  |
