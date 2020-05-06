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
| AutoSize | [AutoSize](../Types/AutoSize) | Enum indicating if and how the label should automatically resize itself to the size of the text. |
| AutoSizeTextContainer | bool | Boolean indicating if text container should be resized to text. |
| BubbleNotifyChildLayoutChanged | bool | Boolean indicating if parent always should be notified when the child changes layout. |
| CharacterSpacing | float | Determines the spacing between characters in the text. |
| CharacterWidthAdjustment | float | Percentage the width of characters can be adjusted before text auto-sizing begins to reduce the point size. |
| ColorGradient | VertexGradient | Sets the vertex colors for each of the 4 vertices of the character quads. |
| ColorGradientPreset | TMP_ColorGradient | Set the vertex colors of the 4 vertices of each character quads. |
| DisableLayoutUpdate | bool | Boolean indicating if automatic layout updates for this view should be disabled. When disabled the view doesn't call UpdateLayout() when properties such as Width, Height, etc. changes. |
| EnableAutoSizing | bool | Enable text auto-sizing. |
| EnableCulling | bool | Sets the culling on the shaders. Note changing this value will result in an instance of the material. |
| EnableKerning | bool | Determines if kerning is enabled or disabled. |
| EnableScriptEvents | bool | Boolean indicating if unity script events (Update, LateUpdate, Awake, etc) should be relayed to the view code-behind through the corresponding methods that can be overriden. |
| EnableVertexGradient | bool | Determines if Vertex Color Gradient should be used. |
| EnableWordWrapping | bool | Controls whether or not word wrapping is applied. When disabled, the text will be displayed on a single line. |
| ExtraPadding | bool | Adds extra padding around each character. This may be necessary when the displayed text is very small to prevent clipping. |
| FaceColor | [Color32](http://docs.unity3d.com/ScriptReference/Color32.html) | Sets the color of the _FaceColor property of the assigned material. Changing face color will result in an instance of the material. |
| FirstVisibleCharacter | int | The first character which should be made visible in conjunction with the Text Overflow Linked mode. |
| Font | [TMP_FontAsset](../Types/TMP_FontAsset) | The font of the label. The value is the name of the font asset file without extension, e.g. "myfont". |
| FontColor | [Color](http://docs.unity3d.com/ScriptReference/Color.html) | Color of the font. |
| FontMaterial | [Material](http://docs.unity3d.com/ScriptReference/Material.html) | Font material to be used. |
| FontMaterials | [Material[]](http://docs.unity3d.com/ScriptReference/Material[].html) | Font materials to be used. |
| FontSharedMaterial | [Material](http://docs.unity3d.com/ScriptReference/Material.html) | Shared font material. |
| FontSharedMaterials | [Material[]](http://docs.unity3d.com/ScriptReference/Material[].html) | Shared font materials. |
| FontSize | float | The point size of the font. |
| FontSizeMax | float | Maximum point size of the font when text auto-sizing is enabled. |
| FontSizeMin | float | Minimum point size of the font when text auto-sizing is enabled. |
| FontStyle | FontStyles | Font style. |
| FontWeight | FontWeight | Control the weight of the font if an alternative font asset is assigned for the given weight in the font asset editor. |
| GameObject | [GameObject](http://docs.unity3d.com/ScriptReference/GameObject.html) | GameObject in the hierarchy that corresponds to the view. |
| GeometrySortingOrder | VertexSortingOrder | Determines the sorting order of the geometry of the text object. |
| HavePropertiesChanged | bool | Property tracking if any of the text properties have changed. Flag is set before the text is regenerated. |
| Height | [ElementSize](../Types/ElementSize) | The height of the view in pixels or percents. |
| HorizontalMapping | TextureMappingOptions | Controls how the face and outline textures will be applied to the text object. |
| IgnoreFlip | bool | Used when doing localization override default behavior of flipping the view Right to Left or Left to Rigth. |
| IgnoreObject | bool | Boolean indicating if the view should be ignored. Ignored objects don't run any load logic and don't respond to property changed events. |
| IgnoreRectMaskCulling | bool | Controls whether or not the text object will be culled when using a 2D Rect Mask. |
| IgnoreVisibility | bool | Forces objects that are not visible to get refreshed. |
| IsActive | bool | Boolean indicating if the view is active. Deactivated views deactivates corresponding game object, components, renderers and scripts. |
| IsLinkedTextComponent | bool | Indicates whether this text component is linked to another. |
| IsMaskingGraphic | bool | Boolean indicating if this is a masking graphic. |
| IsOrthographic | bool | Boolean indicating if this graphic is orthographic. |
| IsOverlay | bool | Sets the RenderQueue along with Ztest to force the text to be drawn last and on top of scene elements. |
| IsRightToLeftText | bool | Boolean indicating if this text flows from right to left. |
| IsUsingLegacyAnimationComponent | bool | Property to handle legacy animation component. |
| IsVisible | bool | Boolean indicating if view is visible or hidden. Invisible views still take up space but aren't interactable and have their alpha set to 0. |
| IsVolumetricText | bool | Determines if the geometry of the characters will be quads or volumetric (cubes). |
| LayoutRoot | [LayoutRoot](LayoutRoot) | Reference to the layout root view that is the main UICanvas that manages layout updates. All UI views resides under a layout root. |
| LineSpacing | float | The amount of additional spacing to add between each lines of text. |
| LineSpacingAdjustment | float | The amount of potential line spacing adjustment before text auto sizing kicks in. |
| LinkedTextComponent | TMP_Text | The linked text component used for flowing the text from one text component to another. |
| LoadMode | [LoadMode](../Types/LoadMode) | Enum flags indicating when and how the view should be loaded by the framework. Can be changed when e.g. the view is to be loaded on-demand. |
| MappingUvLineOffset | float | Controls the horizontal offset of the UV of the texture mapping mode for each line of the text object. |
| Margin | [ElementMargin](../Types/ElementMargin) | Adding margins to a view changes the size of the area in which its content resides, but it does not change the width or height of the view. |
| Maskable | bool | Boolean indicating if graphic is maskable. |
| MaskOffset | [Vector4](http://docs.unity3d.com/ScriptReference/Vector4.html) | Offset of mask graphics. |
| Material | [Material](http://docs.unity3d.com/ScriptReference/Material.html) | Material used by graphic. |
| MaxVisibleCharacters | int | Allows to control how many characters are visible from the input. |
| MaxVisibleLines | int | Allows control over how many lines of text are displayed. |
| MaxVisibleWords | int | Allows to control how many words are visible from the input. |
| Offset | [ElementMargin](../Types/ElementMargin) | Determines the offset of the view. |
| OffsetFromParent | [ElementMargin](../Types/ElementMargin) | Offset set by a parent view. Used by views like Group to arrange children without changing their own Offset values. |
| OnCullStateChanged | [CullStateChangedEvent](http://docs.unity3d.com/ScriptReference/CullStateChangedEvent.html) | Called when cull state changes. |
| OutlineColor | [Color32](http://docs.unity3d.com/ScriptReference/Color32.html) | Sets the _OutlineColor property of the assigned material. Changing outline color will result in an instance of the material. |
| OutlineWidth | float | Sets the thickness of the outline of the font. Setting this value will result in an instance of the material. |
| OverflowMode | TextOverflowModes | Controls the text overflow mode. |
| OverrideColorTags | bool | This overrides the color tags forcing the vertex colors to be the default font color. |
| OverrideHeight | [ElementSize](../Types/ElementSize) | Overrides regular Height value. Used to e.g. automatically size items without changing the default Height value set. |
| OverrideWidth | [ElementSize](../Types/ElementSize) | Overrides regular Width value. Used to e.g. automatically size items without changing the default Width value set. |
| PageToDisplay | int | Controls which page of text is shown. |
| ParagraphSpacing | float | The amount of additional spacing to add between each lines of text. |
| ParseCtrlCharacters | bool | Enables or Disables parsing of CTRL characters in input text. |
| Pivot | [Vector2](http://docs.unity3d.com/ScriptReference/Vector2.html) | The pivot point of the view. |
| Position | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Directly sets the local position of the view relative to parent. Position otherwise set using the Alignment and Offset properties. |
| RaycastBlockMode | [RaycastBlockMode](../Types/RaycastBlockMode) | Enum indicating if raycasts should be blocked. |
| RaycastTarget | bool | Boolean indicating if the graphic should be considered a target for raycasting. |
| RenderMode | TextRenderFlags | Determines if the Mesh will be rendered. |
| RichText | bool | Enables or disables rich text tags. |
| Rotation | [Quaternion](http://docs.unity3d.com/ScriptReference/Quaternion.html) | Rotation of the view. |
| Scale | [Vector3](http://docs.unity3d.com/ScriptReference/Vector3.html) | Scale of the view. |
| SpriteAsset | [TMP_SpriteAsset](../Types/TMP_SpriteAsset) | Default Sprite Asset used by the text object. |
| Text | string | A string containing the text to be displayed. |
| TextAlignment | TextAlignmentOptions | Determines the alignment of the text. |
| TextMargin | [Vector4](http://docs.unity3d.com/ScriptReference/Vector4.html) | Determines the margin of the text. |
| TextMeshProUGUIAlpha | float | Alpha value of the text. |
| TintAllSprites | bool | Determines whether or not the sprite color is multiplies by the vertex color of the text. |
| UseFastShader | bool | Boolean indicating if the default UI shader should be replaced by a simpler and faster one. The faster shader does not support masking and clipping. |
| UseMaxVisibleDescender | bool | Determines if the text's vertical alignment will be adjusted based on visible descender of the text. |
| VertexBufferAutoSizeReduction | bool | Determines if the data structures allocated to contain the geometry of the text object will be reduced in size if the number of characters required to display the text is reduced by more than 256 characters. |
| VerticalMapping | TextureMappingOptions | Controls how the face and outline textures will be applied to the text object. |
| Width | [ElementSize](../Types/ElementSize) | The width of the view in pixels or percents. |
| WordSpacing | float | The amount of additional spacing between words. |
| WordWrappingRatios | float | Controls the blending between using character and word spacing to fill-in the space for justified text. |
