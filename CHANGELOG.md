# Only HUGE changes are stated here, not the ones auto-generated!

# v`0.736.0.7361342` -> v`0.736.0.7361346` changes
## The structure was changed, adding LOTS of LINES
> It turns out using the type definition of ClassNameTypePairs in conjunction with `keyof` and `index` type functions and mixed with a generic via `&` (as in `T & index<ClassNameTypePairs, keyof<ClassNameTypePairs>>`) over a chained wrapper structure will lead to `Type Error: type if too complex to typecheck...`
> 
> So we came up with a solution. Let you use either all classes ClassNameTypePairs, or all sub-classes of a specific class, with three variations:
> - {ClassName}Child - all direct sub-classes of ClassName
> - {ClassName}Descendant - all sub-classes of ClassName
> - {ClassName}Leaf - all sub-classes at the max depth (those sub-class descendants that have no further sub-classes)
> e.g. you take `GuiBase2d` as your `ClassName`, then you will have the following available:
```luau
export type GuiBaseChild = {
	["GuiBase2d"]: GuiBase2d,
	["GuiBase3d"]: GuiBase3d,
	["Path2D"]: Path2D,
}

export type GuiBaseDescendant = {
	["GuiBase2d"]: GuiBase2d,
	["LayerCollector"]: LayerCollector,
	["ScreenGui"]: ScreenGui,
	["GuiMain"]: GuiMain,
	["BillboardGui"]: BillboardGui,
	["PluginGui"]: PluginGui,
	["QWidgetPluginGui"]: QWidgetPluginGui,
	["DockWidgetPluginGui"]: DockWidgetPluginGui,
	["SurfaceGuiBase"]: SurfaceGuiBase,
	["SurfaceGui"]: SurfaceGui,
	["AdGui"]: AdGui,
	["GuiObject"]: GuiObject,
	["GuiLabel"]: GuiLabel,
	["ImageLabel"]: ImageLabel,
	["TextLabel"]: TextLabel,
	["GuiButton"]: GuiButton,
	["ImageButton"]: ImageButton,
	["TextButton"]: TextButton,
	["TextChannelWindow"]: TextChannelWindow,
	["VideoDisplay"]: VideoDisplay,
	["ViewportFrame"]: ViewportFrame,
	["RelativeGui"]: RelativeGui,
	["CanvasGroup"]: CanvasGroup,
	["TextBox"]: TextBox,
	["ScrollingFrame"]: ScrollingFrame,
	["Frame"]: Frame,
	["InputActionLabel"]: InputActionLabel,
	["VideoFrame"]: VideoFrame,
	["GuiBase3d"]: GuiBase3d,
	["PartAdornment"]: PartAdornment,
	["HandlesBase"]: HandlesBase,
	["Handles"]: Handles,
	["ArcHandles"]: ArcHandles,
	["SurfaceSelection"]: SurfaceSelection,
	["SelectionLasso"]: SelectionLasso,
	["SelectionPartLasso"]: SelectionPartLasso,
	["SelectionPointLasso"]: SelectionPointLasso,
	["PVAdornment"]: PVAdornment,
	["HandleAdornment"]: HandleAdornment,
	["ImageHandleAdornment"]: ImageHandleAdornment,
	["CylinderHandleAdornment"]: CylinderHandleAdornment,
	["WireframeHandleAdornment"]: WireframeHandleAdornment,
	["LineHandleAdornment"]: LineHandleAdornment,
	["PyramidHandleAdornment"]: PyramidHandleAdornment,
	["BoxHandleAdornment"]: BoxHandleAdornment,
	["SphereHandleAdornment"]: SphereHandleAdornment,
	["ConeHandleAdornment"]: ConeHandleAdornment,
	["SelectionSphere"]: SelectionSphere,
	["ParabolaAdornment"]: ParabolaAdornment,
	["InstanceAdornment"]: InstanceAdornment,
	["SelectionBox"]: SelectionBox,
	["FloorWire"]: FloorWire,
	["Path2D"]: Path2D,
}

export type GuiBaseLeaf = {
	["GuiMain"]: GuiMain,
	["BillboardGui"]: BillboardGui,
	["QWidgetPluginGui"]: QWidgetPluginGui,
	["DockWidgetPluginGui"]: DockWidgetPluginGui,
	["SurfaceGui"]: SurfaceGui,
	["AdGui"]: AdGui,
	["ImageLabel"]: ImageLabel,
	["TextLabel"]: TextLabel,
	["ImageButton"]: ImageButton,
	["TextButton"]: TextButton,
	["TextChannelWindow"]: TextChannelWindow,
	["VideoDisplay"]: VideoDisplay,
	["ViewportFrame"]: ViewportFrame,
	["RelativeGui"]: RelativeGui,
	["CanvasGroup"]: CanvasGroup,
	["TextBox"]: TextBox,
	["ScrollingFrame"]: ScrollingFrame,
	["Frame"]: Frame,
	["InputActionLabel"]: InputActionLabel,
	["VideoFrame"]: VideoFrame,
	["Handles"]: Handles,
	["ArcHandles"]: ArcHandles,
	["SurfaceSelection"]: SurfaceSelection,
	["SelectionPartLasso"]: SelectionPartLasso,
	["SelectionPointLasso"]: SelectionPointLasso,
	["ImageHandleAdornment"]: ImageHandleAdornment,
	["CylinderHandleAdornment"]: CylinderHandleAdornment,
	["WireframeHandleAdornment"]: WireframeHandleAdornment,
	["LineHandleAdornment"]: LineHandleAdornment,
	["PyramidHandleAdornment"]: PyramidHandleAdornment,
	["BoxHandleAdornment"]: BoxHandleAdornment,
	["SphereHandleAdornment"]: SphereHandleAdornment,
	["ConeHandleAdornment"]: ConeHandleAdornment,
	["SelectionSphere"]: SelectionSphere,
	["ParabolaAdornment"]: ParabolaAdornment,
	["SelectionBox"]: SelectionBox,
	["FloorWire"]: FloorWire,
	["Path2D"]: Path2D,
}
```

## This is still backwards compatible!
> - `ClassNameTypePairs` still represents ALL CLASS NAMES (in other words descendant classes of the roblox studio hierarchy)
> - (new) `ClassNameTypePairsLeaf` represents ALL CLASS NAMES that have no children, thus each of them is a leaf
> - (new) `ClassNameTypePairsChild` represents ALL CLASS NAMES that are roots (in other words child classes of the roblox studio hierarchy, this is just `Object`, but the auto-generator will add (detect) more if roblox ever makes such update)

## The return value was changed from a `table.freeze({})` to `nil`