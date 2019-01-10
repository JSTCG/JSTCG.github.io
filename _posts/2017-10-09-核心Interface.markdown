---
layout: post
title: 核心Interface
date: 2017-10-09 22:12:28.000000000 +08:00
tags: MXS
---
**MAXScript Language Reference > 3ds Max Objects > Interfaces >**
- **Core Interfaces** ：
>利用getCoreInterfaces()、showInterface

```swift
#(<Interface:ExchangeStorePackageManager>, <Interface:tmGizmos>, <Interface:qat>, <Interface:RingArray>, <Interface:ViewPanelManager>, <Interface:WorkspaceManager>, <Interface:ChannelInfo>, <Interface:SkinUtils>, <Interface:EPolyManipGrip>, <Interface:Grip>, <Interface:MouseConfigManager>, <Interface:DaylightSimulationUIOps>, <Interface:PseudoColorManager>, <Interface:rollup>, <Interface:FlightStudioExport>, <Interface:MxsUnitResults>, <Interface:EditRenderRegion>, <Interface:MeshInspector>, <Interface:BitmapLayerManager>, <Interface:PhysXPanelInterface>, ...)
Interface: ExchangeStorePackageManager
 Properties:
 Methods:
  <integer>GetNativePlugInCount()
  <filename>GetNativePlugInFullPath <index>index
  <integer>GetManagedAssemblyCount()
  <filename>GetManagedAssemblyFullPath <index>index
  <integer>GetUISchemeCount()
  <filename>GetUISchemeFullPath <index>index
  <integer>GetDefaultSettingCount()
  <filename>GetDefaultSettingFullPath <index>index
  <integer>GetMaxscriptsCount()
  <filename>GetMaxscriptsFullPath <index>index
  <integer>GetMacroscriptsCount()
  <filename>GetMacroScriptsFullPath <index>index
  <integer>GetPostStartUpScriptsCount()
  <filename>GetPostStartUpScriptFullPath <index>index
  <integer>GetMetaSLShaderPathCount()
  <filename>GetMetaSLShaderFullPath <index>index
  <integer>GetMiFileCount()
  <filename>GetMiFileFullPath <index>index
  <integer>GetMentalRayShaderCount()
  <filename>GetMentalRayShaderFullPath <index>index
  <integer>GetLightIconPathsCount()
  <filename>GetLightIconPathFullPath <index>index
  <integer>GetDarkIconPathsCount()
  <filename>GetDarkIconPathFullPath <index>index
 Actions:

Interface: tmGizmos
 Properties:
  .useGizmo : boolean : Read|Write
  .size : integer : Read|Write
  .useLabels : boolean : Read|Write
  .planeOpacity : float : Read|Write
  .useCenterBox : boolean : Read|Write
  .usePlanes : boolean : Read|Write
  .movePlaneHandleSize : float : Read|Write
  .movePlaneHandleOffset : float : Read|Write
  .centerBoxType : enum : Read|Write
     centerBoxType enums: {#screen|#activeGrid}
  .freeRotate : boolean : Read|Write
  .screenHandle : boolean : Read|Write
  .uniformPlaneScaling : boolean : Read|Write
  .uniformScaleHandleSize : float : Read|Write
  .scalePlaneHandleSize : float : Read|Write
  .rotationMode : integer : Read|Write
  .showMiniTripod : boolean : Read|Write
  .showPieSlice : boolean : Read|Write
  .showAngleData : boolean : Read|Write
  .rotationPlanarThreshold : float : Read|Write
  .dragX : float : Read|Write
  .dragY : float : Read|Write
  .vecX : float : Read|Write
  .vecY : float : Read|Write
  .ShowMultipleTransformGizmos : boolean : Read|Write
  .moveGizmoRelativeSize : float : Read|Write
  .rotateGizmoRelativeSize : float : Read|Write
  .scaleGizmoRelativeSize : float : Read|Write
  .intersectMode : boolean : Read|Write
  .perpsectiveSensitivity : float : Read|Write
  .rotationIncrement : float : Read|Write
  .arcRotateSnapAngle : float : Read|Write
 Methods:
 Actions:

Interface: qat
 Properties:
 Methods:
  <integer>add <string>group <string>action
  <void>swap <integer>index1 <integer>index2
  <void>delete <integer>index
 Actions:

Interface: RingArray
 Properties:
 Methods:
  <Interface>Create posOrigin:<&point3> numNodes:<integer> amplitude:<float> radius:<float> cycles:<float> phase:<float>
     posOrigin default value: [0,0,0]
     posOrigin is In parameter
     numNodes default value: 4
     numNodes Validated by Range: 1 to 200
     amplitude default value: 20.0
     amplitude Validated by Range: 0 to 1140457472
     radius default value: 100.0
     radius Validated by Range: 0 to 1140457472
     cycles default value: 3.0
     cycles Validated by Range: 0 to 1092616192
     phase default value: 1.0
     phase Validated by Range: -998637568 to 1148846080
 Actions:

Interface: ViewPanelManager
 Properties:
 Methods:
  <index>CreateViewPanel <string>tabName <enum>layout <bool>isActive
     layout enums: {#layout_1|#layout_2v|#layout_2h|#layout_2ht|#layout_2hb|#layout_3vl|#layout_3vr|#layout_3ht|#layout_3hb|#layout_4|#layout_4vl|#layout_4vr|#layout_4ht|#layout_4hb}
  <bool>DestroyViewPanel <index>Index
  <bool>SetActiveViewPanel <index>Index
  <integer>GetViewPanelCount()
  <index>GetActiveViewPanelIndex()
  <bool>CanCreateMoreViewPanels()
  <string>GetViewPanelName <index>Index
  <bool>SetViewPanelName <index>Index <string>newPanelName
  <value>GetActiveViewPanelDib()
  <bool>IsViewPanelLocked <index>Index
  <bool>SetExtendedView <integer>viewIndex <enum>extendedViewType
     extendedViewType enums: {#ev_type_tree|#ev_type_schematic|#ev_type_sceneexplore}
  <bool>SetSplitterBarPos <integer>splitterBarID <float>pos
  <index>CreateViewPanelFromPreset <string>presetName <bool>isActive
  <integer>GetPresetCount()
  <string>GetPresetName <index>presetIndex
  <index>GetPresetID <string>presetName
  <bool>CreatePresetFromActiveViewPanel <string>presetName
  <bool>CreatePresetFromViewPanel <index>panelIndex <string>presetName
  <bool>DeletePreset <string>presetName
  <bool>RenameViewPanelPreset <string>presetName <string>newName
  <bool>DeleteAllViewPanelPresets()
  <bool>DoesViewPanelPresetExist <string>presetName
  <integer>GetViewPanelPresetLayout <integer>presetIndex
 Actions:

Interface: WorkspaceManager
 Properties:
 Methods:
  <bool>CreateNewWorkspace <string>identifier <string>friendlyName
  <string>GetWorkspaceIdentifier <index>index
  <string>GetWorkspaceName <index>index
  <string>GetWorkspaceNameWithIdentifier <string>identifier
  <integer>GetWorkspaceCount()
  <string>GetCurrentWorkspaceIdentifier()
  <bool>SetCurrentWorkspaceByIdentifier <string>identifier
  <bool>DeleteWorkspace <string>identifier
  <TSTR by value>GetWriteDirectory()
  <bool>SetWorkspaceName <index>index <string>name
  <bool>SetWorkspaceNameWithIdentifier <string>identifier <string>name
  <bool>ResetToDefaults <string>identifier
  <bool>GetRunScript <string>identifier
  <void>ToggleRunScript <string>identifier
  <filename>GetEntryScript <string>identifier
  <bool>SetEntryScript <string>identifier <filename>script
  <filename>GetExitScript <string>identifier
  <bool>SetExitScript <string>identifier <filename>script
  <integer>GetAllSubsystemsCount()
  <string>GetSubsystemName <index>index
  <bool>IsSubsystemSaving <string>identifier <string>subSystemIdentifier
  <bool>ToggleSubsystemSaving <string>identifier <string>subSystemIdentifier
  <bool>IsSystemWorkspace <string>identifier
 Actions:

Interface: ChannelInfo
 Properties:
  .subComp : boolean : Read|Write
  .lock : boolean : Read|Write
 Methods:
  <void>dialog()
     dialog - no automatic redraw after invoked
  <void>closeDialog()
     closeDialog - no automatic redraw after invoked
  <boolean>isChecked()
     isChecked - no automatic redraw after invoked
  <void>CopyChannel <node>node <integer>channelType <integer>channel
     CopyChannel - no automatic redraw after invoked
  <void>CopySubChannel <node>node <integer>channelType <integer>channel <integer>subchannel
     CopySubChannel - no automatic redraw after invoked
  <void>PasteChannel <node>node <integer>channelType <integer>channel
  <void>PasteSubChannel <node>node <integer>channelType <integer>channel <integer>subchannel
  <void>AddChannel <node>node
  <void>ClearChannel <node>node <integer>channel
  <void>NameChannel <node>node <integer>channelType <integer>channel <string>name
  <void>NameSubChannel <node>node <integer>channelType <integer>channel <integer>subchannel <string>name
  <void>update()
     update - no automatic redraw after invoked
 Actions:

Interface: SkinUtils
 Properties:
 Methods:
  <void>ExtractSkinData <node>node
  <void>ImportSkinData <node>targetNode <node>sourceNode
  <matrix3 by value>GetBoneBindTM <node>skinNode <node>boneNode
  <void>SetBoneBindTM <node>skinNode <node>boneNode <matrix3 by value>tm
  <matrix3 by value>GetMeshBindTM <node>skinNode
  <void>SetMeshBindTM <node>skinNode <matrix3 by value>tm
  <matrix3 by value>GetBoneStretchTM <node>skinNode <node>boneNode
  <void>SetBoneStretchTM <node>skinNode <node>boneNode <matrix3 by value>tm
  <void>GrowSelection <node>skinNode
  <void>ShrinkSelection <node>skinNode
  <void>LoopSelection <node>skinNode
  <void>RingSelection <node>skinNode
  <void>ImportSkinDataNoDialog <boolean>matchByName <boolean>removeTargetPrefix <boolean>removeTargetSuffix <boolean>removeSourcePrefix <boolean>removeSourceSuffix <float>threshold <integer>interpolationType
 Actions:

Interface: EPolyManipGrip
 Properties:
 Methods:
  <void>SetManipulateGrip <bool>on <enum>gripItem
     gripItem enums: {#SSFalloff|#SSBubble|#SSPinch|#SetFlow|#LoopShift|#RingShift|#EdgeCrease|#EdgeWeight|#VertexWeight}
  <bool>GetManipulateGrip <enum>gripItem
     gripItem enums: {#SSFalloff|#SSBubble|#SSPinch|#SetFlow|#LoopShift|#RingShift|#EdgeCrease|#EdgeWeight|#VertexWeight}
 Actions:

Interface: Grip
 Properties:
  .Show : bool : Read|Write
  .CenterOnSelected : bool : Read|Write
  .SelectedXOffset : integer : Read|Write
  .SelectedYOffset : integer : Read|Write
  .CenterYPos : float : Read|Write
  .CenterXPos : float : Read|Write
  .Transparency : float : Read|Write
  .HoverTransparency : float : Read|Write
  .WidgetSpacing : float : Read|Write
 Methods:
 Actions:

Interface: MouseConfigManager
 Properties:
  .ArcRotateLocked : bool : Read|Write
  .MayaSelectionMode : bool : Read|Write
  .AutoFocusViewportOnKeyPress : bool : Read|Write
  .ZoomWheelIncrement : float : Read|Write
  .MiddleMouseStrokeMode : bool : Read|Write
  .ZoomAboutMousePointOrthographic : bool : Read|Write
  .ZoomAboutMousePointPerspective : bool : Read|Write
  .RightClickMenuOverSelectedOnly : bool : Read|Write
  .ZoomInDirection : enum : Read|Write
     ZoomInDirection enums: {#North|#NorthEast|#East|#SouthEast|#South|#SouthWest|#West|#NorthWest}
  .UserMode : enum : Read|Write
     UserMode enums: {#Max|#Maya|#Customized}
 Methods:
  <void>GetZoomShortcut <&enum>key <&enum>button
     key enums: {#Null|#Shift|#Ctrl|#Alt|#ShiftCtrl|#CtrlAlt|#AltShift|#ShiftCtrlAlt}
     key is Out parameter
     button enums: {#NullButton|#LeftButton|#MiddleButton|#RightButton}
     button is Out parameter
  <void>SetZoomShortcut <enum>key <enum>button
     key enums: {#Null|#Shift|#Ctrl|#Alt|#ShiftCtrl|#CtrlAlt|#AltShift|#ShiftCtrlAlt}
     button enums: {#NullButton|#LeftButton|#MiddleButton|#RightButton}
  <void>GetPanShortcut <&enum>key <&enum>button
     key enums: {#Null|#Shift|#Ctrl|#Alt|#ShiftCtrl|#CtrlAlt|#AltShift|#ShiftCtrlAlt}
     key is Out parameter
     button enums: {#NullButton|#LeftButton|#MiddleButton|#RightButton}
     button is Out parameter
  <void>SetPanShortcut <enum>key <enum>button
     key enums: {#Null|#Shift|#Ctrl|#Alt|#ShiftCtrl|#CtrlAlt|#AltShift|#ShiftCtrlAlt}
     button enums: {#NullButton|#LeftButton|#MiddleButton|#RightButton}
  <void>GetRotateShortcut <&enum>key <&enum>button
     key enums: {#Null|#Shift|#Ctrl|#Alt|#ShiftCtrl|#CtrlAlt|#AltShift|#ShiftCtrlAlt}
     key is Out parameter
     button enums: {#NullButton|#LeftButton|#MiddleButton|#RightButton}
     button is Out parameter
  <void>SetRotateShortcut <enum>key <enum>button
     key enums: {#Null|#Shift|#Ctrl|#Alt|#ShiftCtrl|#CtrlAlt|#AltShift|#ShiftCtrlAlt}
     button enums: {#NullButton|#LeftButton|#MiddleButton|#RightButton}
 Actions:

Interface: DaylightSimulationUIOps
 Properties:
  .Visible : bool : Read|Write
 Methods:
  <void>Refresh()
     Refresh - no automatic redraw after invoked
 Actions:

Interface: PseudoColorManager
 Properties:
  .rangeStart : float : Read|Write
  .rangeEnd : float : Read|Write
  .scaleType : enum : Read|Write
     scaleType enums: {#linear|#logarithmic}
 Methods:
 Actions:

Interface: rollup
 Properties:
 Methods:
 Actions:

Interface: FlightStudioExport
 Properties:
 Methods:
  <float>GetMatrixEpsilon()
  <void>SetMatrixEpsilon <float>MatrixEpsilon
  <boolean>GetAutoGroup()
  <void>SetAutoGroup <boolean>AutoGroup
  <boolean>GetAutoObject()
  <void>SetAutoObject <boolean>AutoObject
  <boolean>GetCopyTextures()
  <void>SetCopyTextures <boolean>CopyTextures
 Actions:

Interface: MxsUnitResults
 Properties:
 Methods:
  <integer>GetAssertFailCount()
  <integer>GetExceptionCount()
  <integer>GetMessageCount()
  <TSTR>GetAssertFailure <index>index
  <TSTR>GetExceptionFailure <index>index
  <TSTR>GetMessage <index>index
  <TSTR>GetUserData()
  <void>Clear()
 Actions:

Interface: EditRenderRegion
 Properties:
  .IsEditing : boolean : Read|Write
  .IsEditable : boolean : Read|Write
 Methods:
  <void>EditRegion()
  <void>UpdateRegion()
 Actions:

Interface: MeshInspector
 Properties:
  .Enable : bool : Read|Write
  .RepairMesh : bool : Read|Write
  .ShowDialog : bool : Read|Write
 Methods:
 Actions:

Interface: BitmapLayerManager
 Properties:
 Methods:
  <integer>getLayerCount <filename>filename
  <string>getLayerName <filename>filename <integer>index
  <string>LoadLayer <filename>filename <integer>index <boolean>fullframe
 Actions:

Interface: PhysXPanelInterface
 Properties:
  .instance : maxObject : Read
 Methods:
 Actions:

Interface: renderMessageManager
 Properties:
  .OpenOnError : bool : Read|Write
  .ShowInfoMessage : bool : Read|Write
  .ShowProgressMessage : bool : Read|Write
  .LogDebugMessage : bool : Read|Write
  .LogFilename : string : Read|Write
  .LogFileON : bool : Read|Write
  .LogFileAppend : bool : Read|Write
 Methods:
  <bool>OpenWindow()
  <void>HideWindow()
  <void>ClearWindow()
 Actions:

Interface: iDisplayGamma
 Properties:
  .colorCorrectionMode : enum : Read|Write
     colorCorrectionMode enums: {#LUT|#gamma|#none}
  .LUTFileName : filename : Read|Write
  .gamma : float : Read|Write
  .colorCorrectionPrefMode : enum : Read|Write
     colorCorrectionPrefMode enums: {#LUT|#gamma|#none}
  .affectColorPickers : boolean : Read|Write
  .affectMEdit : boolean : Read|Write
 Methods:
 Actions:

Interface: FlowRaytraceInterface
 Properties:
 Methods:
 Actions:

Interface: RevitDBManager
 Properties:
 Methods:
 Actions:

Interface: colorMan
 Properties:
 Methods:
  <enum>getColorSchemeType()
     getColorSchemeType enums: {#customColor|#standardWindows|#windowsTheme
  <enum>setColorSchemeType <enum>type
     setColorSchemeType enums: {#customColor|#standardWindows|#windowsTheme
     type enums: {#customColor|#standardWindows|#windowsTheme}
  <boolean>registerColor <string>color <string>name <string>category <point3 by value>defaultColor
  <boolean>loadColorFile <filename>file
  <boolean>saveColorFile <filename>file
  <filename>getColorFile()
  <boolean>setColor <string>color <point3 by value>colorValue
  <point3 by value>getColor <string>color
  <string>getName <string>color
  <string>getCategory <string>color
  <float>getIconColorScale <enum>type <enum>which
     type enums: {#disabledIcon|#enabledIcon}
     which enums: {#saturationScale|#valueScale|#alphaScale}
  <void>setIconColorScale <enum>type <enum>which <float>value
     type enums: {#disabledIcon|#enabledIcon}
     which enums: {#saturationScale|#valueScale|#alphaScale}
  <boolean>getIconColorInvert <enum>type
     type enums: {#disabledIcon|#enabledIcon}
  <void>setIconColorInvert <enum>type <boolean>value
     type enums: {#disabledIcon|#enabledIcon}
  <filename>getFileName()
  <point3 by value>getDefaultColor <string>color
  <void>repaintUI <enum>type
     type enums: {#repaintAll|#repaintTrackBar|#repaintTimeBar}
  <boolean>setIconFolder <filename>folder
  <void>reInitIcons()
  <filename>getIconFolder()
  <boolean>resolveIconFolder <filename>filename <&TSTR>path
     path is Out parameter
 Actions:

Interface: MXSDebugger
 Properties:
  .isDialogOpen : boolean : Read
  .hWnd : HWND : Read
  .commandTimeOutPeriod : DWORD : Read|Write
  .breakTimeoutPeriod : DWORD : Read|Write
  .gcTimeoutPeriod : DWORD : Read|Write
  .breakCyclePeriod : DWORD : Read|Write
  .allowBreakOnThrow : boolean : Read|Write
  .breakOnError : boolean : Read|Write
  .breakOnException : boolean : Read|Write
  .defaultBreakOnThrow : boolean : Read|Write
  .ignoreCaughtThrows : boolean : Read|Write
  .ignoreCaughtErrors : boolean : Read|Write
  .ignoreCaughtExceptions : boolean : Read|Write
  .enabledInQuietMode : boolean : Read|Write
  .enabledInNetRender : boolean : Read|Write
  .stayOnTop : boolean : Read|Write
  .showGlobalConstants : boolean : Read|Write
  .showFirstFrameOnly : boolean : Read|Write
  .allowUnsafeMethods : boolean : Read|Write
  .clearOutputOnOpen : boolean : Read|Write
 Methods:
  <void>openDialog break:<boolean> message:<string> setFocus:<boolean>
     break default value: false
     message default value: undefined
     setFocus default value: false
  <void>closeDialog()
  <void>writeString <string>message
  <void>writeLine <string>message
 Actions:

Interface: xViewChecker
 Properties:
  .on : bool : Read|Write
  .activeIndex : index : Read|Write
  .seeThrough : bool : Read|Write
  .autoUpdate : bool : Read|Write
  .displayTextUpTop : bool : Read|Write
 Methods:
  <integer>getNumCheckers()
  <TSTR by value>getCheckerName <index>index
  <DWORD>getCheckerID <index>index
  <DWORD>getActiveCheckerID()
  <void>setActiveCheckerID <DWORD>ID
  <bool>doesCheckerHavePropDlg <index>index
  <void>showCheckerPropDlg <index>index
  <void>popupMenuSelect()
  <void>selectResults <time>time
  <void>displayResults <color>color <time>time <node>node <HWND>hwnd <enum>type <&index array>results
     type enums: {#Failed|#Vertices|#Edges|#Faces}
     results is In and Out parameter
  <index>registerChecker <value>checkerFunc <value>isSupportedFunc <enum>type <TSTR>name <value>popupDlgFunc <value>textOverrideFunc <value>displayOverrideFunc
     type enums: {#Failed|#Vertices|#Edges|#Faces}
  <bool>unRegisterChecker <TSTR>name
  <void>runCheck <time>time
  <enum>getCurrentReturnVal()
     getCurrentReturnVal enums: {#Failed|#Vertices|#Edges|#Faces
  <integer>getCurrentOutputCount()
  <TSTR by value>getCurrentString()
 Actions:

Interface: AssetManager
 Properties:
 Methods:
  <TSTR by value>GetAssetId <&TSTR>fileName <enum>assetType
     fileName is In parameter
     assetType enums: {#Other|#Bitmap|#XRef|#Photometric|#Animation|#VideoPost|#BatchRender|#ExternalLink|#RenderOutput|#PreRenderScript|#PostRenderScript|#Sound|#Container}
  <IObject>GetAsset <&TSTR>fileName <enum>assetType autoAcquire:<bool>
     fileName is In parameter
     assetType enums: {#Other|#Bitmap|#XRef|#Photometric|#Animation|#VideoPost|#BatchRender|#ExternalLink|#RenderOutput|#PreRenderScript|#PostRenderScript|#Sound|#Container}
     autoAcquire default value: true
  <IObject>GetAssetByIndex <index>index
  <TSTR by value>GetFileName <&TSTR>assetid
     assetid is In parameter
  <bool>AddReference <&TSTR>assetid
     assetid is In parameter
  <bool>ReleaseReference <&TSTR>assetid
     assetid is In parameter
  <integer>GetNumReference <&TSTR>assetid
     assetid is In parameter
  <INT64>GetNumAssetUsersCreated()
  <INT64>GetNumAssetUsers()
  <INT64>GetNumAssetsCreated()
  <INT64>GetNumAssets()
 Actions:

Interface: DialogMonitorOPS
 Properties:
  .Enabled : bool : Read|Write
  .Interactive : bool : Read|Write
 Methods:
  <bool>RegisterNotification <value>Callback ID:<name>
     RegisterNotification - no automatic redraw after invoked
     ID default value: undefined
  <bool>UnRegisterNotification ID:<name>
     UnRegisterNotification - no automatic redraw after invoked
     ID default value: undefined
  <void>ShowNotification()
     ShowNotification - no automatic redraw after invoked
  <HWND>GetWindowHandle()
     GetWindowHandle - no automatic redraw after invoked
 Actions:

Interface: GhostingManager
 Properties:
  .DisplayGhostInWireframe : bool : Read|Write
  .ShowGhosting : bool : Read|Write
  .GhostType : integer : Read|Write
  .TotalGhostFrames : integer : Read|Write
  .GhostFrameIncrement : integer : Read|Write
  .ShowGhostFrameNumbers : bool : Read|Write
 Methods:
 Actions:

Interface: HelpSystem
 Properties:
  .productHelpLocation : enum : Read|Write
     productHelpLocation enums: {#onlineHelp|#localHelp}
  .localProductHelpPath : string : Read|Write
  .defaultLocalProductHelpPath : string : Read
 Methods:
  <void>ShowProductHelp <integer>helpContextId
  <void>SearchProductHelp <string>searchFor
 Actions:

Interface: ViewportButtonMgr
 Properties:
  .EnableButtons : bool : Read|Write
 Methods:
 Actions:

Interface: browserMgr
 Properties:
 Methods:
  <Interface>newBrowser <string>rootURL <boolean>showDirectory <boolean>showContent <boolean>showToolbar <boolean>showMenu
  <integer>numBrowsers()
  <Interface>getBrowser <integer>index
 Actions:

Interface: NetworkLicenseStatusManager
 Properties:
  .minimumIdleDuration : float : Read|Write|Validated by Range: 120.0 to 10000.0
 Methods:
  <bool>IsBusy()
     IsBusy - no automatic redraw after invoked
  <void>SetBusy()
     SetBusy - no automatic redraw after invoked
  <void>Lock()
     Lock - no automatic redraw after invoked
  <void>Unlock()
     Unlock - no automatic redraw after invoked
  <bool>IsLocked()
     IsLocked - no automatic redraw after invoked
  <bool>IsPaused()
     IsPaused - no automatic redraw after invoked
  <float>GetLastStampDuration()
     GetLastStampDuration - no automatic redraw after invoked
  <float>GetTotalIdleTime()
     GetTotalIdleTime - no automatic redraw after invoked
 Actions:

Interface: particleFlow
 Properties:
 Methods:
  <void>beginEdit()
  <void>endEdit()
  <node>openParticleView()
  <node>scriptRunner()
  <bool>makeUnique <node>action
  <integer>getActionOrder()
  <integer>setActionOrder <integer>orderType
  <integer>getUpdateType()
  <integer>setUpdateType <integer>updateType
  <void>delete <node>particleFlowItem
  <integer>cleanUpParticleFlow <bool>doReport
  <void>resetParticleView()
  <integer>synchronizeLayers <bool>doReport
  <void>repairCacheSystem <bool>doReport
  <void>presetManager()
 Actions:

Interface: DwfExportPreferences
 Properties:
  .logFileName : filename : Read|Write
  .maxTextureSize : integer : Read|Write
  .writeLogFile : boolean : Read|Write
  .showViewer : boolean : Read|Write
  .rescaleTextures : boolean : Read|Write
  .defaultDwfLights : boolean : Read|Write
  .exportProperties : boolean : Read|Write
  .exportMaterials : boolean : Read|Write
  .exportHidden : boolean : Read|Write
  .selectedOnly : boolean : Read|Write
  .groupBy : enum : Read|Write
     groupBy enums: {#ByObject|#ByLayer}
 Methods:
  <void>ResetDefaultPreferences()
  <void>SavePreferences()
  <boolean>LoadPreferences()
 Actions:

Interface: DaylightSimulationUtilities
 Properties:
 Methods:
  <node by value array>FindValidLights()
     FindValidLights - no automatic redraw after invoked
  <node by value array>FindInvalidLights()
     FindInvalidLights - no automatic redraw after invoked
  <node by value array>FindActiveLights()
     FindActiveLights - no automatic redraw after invoked
  <node by value array>FindInactiveLights()
     FindInactiveLights - no automatic redraw after invoked
  <node by value array>FindLightsWithValidType()
     FindLightsWithValidType - no automatic redraw after invoked
  <node by value array>FindLightsWithInvalidType()
     FindLightsWithInvalidType - no automatic redraw after invoked
  <node by value array>FindLightsWithShadowsOn()
     FindLightsWithShadowsOn - no automatic redraw after invoked
  <node by value array>FindLightsWithShadowsOff()
     FindLightsWithShadowsOff - no automatic redraw after invoked
  <node by value array>FindLightsUsingRaytracedShadows()
     FindLightsUsingRaytracedShadows - no automatic redraw after invoked
  <node by value array>FindLightsNotUsingRaytracedShadows()
     FindLightsNotUsingRaytracedShadows - no automatic redraw after invoked
  <node by value array>FindRenderableObjects()
     FindRenderableObjects - no automatic redraw after invoked
  <node by value array>FindInvalidMaterials()
     FindInvalidMaterials - no automatic redraw after invoked
  <boolean>FixInvalidMaterials()
     FixInvalidMaterials - no automatic redraw after invoked
  <node by value array>FindDaylightSystems()
     FindDaylightSystems - no automatic redraw after invoked
  <boolean>LightAnalysisRenderEffectExists()
     LightAnalysisRenderEffectExists - no automatic redraw after invoked
  <boolean>IsLightAnalysisRenderEffectActive()
     IsLightAnalysisRenderEffectActive - no automatic redraw after invoked
  <integer>GetLightAnalysisRenderEffectCount()
     GetLightAnalysisRenderEffectCount - no automatic redraw after invoked
  <boolean>IsValidRenderer()
     IsValidRenderer - no automatic redraw after invoked
  <boolean>IsMentalRaySunDaylightSystem <Interface>daylightSystem
     IsMentalRaySunDaylightSystem - no automatic redraw after invoked
  <boolean>IsMentalRaySkyDaylightSystem <Interface>daylightSystem
     IsMentalRaySkyDaylightSystem - no automatic redraw after invoked
  <boolean>IsShadowCastingDaylightSystem <Interface>daylightSystem
     IsShadowCastingDaylightSystem - no automatic redraw after invoked
  <boolean>IsValidSunMultiplier <Interface>daylightSystem
     IsValidSunMultiplier - no automatic redraw after invoked
  <boolean>IsValidSkyMultiplier <Interface>daylightSystem
     IsValidSkyMultiplier - no automatic redraw after invoked
  <boolean>IsSunOn <Interface>daylightSystem
     IsSunOn - no automatic redraw after invoked
  <boolean>IsSkyOn <Interface>daylightSystem
     IsSkyOn - no automatic redraw after invoked
  <void>SetMentalRayAsProductionRenderer()
     SetMentalRayAsProductionRenderer - no automatic redraw after invoked
  <void>OpenIndirectIlluminationRenderDialogPage()
     OpenIndirectIlluminationRenderDialogPage - no automatic redraw after invoked
  <boolean>Is32bitFrameBuffer()
     Is32bitFrameBuffer - no automatic redraw after invoked
  <boolean>IsRenderIterative()
     IsRenderIterative - no automatic redraw after invoked
  <void>SetRenderIterative <boolean>renderIterative
     SetRenderIterative - no automatic redraw after invoked
  <void>ApplyDefaultRenderPreset()
     ApplyDefaultRenderPreset - no automatic redraw after invoked
 Actions:

Interface: CUIMouseConfigManagerImplement
 Properties:
 Methods:
 Actions:

Interface: AutoTangentMan
 Properties:
  .NewControllersAutoTangentAlgorithm : enum : Read|Write
     NewControllersAutoTangentAlgorithm enums: {#unsupported|#legacy|#unified}
 Methods:
  <bool>SupportsAutoTangent <maxObject>anim
  <enum>GetAutoTangentAlgorithm <maxObject>anim
     GetAutoTangentAlgorithm enums: {#unsupported|#legacy|#unified
  <void>SetAutoTangentAlgorithm <enum>algorithm <&maxObject array>anims
     algorithm enums: {#unsupported|#legacy|#unified}
     anims is In and Out parameter
 Actions:

Interface: MaxNetWorkerInterface
 Properties:
 Methods:
 Actions:

Interface: visualMS
 Properties:
 Methods:
  <Interface>createForm()
  <Interface>createFormFromFile <filename>fileName
 Actions:

Interface: IShaderManagerCreator
 Properties:
 Methods:
 Actions:

Interface: RetimerMan
 Properties:
  .numRetimers : index : Read
  .active : bool : Read|Write
  .bakeThreshold : float : Read|Write
 Methods:
  <maxObject>GetGlobalRetimer()
  <maxObject>GetNthRetimer <index>index
  <maxObject>CreateRetimer()
  <void>DeleteRetimer <index>index
  <void>BakeAndDeleteLocalRetimers()
 Actions:

Interface: ContainerPreferences
 Properties:
  .saveAsPreviousAccessType : enum : Read|Write
     saveAsPreviousAccessType enums: {#noAccess|#onlyEditInPlace|#onlyAddNewObjects|#anythingUnlocked}
  .displayStatusOverride : enum : Read|Write
     displayStatusOverride enums: {#always|#never|#perContainer}
  .updateCheck : boolean : Read|Write
  .updateOnLoad : boolean : Read|Write
  .updateOnReload : boolean : Read|Write
 Methods:
 Actions:

Interface: NetworkManager
 Properties:
 Methods:
  <boolean>Send <string>to <string>from <string>subject <string>body <string>server
     Send - no automatic redraw after invoked
 Actions:

Interface: ValueConverter
 Properties:
 Methods:
 Actions:

Interface: LayerManager
 Properties:
  .count : integer : Read
  .current : Interface : Read
 Methods:
  <Interface>getLayer <integer>which
  <Interface>newLayer()
  <Interface>getLayerFromName <string>name
  <Interface>newLayerFromName <string>name
  <void>editLayerByName <string>name
  <boolean>deleteLayerByName <string>name
  <void>closeDialog()
  <boolean>isDialogOpen()
     isDialogOpen - no automatic redraw after invoked
 Actions:

Interface: IRTShadeTreeCompiler
 Properties:
 Methods:
 Actions:

Interface: AnimLayerManager
 Properties:
  .filterActiveOnly : bool : Read|Write
  .justUpToActive : bool : Read|Write
 Methods:
  <void>showAnimLayersManagerToolbar <bool>show
  <integer>enableLayersDlg <&node array>nodes
     nodes is In and Out parameter
  <integer>enableLayers <&node array>nodes pos:<boolean> rot:<boolean> scale:<boolean> ik:<boolean> object:<boolean> customAtt:<boolean> mod:<boolean> mat:<boolean> other:<boolean>
     nodes is In and Out parameter
     pos default value: true
     rot default value: true
     scale default value: true
     ik default value: false
     object default value: false
     customAtt default value: false
     mod default value: false
     mat default value: false
     other default value: false
  <boolean>canEnableLayer <maxObject>anim <maxObject>client <index>subNum
  <boolean>enableLayer <maxObject>anim <maxObject>client <index>subNum
  <index>getLayerCount()
  <index array>getNodesLayers <&node array>nodes
     nodes is In and Out parameter
  <void>setLayerActive <index>listIndex
     listIndex Validated by Validator function
  <void>setLayerActiveNodes <index>listIndex <&node array>nodes
     listIndex Validated by Validator function
     nodes is In and Out parameter
  <index array>getActiveLayersNodes <&node array>nodes
     nodes is In and Out parameter
  <void>getNodesActiveLayer <&node array>nodes
     nodes is In and Out parameter
  <void>addLayer <&TSTR>name <&node array>nodes <bool>useActiveControllerType
     name is In and Out parameter
     nodes is In and Out parameter
  <void>addLayerDlg <&node array>nodes
     nodes is In and Out parameter
  <void>deleteLayer <index>listIndex
     listIndex Validated by Validator function
  <void>deleteLayerNodes <index>listIndex <&node array>nodes
     listIndex Validated by Validator function
     nodes is In and Out parameter
  <void>copyLayerNodes <index>listIndex <&node array>nodes
     listIndex Validated by Validator function
     nodes is In and Out parameter
  <void>pasteLayerNodes <index>listIndex <&node array>nodes
     listIndex Validated by Validator function
     nodes is In and Out parameter
  <TSTR by value>getLayerName <index>listIndex
     listIndex Validated by Validator function
  <void>setLayerName <index>listIndex <TSTR by value>name
     listIndex Validated by Validator function
  <float>getLayerWeight <index>listIndex <time>atTime
     listIndex Validated by Validator function
  <void>setLayerWeight <index>listIndex <time>atTime <float>weight
     listIndex Validated by Validator function
  <control>getLayerWeightControl <index>listIndex
     listIndex Validated by Validator function
  <bool>setLayerWeightControl <index>listIndex <control>control
     listIndex Validated by Validator function
  <bool>getLayerMute <index>listIndex
     listIndex Validated by Validator function
  <void>setLayerMute <index>listIndex <bool>mute
     listIndex Validated by Validator function
  <bool>getLayerLocked <index>listIndex
     listIndex Validated by Validator function
  <void>setLayerLocked <index>listIndex <bool>locked
     listIndex Validated by Validator function
  <bool>getLayerOutputMute <index>listIndex
     listIndex Validated by Validator function
  <void>setLayerOutputMute <index>listIndex <bool>mute
     listIndex Validated by Validator function
  <void>collapseLayerNodes <index>listIndex <&node array>nodes
     listIndex Validated by Validator function
     nodes is In and Out parameter
  <void>disableLayerNodes <&node array>nodes
     nodes is In and Out parameter
  <void>animLayerPropertiesDlg()
  <void>refreshAnimLayerPropertiesDlg()
  <void>SetCollapseControllerType <enum>controllerType
     controllerType enums: {#Bezier|#Linear|#Default}
  <enum>GetCollapseControllerType()
     GetCollapseControllerType enums: {#Bezier|#Linear|#Default
  <void>SetCollapsePerFrame <bool>keyable
  <bool>GetCollapsePerFrame()
  <void>SetCollapsePerFrameActiveRange <bool>activeRange
  <bool>GetCollapsePerFrameActiveRange()
  <void>SetCollapseRange <interval>range
  <interval>GetCollapseRange()
 Actions:

Interface: MissingUVCoordinates
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: refhierarchy
 Properties:
 Methods:
  <boolean>IsRefTargetInstanced <maxObject>refTarget
 Actions:

Interface: DaylightSystemFactory
 Properties:
 Methods:
 Actions:

Interface: sceneStateMgr
 Properties:
 Methods:
  <integer>GetCount()
  <string>GetSceneState <index>index
  <index>FindSceneState <string>name
  <bool>Capture <string>name <bitArray by value>parts
  <bool>Restore <string>name <bitArray by value>parts
  <bool>Delete <string>name
  <bool>Rename <string>oldname <string>newname
  <bitArray by value>GetParts <string>name
  <integer>PartsCount()
  <index>MapPartToIndex <string>part
  <string>MapIndexToPart <index>index
  <bool>CaptureAllParts <string>name
  <bool>RestoreAllParts <string>name
 Actions:

Interface: manip
 Properties:
  .msXYPlane : Interface : Read
  .msXZPlane : Interface : Read
  .msYZPlane : Interface : Read
 Methods:
  <mesh>makeSphere <point3 by value>pos <float>radius <integer>segments
  <mesh>makeTorus <point3 by value>pos <float>radius <float>radius2 <integer>segs <integer>sides
  <mesh>makeBox <point3 by value>pos <float>l <float>w <float>h <integer>lsegs <integer>wsegs <integer>hsegs
  <Interface>makePlaneFromPts <point3 by value>p1 <point3 by value>p2 <point3 by value>p3
  <Interface>makePlaneFromNormal <point3 by value>normal <point3 by value>point
  <Interface>makeGizmoShape()
  <Interface>makeCircle <point3 by value>center <float>radius <integer>segments
 Actions:

Interface: FlightStudio
 Properties:
  .OverrideColors : integer : Read
  .OverrideMaterials : integer : Read
  .OverrideTextures : integer : Read
  .OverrideLineStyles : integer : Read
  .OverrideSounds : integer : Read
  .OverrideLightSources : integer : Read
  .OverrideLightPoints : integer : Read
 Methods:
  <void>Browser()
  <void>RefreshBrowser()
  <float>GetLodDistance()
  <void>SetLodDistance <float>LodDistance
  <boolean>IsLodDistanceSet()
  <void>LodLeastDetail()
  <void>LodLessDetail()
  <void>LodMoreDetail()
  <void>LodMostDetail()
  <boolean>CreateGroup()
  <boolean>CreateObject()
  <boolean>CreateSwitch()
  <boolean>CreateLOD()
  <boolean>CreateDOF()
  <boolean>CreateBSP()
  <boolean>CreateClipRegion()
  <boolean>CreateExternalRef()
  <boolean>CreateLightPoint()
  <string>GetComment <node>Node
  <boolean>PutComment <node>Node <string>String
  <boolean>HasData <node>node
  <boolean>CopyData <node>srcnode <node>dstnode
  <boolean>RemoveData <node>node
  <string>GetLastImport()
  <boolean>IsOfType <node>Node <string>String
  <boolean>SetKeepTriangles <node>Node <boolean>Flag
  <boolean>GetKeepTriangles <node>Node
  <boolean>AddTextureAttr <texturemap>Texmap
  <boolean>RemoveTextureAttr <texturemap>Texmap
  <string>GetExternalRefFilename <node>Node
  <boolean>PutExternalRefFilename <node>Node <string>String
  <integer>GetExternalRefFlags <node>Node
  <boolean>PutExternalRefFlags <node>Node <integer>Flags
 Actions:

Interface: OGSDiagnostics
 Properties:
  .HardwareReport : string : Read
 Methods:
 Actions:

Interface: InterfaceIDRegistry
 Properties:
 Methods:
 Actions:

Interface: paramWire
 Properties:
 Methods:
  <void>start()
  <void>openEditor()
  <void>editParams <value>leftParam <value>rightParam
  <void>editParam <value>param
  <void>editControllers <control>leftController <control>rightController
  <void>editController <control>controller
  <bool>connect <value>fromParam <value>toParam <string>toExpr
  <bool>connect2Way <value>leftParam <value>rightParam <string>leftExpr <string>rightExpr
  <bool>disconnect <control>controller
  <bool>disconnect2Way <control>leftController <control>rightController
 Actions:

Interface: LoadSaveAnimation
 Properties:
 Methods:
  <filename>loadAnimationDlg()
  <filename>saveAnimationDlg()
  <boolean>saveAnimation <filename>fileName <&node array>nodes <&TSTR array>userAttributes <&TSTR array>userValues animatedTracks:<boolean> includeConstraints:<boolean> keyableTracks:<boolean> saveSegment:<boolean> segInterval:<interval by value> segKeyPerFrame:<boolean>
     nodes is In and Out parameter
     userAttributes is In and Out parameter
     userValues is In and Out parameter
     animatedTracks default value: true
     includeConstraints default value: true
     keyableTracks default value: false
     saveSegment default value: false
     segInterval default value: (interval 0f 0f)
     segKeyPerFrame default value: false
  <boolean>saveAnimationNodeAnim <filename>fileName <&Interface array>nodeAnims <&TSTR array>userAttributes <&TSTR array>userValues animatedTracks:<boolean> includeConstraints:<boolean> keyableTracks:<boolean> saveSegment:<boolean> segInterval:<interval by value> segKeyPerFrame:<boolean>
     nodeAnims is In and Out parameter
     userAttributes is In and Out parameter
     userValues is In and Out parameter
     animatedTracks default value: true
     includeConstraints default value: true
     keyableTracks default value: false
     saveSegment default value: false
     segInterval default value: (interval 0f 0f)
     segKeyPerFrame default value: false
  <boolean>loadAnimation <filename>fileName <&node array>nodes relative:<boolean> insert:<boolean> insertTime:<time> stripLayers:<boolean> useMapFile:<boolean> mapFileName:<&TSTR>
     nodes is In and Out parameter
     relative default value: true
     insert default value: false
     insertTime default value: 0f
     stripLayers default value: false
     useMapFile default value: false
     mapFileName default value: undefined
     mapFileName is In and Out parameter
  <boolean>loadAnimationNodeAnim <filename>fileName <&Interface array>nodeAnims relative:<boolean> insert:<boolean> insertTime:<time> useMapFile:<boolean> mapFileName:<&TSTR>
     nodeAnims is In and Out parameter
     relative default value: true
     insert default value: false
     insertTime default value: 0f
     useMapFile default value: false
     mapFileName default value: undefined
     mapFileName is In and Out parameter
  <boolean>createMapFile <filename>fileName <&node array>nodes <filename>incomingAnimationFile <&TSTR array>userAttributes <&TSTR array>userValues <&Interface array>retargetData nodeMapType:<enum> matchControllerExactName:<boolean> matchControllerType:<boolean> stripLayers:<boolean>
     nodes is In and Out parameter
     userAttributes is In and Out parameter
     userValues is In and Out parameter
     retargetData is In and Out parameter
     nodeMapType enums: {#matchExactNodeName|#matchClosestNodeName|#matchNodeHierarchy}
     nodeMapType default value: #matchClosestNodeName
     matchControllerExactName default value: true
     matchControllerType default value: false
     stripLayers default value: false
  <boolean>createMapFileNodeAnim <filename>fileName <&Interface array>nodeAnims <filename>incomingAnimationFile <&TSTR array>userAttributes <&TSTR array>userValues <&Interface array>retargetData nodeMapType:<enum> matchControllerExactName:<boolean> matchControllerType:<boolean>
     nodeAnims is In and Out parameter
     userAttributes is In and Out parameter
     userValues is In and Out parameter
     retargetData is In and Out parameter
     nodeMapType enums: {#matchExactNodeName|#matchClosestNodeName|#matchNodeHierarchy}
     nodeMapType default value: #matchClosestNodeName
     matchControllerExactName default value: true
     matchControllerType default value: false
  <Interface>makeRetargetData()
  <boolean>getUserAttributes <filename>fileName <&TSTR array>userAttributes <&TSTR array>userValues
     userAttributes is In and Out parameter
     userValues is In and Out parameter
  <string>getAnimFileExtension()
  <string>getAnimMapFileExtension()
  <filename>getAnimFileDirectory()
  <filename>getAnimMapFile()
  <void>setAnimFileDirectory <filename>fileName
  <void>setAnimMapFile <filename>fileName
  <Interface by value array>setUpAnimsForSave <&node array>nodesToSetup animatedTracks:<boolean> includeContraints:<boolean> keyable:<boolean>
     nodesToSetup is In and Out parameter
     animatedTracks default value: true
     includeContraints default value: true
     keyable default value: false
  <Interface by value array>setUpAnimsForLoad <&node array>nodesToSetup includePB2s:<boolean> stripLayers:<boolean>
     nodesToSetup is In and Out parameter
     includePB2s default value: false
     stripLayers default value: false
  <Interface by value array>setUpAnimsForMap <&node array>nodesToSetup stripLayers:<boolean>
     nodesToSetup is In and Out parameter
     stripLayers default value: false
  <boolean>replaceAttributesInMapFile <filename>mapFileName <filename>newMapFileName <&TSTR array>oldStrings <&TSTR array>newStrings <boolean>mapName
     oldStrings is In and Out parameter
     newStrings is In and Out parameter
  <boolean>createDefaultMapFile <&node array>nodes <filename>mapFileName
     nodes is In and Out parameter
  <void>createNodeAnimsForLoad <&maxObject array>anims <&maxObject array>clients <&maxObject array>subNums <&Interface array>nodeAnims
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
     nodeAnims is In and Out parameter
  <void>createNodeAnimsForSave <&maxObject array>anims <&maxObject array>clients <&maxObject array>subNums <&Interface array>nodeAnims
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
     nodeAnims is In and Out parameter
  <void>createNodeAnimsForMap <&maxObject array>anims <&maxObject array>clients <&maxObject array>subNums <&Interface array>nodeAnims
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
     nodeAnims is In and Out parameter
  <filename>loadAnimationDlgFromAnims <&maxObject array>anims <&maxObject array>clients <&integer array>subNums
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
  <filename>saveAnimationDlgFromAnims <&maxObject array>anims <&maxObject array>clients <&integer array>subNums
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
 Actions:

Interface: NullInterface
 Properties:
 Methods:
 Actions:

Interface: LightingUnits
 Properties:
 Methods:
  <bool>IsLightingSystemSI()
  <bool>IsLightingSystemAS()
  <void>SetLightingSystemToSI()
  <void>SetLightingSystemToAS()
  <string>GetLuminanceUnits()
  <string>GetIlluminanceUnits()
  <float>ConvertASToSI <float>as_value
  <float>ConvertSIToAS <float>si_value
  <float>ConvertToCurrentSystem <float>value <bool>is_SI_value
 Actions:

Interface: UtilityPanel
 Properties:
 Methods:
  <integer>OpenUtility <class>ClassName
  <integer>CloseUtility()
 Actions:

Interface: NamedSelectionSetManager
 Properties:
 Methods:
  <integer>GetNumNamedSelSets()
     GetNumNamedSelSets - no automatic redraw after invoked
  <string>GetNamedSelSetName <integer>setIndex
     GetNamedSelSetName - no automatic redraw after invoked
  <integer>GetNamedSelSetItemCount <integer>setIndex
     GetNamedSelSetItemCount - no automatic redraw after invoked
  <node>GetNamedSelSetItem <integer>setIndex <integer>itemIndex
     GetNamedSelSetItem - no automatic redraw after invoked
  <boolean>AddNewNamedSelSet <&node array>nodeSet <&TSTR>setName
     AddNewNamedSelSet - no automatic redraw after invoked
     nodeSet is In parameter
     setName is In parameter
  <boolean>RemoveNamedSelSetByIndex <integer>setName
     RemoveNamedSelSetByIndex - no automatic redraw after invoked
  <boolean>RemoveNamedSelSetByName <&TSTR>setName
     RemoveNamedSelSetByName - no automatic redraw after invoked
     setName is In parameter
  <boolean>ReplaceNamedSelSetByIndex <&node array>nodeSet <integer>setIndex
     ReplaceNamedSelSetByIndex - no automatic redraw after invoked
     nodeSet is In parameter
  <boolean>ReplaceNamedSelSetByName <&node array>nodeSet <&TSTR>setName
     ReplaceNamedSelSetByName - no automatic redraw after invoked
     nodeSet is In parameter
     setName is In parameter
  <boolean>GetNamedSelSetList <&node array>nodeSet <integer>setIndex
     GetNamedSelSetList - no automatic redraw after invoked
     nodeSet is In and Out parameter
  <boolean>SetNamedSelSetName <integer>setIndex <&TSTR>setName
     SetNamedSelSetName - no automatic redraw after invoked
     setName is In parameter
 Actions:

Interface: OpenEdges
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: BitmapProxyMgr
 Properties:
  .globalProxyEnable : boolean : Read|Write
  .globalProxyRenderMode : enum : Read|Write
     globalProxyRenderMode enums: {#renderMode_UseProxies|#renderMode_UseFullRes_KeepInMemory|#renderMode_UseFullRes_FlushFromMemory}
  .globalProxySizeFactor : enum : Read|Write
     globalProxySizeFactor enums: {#full|#half|#third|#quarter|#eighth}
  .globalProxySizeMin : integer : Read|Write
 Methods:
  <enum>GetProxySizeFactor <string>bitmap
     GetProxySizeFactor enums: {#full|#half|#third|#quarter|#eighth
  <void>SetProxySizeFactor <string>bitmap <enum>factor
     factor enums: {#full|#half|#third|#quarter|#eighth}
  <boolean>GetProxyUseGlobal <string>bitmap
  <void>SetProxyUseGlobal <string>bitmap <boolean>useGlobal
  <boolean>GetProxyReady <string>bitmap
  <void>RefreshAll requestRefresh:<enum>
     requestRefresh enums: {#updateStale|#refreshAll|#generateAll}
     requestRefresh default value: #updateStale
  <void>GenerateAll requestRefresh:<enum>
     requestRefresh enums: {#updateStale|#refreshAll|#generateAll}
     requestRefresh default value: #updateStale
  <void>ShowConfigDialog bitmapFilenames:<string array>
     bitmapFilenames default value: #()
  <void>ShowPrecacheDialog bitmapFilenames:<string array>
     bitmapFilenames default value: #()
 Actions:

Interface: mental_ray_Preferences
 Properties:
  .mrExtensionsActive : bool : Read|Write
 Methods:
 Actions:

Interface: ProjectionRenderMgr
 Properties:
 Methods:
 Actions:

Interface: FileResolutionManager
 Properties:
 Methods:
  <bool>getFullFilePath <&TSTR>filePath <enum>assetType byPassCache:<bool>
     filePath is In and Out parameter
     assetType enums: {#Other|#Bitmap|#XRef|#Photometric|#Animation|#VideoPost|#BatchRender|#ExternalLink|#RenderOutput|#PreRenderScript|#PostRenderScript|#Sound|#Container}
     byPassCache default value: false
  <bool>getFullFilePath_assetID <TSTR>assetID <&TSTR>filePath byPassCache:<bool>
     filePath is Out parameter
     byPassCache default value: false
  <DWORD>GetMaximumCacheDuration()
  <void>SetMaximumCacheDuration <DWORD>newMaxDuration
  <bool>IsCachingEnabled()
  <void>EnableCaching()
  <void>DisableCaching()
  <void>doGetUniversalFileName <&TSTR>aFullFilePath
     aFullFilePath is In and Out parameter
  <INT64>GetNumCacheHit()
  <integer>GetNumAssetTypes()
  <string>GetAssetTypeString <enum>assetType
     assetType enums: {#Other|#Bitmap|#XRef|#Photometric|#Animation|#VideoPost|#BatchRender|#ExternalLink|#RenderOutput|#PreRenderScript|#PostRenderScript|#Sound|#Container}
 Actions:

Interface: MultipleEdges
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: ATSCustomDepsOps
 Properties:
 Methods:
  <void>LaunchDialog()
     LaunchDialog - no automatic redraw after invoked
  <integer>NumFiles()
     NumFiles - no automatic redraw after invoked
  <integer>GetFiles <&filename array>FileList
     GetFiles - no automatic redraw after invoked
     FileList is In and Out parameter
  <integer>AddFile <filename>Filename
     AddFile - no automatic redraw after invoked
  <bool>SetFile <index>Index <filename>Filename
     SetFile - no automatic redraw after invoked
  <integer>RemoveFileByIndex <index>Index
     RemoveFileByIndex - no automatic redraw after invoked
  <integer>RemoveFileByName <filename>Filename
     RemoveFileByName - no automatic redraw after invoked
  <void>RemoveAll()
     RemoveAll - no automatic redraw after invoked
 Actions:

Interface: LockedTracksMan
 Properties:
  .unLockOverride : bool : Read|Write
 Methods:
  <void>PushUberUnLockOverride()
  <void>PopUberUnLockOverride()
  <integer>GetUberUnLockOverride()
  <void>SetLocks <bool>lock <&maxObject array>anims <&maxObject array>clients <&index array>subNums <bool>includeChildren
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
  <void>ToggleLocks <&maxObject array>anims <&maxObject array>clients <&index array>subNums <bool>includeChildren
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
  <void>SetExposedUI <bool>expose <&maxObject array>anims
     anims is In and Out parameter
  <bool>GetExposedUI <maxObject>anim
  <bool>GetLocked <maxObject>anim <maxObject>client <index>subNum <bool>checkOverride
  <bool>IsLockable <maxObject>anim <maxObject>client <index>subNum
  <void>FindLockedAnims <bool>locked <bool>checkOverride <maxObject>refTarget <&maxObject array>anims <&maxObject array>clients <&index array>subNums
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
  <void>UnlockChildren <&maxObject array>anims <&maxObject array>clients <&index array>subNums
     anims is In and Out parameter
     clients is In and Out parameter
     subNums is In and Out parameter
  <bool>IsAnimOverrideUnlocked <maxObject>anim
 Actions:

Interface: memStreamMgr
 Properties:
 Methods:
  <Interface>openFile <filename>fname favor_type:<enum> code_page:<integer>
     favor_type enums: {#FAVOR_ACP|#FAVOR_UTF8}
     favor_type default value: #FAVOR_ACP
     code_page default value: 0
  <Interface>openString <string>string
  <void>close <Interface>memStream
 Actions:

Interface: MXSEditor
 Properties:
  .x : integer : Read|Write
  .y : integer : Read|Write
  .width : integer : Read|Write
  .height : integer : Read|Write
  .enableCallbacks : boolean : Read|Write
  .isVisible : boolean : Read|Write
  .verbose : boolean : Read|Write
  .isExtendedVP : boolean : Read
  .mainHWND : HWND : Read
  .editHWND : HWND : Read
  .documentCount : integer : Read
  .currentDocument : string : Read
 Methods:
  <void>redraw()
  <void>show()
  <boolean>endExtendedVP()
  <void>reloadOptions()
  <boolean>editFile <string>filename quiet:<boolean>
     quiet default value: false
  <string>documentAtNumber <integer>index
  <void>menuCommand <string>menucode
  <boolean>setWindowPosition <integer>x <integer>y <integer>width <integer>height
  <string>getConfigProperty <string>name
  <integer>getConfigIntProperty <string>name
  <void>setConfigProperty <string>name <string>value
  <integer>listFunctions()
  <integer>listConstants()
  <integer>listProperties()
  <integer>listMenucodes()
 Actions:

Interface: LuminosityUtil
 Properties:
 Methods:
  <float>illumination <float>r <float>g <float>b
 Actions:

Interface: timeSlider
 Properties:
 Methods:
  <void>setVisible <boolean>visible
  <boolean>isVisible()
 Actions:

Interface: imerge
 Properties:
 Methods:
 Actions:

Interface: AutodeskMaterialManager
 Properties:
 Methods:
  <integer>GetCategoryCount()
  <string>GetCategoryUiName <integer>categoryIndex
  <integer>GetDefinitionCount <integer>categoryIndex
  <string>GetDefinitionUiName <integer>categoryIndex <integer>definitionIndex
  <string>GetDefinitionThumbnailURL <integer>categoryIndex <integer>definitionIndex
  <string>GetDefinitionIdentifier <integer>categoryIndex <integer>definitionIndex
  <material>CreateAutodeskMaterial <string>definitionIdentifier
  <material>CreateAutodeskTexmap <string>definitionIdentifier
 Actions:

Interface: reactionMgr
 Properties:
 Methods:
  <void>openEditor()
 Actions:

Interface: IInteractionMode
 Properties:
  .CurrentMode : enum : Read|Write
     CurrentMode enums: {#3dsMaxMode|#MayaMode|#CustomizedMode}
 Methods:
 Actions:

Interface: msZip
 Properties:
 Methods:
  <boolean>fileInPackage <filename>fileName <&TSTR>extractDir
     extractDir is Out parameter
  <boolean>unloadPackage <filename>fileName <&TSTR>extractDir <&TSTR>dropFile
     extractDir is Out parameter
     dropFile is Out parameter
 Actions:

Interface: OneClickRevit
 Properties:
 Methods:
  <void>RequestViews <integer>id <&TSTR>fileName
     fileName is In parameter
 Actions:

Interface: AssignVertexColors
 Properties:
 Methods:
  <integer>ApplyNodes <node array>nodes vertexPaint:<maxObject>
     vertexPaint default value: undefined
 Actions:

Interface: MaterialExplorerManager
 Properties:
 Methods:
  <bool>OpenMaterialExplorer()
     OpenMaterialExplorer - no automatic redraw after invoked
  <bool>CloseMaterialExplorer()
     CloseMaterialExplorer - no automatic redraw after invoked
  <bool>LoadMaterialExplorerConfiguration <&TSTR>configurationFile
     LoadMaterialExplorerConfiguration - no automatic redraw after invoked
     configurationFile is In parameter
  <bool>SaveMaterialExplorerConfiguration <&TSTR>outputConfigurationFile
     SaveMaterialExplorerConfiguration - no automatic redraw after invoked
     outputConfigurationFile is In parameter
  <bool>IsMaterialExplorerOpen()
     IsMaterialExplorerOpen - no automatic redraw after invoked
 Actions:

Interface: BipAnalyzer
 Properties:
 Methods:
  <void>DoNoiseDetectorAnalysis <&node array>nodeTab <interval>range <float>deviation <boolean>angular <integer>noiseType <node>parentNode
     nodeTab is In and Out parameter
  <void>DoSpikeDetectorAnalysis <&node array>nodeTab <interval>range <float>deviation
     nodeTab is In and Out parameter
  <time by value array>GetResults <node>node
  <void>LoadAnalysisFile <filename>fileName
  <void>SaveAnalysisFile <&node array>nodeTab <filename>fileName
     nodeTab is In and Out parameter
  <void>ClearAnalysisResults()
  <void>DoKneeWobbleAnalysis <&node array>nodeTab <interval>range <float>frameThreshold <float>fluctuationThreshold
     nodeTab is In and Out parameter
  <void>DoKneeExtensionAnalysis <&node array>nodeTab <interval>range <float>kneeAngle
     nodeTab is In and Out parameter
 Actions:

Interface: MentalMillCompiler
 Properties:
 Methods:
 Actions:

Interface: autosave
 Properties:
  .Enable : boolean : Read|Write
  .NumberOfFiles : integer : Read|Write|Validated by Range: 1 to 99
  .Interval : float : Read|Write
  .filename : string : Read|Write
 Methods:
  <void>resettimer()
  <boolean>isactive()
  <void>autobackupnow()
 Actions:

Interface: LightingAnalysisOverlayFactory
 Properties:
 Methods:
 Actions:

Interface: maxOps
 Properties:
  .productVersion : enum : Read
     productVersion enums: {#productVersionDevel|#productVersionTrial|#productVersionOrdinary|#productVersionEdu|#productVersionNFR}
  .licenseBehavior : enum : Read
     licenseBehavior enums: {#licenseBehaviorPermanent|#licenseBehaviorExtendable|#licenseBehaviorNonextendable}
  .licenseDaysLeft : integer : Read
  .trackbar : Interface : Read
  .isNetworkLicense : boolean : Read
  .autoGrid : boolean : Read|Write
  .startNewShapeLock : boolean : Read|Write
  .productAppID : enum : Read
     productAppID enums: {#none|#max|#viz|#gmax|#vizR}
  .productID : enum : Read
     productID enums: {#3dsMax|#3dsMaxDesign}
  .affectChildren : boolean : Read|Write
  .hideFrozenObjects : boolean : Read|Write
  .pivotMode : enum : Read|Write
     pivotMode enums: {#none|#pivotOnly|#objectOnly|#hierarchyOnly}
  .setKeyMode : boolean : Read|Write
  .setKeySuspend : boolean : Read|Write
  .setKeyFilters : enum by value array : Read
     setKeyFilters enums: {#all|#position|#rotation|#scale|#ikParams|#objParams|#custAttribs|#modifiers|#materials|#other}
  .setKeyNodeSets : TSTR by value array : Read
  .setKeyNodeSetCurrent : TSTR : Read|Write
  .inProgressiveMode : boolean : Read
  .paintSelBrushSize : integer : Read|Write
  .overrideControllerRangeDefault : boolean : Read|Write
  .springQuickEditMode : boolean : Read|Write
  .springRollingStart : integer : Read|Write
  .autoKeyDefaultKeyOn : boolean : Read|Write
  .autoKeyDefaultKeyTime : time : Read|Write
  .trajectoryMode : bool : Read|Write
  .trajectoryKeySubMode : bool : Read|Write
  .trajectoryAddKeyMode : bool : Read|Write
  .rendUseIterative : boolean : Read|Write
  .mtlDlgMode : enum : Read|Write
     mtlDlgMode enums: {#basic|#advanced}
  .nameSuffixLength : integer : Read|Write
  .overrideLanguageSpecifiedInSceneFile : bool : Read|Write
  .useCodePageSpecifiedInSceneFile : bool : Read|Write
  .languageToUseForFileIO : enum : Read|Write
     languageToUseForFileIO enums: {#current|#English|#German|#French|#Japanese|#Korean|#Chinese}
  .legacyFilesCanBeStoredUsingUTF8 : bool : Read|Write
 Methods:
  <boolean>canImportBitmap <filename>fileName
  <void>displayActiveCameraViewWithMultiPassEffect()
     displayActiveCameraViewWithMultiPassEffect - no automatic redraw after invoked
  <void>setActiveViewportTransparencyDisplay <integer>transparencyLevel
  <boolean>loadCUIFile <filename>fileName
  <boolean>isFeatureLicensed <integer>featureNumber
  <Interface>GetCurRenderElementMgr()
  <Interface>GetRenderElementMgr <enum>
      enums: {#Production|#Draft}
  <void>CollapseNode <node>node <boolean>noWarning
  <boolean>CollapseNodeTo <node>node <index>modIndex <boolean>noWarning
  <bool>CloneNodes <&node array>nodes offset:<point3 by value> expandHierarchy:<bool> cloneType:<enum> actualNodeList:<&node array> newNodes:<&node array>
     nodes is In parameter
     offset default value: [0,0,0]
     expandHierarchy default value: false
     cloneType enums: {#copy|#instance|#reference}
     cloneType default value: #copy
     actualNodeList default value: #()
     actualNodeList is Out parameter
     newNodes default value: #()
     newNodes is Out parameter
  <boolean>setSelectionType <boolean>auto <enum>method
     method enums: {#window|#crossing|#leftToRight|#rightToLeft}
  <maxObject>getNodeByHandle <DWORD>handle
  <Interface>getTrackBar()
  <void>activateSetKeyMode <boolean>onOff
  <void>allTracksCommitSetKeyBuffer()
  <void>allTracksRevertSetKeyBuffer()
  <boolean>allTracksSetKeyBufferPresent()
  <boolean>getSetKeyMode()
  <boolean>getSetKeyFilterState <enum>filter
     filter enums: {#all|#position|#rotation|#scale|#ikParams|#objParams|#custAttribs|#modifiers|#materials|#other}
  <boolean>setSetKeyFilterState <enum>filter <boolean>onOff
     filter enums: {#all|#position|#rotation|#scale|#ikParams|#objParams|#custAttribs|#modifiers|#materials|#other}
  <void>startNewShape()
  <void>beginProgressiveMode()
  <void>endProgressiveMode()
  <void>deleteSelectedAnimation()
  <void>getDefaultTangentType <&enum>dfltInTangentType <&enum>dfltOutTangentType
     dfltInTangentType enums: {#smooth|#linear|#step|#fast|#slow|#custom|#flat}
     dfltInTangentType is Out parameter
     dfltOutTangentType enums: {#smooth|#linear|#step|#fast|#slow|#custom|#flat}
     dfltOutTangentType is Out parameter
  <void>setDefaultTangentType <enum>dfltInTangentType <enum>dfltOutTangentType writeInCfgFile:<boolean>
     dfltInTangentType enums: {#smooth|#linear|#step|#fast|#slow|#custom|#flat}
     dfltOutTangentType enums: {#smooth|#linear|#step|#fast|#slow|#custom|#flat}
     writeInCfgFile default value: true
  <void>colorById <DWORD>id <&color>color
     color is Out parameter
  <void>findNodes <&node array>templateNodes <&node array>foundNodes nodePropsToMatch:<&enum array>
     templateNodes is In parameter
     foundNodes is Out parameter
     nodePropsToMatch enums: {#nodePropMaterial|#nodePropLayer}
     nodePropsToMatch default value: #()
     nodePropsToMatch is In parameter
  <void>deleteSelectedTrajectoryKey()
  <matrix3>getTransformGizmoTM()
  <IObject>getViewportShadingSettings()
  <void>persistFileLanguageSettings()
 Actions:

Interface: ViewportSSB
 Properties:
  .CubeBias : float : Read|Write
  .EVSMConfig : point3 by value : Read|Write
  .ShadowMapSize : integer : Read|Write
  .AreaShadow : boolean : Read|Write
  .TransAreaShadow : boolean : Read|Write
 Methods:
  <TSTR>GetVideoMemoryUsed()
 Actions:

Interface: SceneEffectLoader
 Properties:
 Methods:
  <bool>LoadSceneEffect <filename>effectFile effectType:<enum> numberOfPasses:<integer>
     effectType enums: {#Post|#Pre|#Env}
     effectType default value: #Post
     numberOfPasses default value: 0
  <void>ResetEffects()
  <bool>EnableSceneEffects <bool>enable
  <bool>IsSceneEffectsEnabled()
  <integer>GetNumberOfSceneEffects effectType:<enum>
     effectType enums: {#Post|#Pre|#Env}
     effectType default value: #Post
  <bool>RemoveSceneEffect <index>index effectType:<enum>
     effectType enums: {#Post|#Pre|#Env}
     effectType default value: #Post
  <material>GetSceneEffect <index>index effectType:<enum>
     effectType enums: {#Post|#Pre|#Env}
     effectType default value: #Post
 Actions:

Interface: custAttribCollapseManager
 Properties:
  .surviveState : boolean : Read|Write
  .retainSubAnimCAs : boolean : Read|Write
 Methods:
 Actions:

Interface: mental_ray_Public_Interface
 Properties:
 Methods:
 Actions:

Interface: quadMenuSettings
 Properties:
 Methods:
  <void>ResetDefaults()
  <void>SetBorderSize <integer>borderSize
  <integer>GetBorderSize()
  <void>SetHorizontalMarginInPoints <integer>horizontalMarginInPoints
  <integer>GetHorizontalMarginInPoints()
  <void>SetVerticalMarginInPoints <integer>verticalMarginInPoints
  <integer>GetVerticalMarginInPoints()
  <void>SetItemFontFace <string>szItemFontFace
  <string>GetItemFontFace()
  <void>SetTitleFontFace <string>szTitleFontFace
  <string>GetTitleFontFace()
  <void>SetItemFontSize <integer>itemFontSize
  <integer>GetItemFontSize()
  <void>SetTitleFontSize <integer>titleFontSize
  <integer>GetTitleFontSize()
  <void>SetUseUniformItemHeight <boolean>useUniformItemHeight
  <boolean>GetUseUniformItemHeight()
  <void>SetOpacity <float>opacity
  <float>GetOpacity()
  <void>SetDisplayMethod <integer>displayMethod
  <integer>GetDisplayMethod()
  <void>SetAnimatedSteps <integer>animatedSteps
  <integer>GetAnimatedSteps()
  <void>SetAnimatedStepTime <integer>animatedStepTime
  <integer>GetAnimatedStepTime()
  <void>SetSubMenuPauseTime <integer>subMenuPauseTime
  <integer>GetSubMenuPauseTime()
  <void>SetUseLastExecutedItem <boolean>useLastSelectedItem
  <boolean>GetUseLastExecutedItem()
  <void>SetRepositionWhenClipped <boolean>repositionWhenClipped
  <integer>GetRepositionWhenClipped()
  <void>SetRemoveRedundantSeparators <boolean>removeRedundantSeparators
  <integer>GetRemoveRedundantSeparators()
  <void>SetFirstQuadDisplayed <integer>firstQuadDisplayed
  <integer>GetFirstQuadDisplayed()
  <void>SetUseUniformQuadWidth <boolean>useUniformQuadWidth
  <boolean>GetUseUniformQuadWidth()
  <void>SetMirrorQuad <boolean>mirrorQuad
  <integer>GetMirrorQuad()
  <void>SetMoveCursorOnReposition <boolean>moveCursorOnReposition
  <boolean>GetMoveCursorOnReposition()
  <void>SetReturnCursorAfterReposition <boolean>returnCursorAfterReposition
  <boolean>GetReturnCursorAfterReposition()
  <void>SetInitialCursorLocInBox_0to1 <float>initialCursorLocX <float>initialCursorLocY
  <float>GetInitialCursorLocXInBox_0to1()
  <float>GetInitialCursorLocYInBox_0to1()
  <void>SetTitleBarBackgroundColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetTitleBarBackgroundColor <integer>quad
  <void>SetTitleBarTextColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetTitleBarTextColor <integer>quad
  <void>SetItemBackgroundColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetItemBackgroundColor <integer>quad
  <void>SetItemTextColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetItemTextColor <integer>quad
  <void>SetLastExecutedItemTextColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetLastExecutedItemTextColor <integer>quad
  <void>SetHighlightedItemBackgroundColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetHighlightedItemBackgroundColor <integer>quad
  <void>SetHighlightedItemTextColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetHighlightedItemTextColor <integer>quad
  <void>SetBorderColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetBorderColor <integer>quad
  <void>SetDisabledShadowColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetDisabledShadowColor <integer>quad
  <void>SetDisabledHighlightColor <integer>quad <&RGB color>color
     color is In and Out parameter
  <&RGB color>GetDisabledHighlightColor <integer>quad
 Actions:

Interface: dragAndDrop
 Properties:
 Methods:
  <void>globalEnableDragAndDrop <boolean>onOff
  <boolean>isEnabled()
  <boolean>enableDragAndDrop <HWND>window <boolean>onOff
  <boolean>dropPackage <HWND>window <&point>mousePoint <&filename array>files
     mousePoint is In and Out parameter
     files is In and Out parameter
  <boolean>downloadPackage <&filename array>files <filename>directory <boolean>showProgress
     files is In and Out parameter
  <filename>getDownloadDirectory()
  <boolean>DownloadUrlToDisk <string>url <filename>fileName <integer>flags
  <node>ImportContextNode()
 Actions:

Interface: Containers
 Properties:
 Methods:
  <node>CreateInheritedContainer <filename>asset
  <node>CreateContainer <&node array>contentNodes
     contentNodes is In and Out parameter
  <Interface>IsInContainer <node>isInContainer
  <Interface>IsContainerNode <node>isContainerNode
 Actions:

Interface: menuMan
 Properties:
 Methods:
  <boolean>loadMenuFile <filename>file
  <boolean>saveMenuFile <filename>file
  <filename>getMenuFile()
  <void>updateMenuBar()
  <boolean>registerMenuContext <integer>contextId
  <Interface>findMenu <string>menuName
  <Interface>findQuadMenu <string>menuName
  <boolean>unRegisterMenu <Interface>menu
  <boolean>unRegisterQuadMenu <Interface>quadMenu
  <Interface>createMenu <string>name
  <Interface>createQuadMenu <string>name <string>quad1Name <string>quad2Name <string>quad3Name <string>quad4Name
  <Interface>createSubMenuItem <string>name <Interface>subMenu
  <Interface>createSeparatorItem()
  <Interface>createActionItem <string>macroScriptName <string>macroScriptCategory
  <boolean>setViewportRightClickMenu <enum>which <Interface>menu
     which enums: {#nonePressed|#shiftPressed|#altPressed|#controlPressed|#shiftAndAltPressed|#shiftAndControlPressed|#controlAndAltPressed|#shiftAndAltAndControlPressed}
  <Interface>getViewportRightClickMenu <enum>which
     which enums: {#nonePressed|#shiftPressed|#altPressed|#controlPressed|#shiftAndAltPressed|#shiftAndControlPressed|#controlAndAltPressed|#shiftAndAltAndControlPressed}
  <Interface>getMainMenuBar()
  <boolean>setMainMenuBar <Interface>menu
  <bool>getShowAllQuads <Interface>quadMenu
  <void>setShowAllQuads <Interface>quadMenu <bool>value
  <string>getQuadMenuName <Interface>quadMenu
  <void>setQuadMenuName <Interface>quadMenu <string>name
  <integer>numMenus()
  <Interface>getMenu <index>index
  <integer>numQuadMenus()
  <Interface>getQuadMenu <index>index
  <Interface>createMenuItemFromAction <string>group <string>action category:<string>
     category default value: undefined
 Actions:

Interface: ICEFlowShapeControl
 Properties:
 Methods:
 Actions:

Interface: XMLMaterial
 Properties:
  .bitmapURL : string : Read|Write
  .thumbnails : bool : Read|Write
  .thumbnailURL : string : Read|Write
  .catalogFormat : bool : Read|Write
  .transformWithXSLT : bool : Read|Write
  .transformURL : string : Read|Write
 Methods:
  <bool>export <material>mtl <filename>filename
  <bool>exportArray <&material array>mtlArray <filename>filename
     mtlArray is In and Out parameter
 Actions:

Interface: nvpx
 Properties:
  .UseAdaptiveForce : boolean : Read|Write
  .gravityMode : enum : Read|Write
     gravityMode enums: {#none|#directional|#object}
  .gravityObject : node : Read|Write
 Methods:
  <integer>GetPhysXSDKVersion()
  <string>GetPhysXSDKVersionString()
  <integer>GetPhysXSDKVersionMajor()
  <integer>GetPhysXSDKVersionMinor()
  <integer>GetPhysXSDKVersionBugFix()
  <integer>GetApexSDKVersion()
  <integer>InitializePhysX <value>stream
  <integer>CreateToolbar()
  <void>ShowToolbar <boolean>show
  <boolean>ShowValidateScene <boolean>automated
  <boolean>HwAvailable()
  <integer>GetScreenHeight()
  <float>GetSimulationFPS()
  <boolean>PrintSimulationFPS <boolean>onoff
  <integer>AddRigidbody <node>inode
  <integer>AddConstraint <node>node
  <integer>AddDistanceJoint <node>node
  <boolean>CaptureInitTransform <node>inode
  <integer>SetRigidbodyShapeFlag <node>inode <TSTR by value>flagname <boolean>value
  <integer>RemoveRigidbody <node>inode
  <integer>RemoveAll()
  <integer>NotifyBeforeFirstFrame()
  <integer>ClearInvalidNodes()
  <void>PauseSimulation()
  <integer>Simulate <float>deltat
  <integer>SetSimulationSubSteps <integer>numSteps
  <integer>SimulationReset()
  <void>BeforeAddPhysXActors()
  <void>SetSimulationState <integer>state
  <integer>GetSimulationState()
  <boolean>IsSimulating()
  <integer>ExportPhysXScene <string>filename <string>extension
  <integer>ExportPhysXProjectFile <string>physxProjectPath <string>physxProjectName
  <integer>ExportPhysXProject <string>physxProjectPath <string>physxProjectName <string>fbxFileName
  <integer>PrepExportPhysXScene <boolean>isexportphysx <string>extension
  <integer>PrepExportAPEXClothing <boolean>exportAPEXClothing <string>apExtension <boolean>useModelSpace <float>scale <boolean>addHulls <boolean>exportCTW <boolean>exportFBX <boolean>exportSelected <boolean>launchViewer <boolean>reverseWinding <boolean>omitMeshSubpartName
  <integer>PrepExportAPEXDestruction <boolean>exportAPEXDestruction <string>apExtension <boolean>exportSelected
  <&point3>GetLinearVelocity <node>inode
  <&point3>GetAngularVelocity <node>inode
  <integer>SetLinearVelocity <node>inode <&point3>linearvelocity
     linearvelocity is In and Out parameter
  <integer>SetAngularVelocity <node>inode <&point3>angularvelocity
     angularvelocity is In and Out parameter
  <&point3>GetGlobalPosition <node>inode
  <integer>SetGlobalPosition <node>inode <&point3>position
     position is In and Out parameter
  <&matrix3>GetGlobalPose <node>inode
  <integer>SetGlobalPose <node>inode <&matrix3>pose
     pose is In and Out parameter
  <float>GetMass <node>inode
  <float>SetMass <node>inode <float>value
  <float>GetDynamicFriction <node>inode
  <float>GetStaticFriction <node>inode
  <float>GetRestitution <node>inode
  <integer>SetDynamicFriction <node>inode <float>value
  <integer>SetStaticFriction <node>inode <float>value
  <integer>SetRestitution <node>inode <float>value
  <boolean>SaveMaterial <string>filename <float>staticFriction <float>dynamicFriction <float>bounciness <integer>density
  <float>LoadMaterialDynFric <string>filename
  <float>LoadMaterialStaticFric <string>filename
  <float>LoadMaterialBounciness <string>filename
  <integer>LoadMaterialDensity <string>filename
  <node>CreateBoundingBox <node>inode
  <node>CreateBoundingSphere <node>inode
  <node>CreateBoundingCapsule <node>inode
  <node>CreateBoundingCapsuleFromPoints <matrix3>poseTransform <&float array>points
     points is In and Out parameter
  <node>CreateBoundingShapeConvex <node>inode <integer>vertLimit <float>inflation <integer>style
  <mesh>CreateBoundingConvex <node>inode <integer>vertLimit <float>inflation
  <mesh>CreateBoundingConvexFromNodes <&node array>inodes <integer>vertLimit <float>inflation
     inodes is In and Out parameter
  <boolean>SetAsDynamic <node>inode <boolean>onoff
  <boolean>SetSleepState <node>inode <boolean>onoff
  <boolean>SetRBParam <node>inode <string>paramName <string>paramValue
  <string>GetRBParam <node>inode <string>paramName
  <boolean>SetRBShapeParam <node>inodeRB <node>inodeShape <string>paramName <string>paramValue
  <boolean>GetRBShapeParam <node>inodeRB <node>inodeShape <string>paramName
  <boolean>SetConstraintParam <node>inode <string>paramName <string>paramValue
  <boolean>GetConstraintParam <node>inode <string>paramName
  <integer>DebugPrint()
  <void>DescribeMe()
  <integer>SetSDKParameter <TSTR by value>paramName <float>value
  <float>GetSDKParameter <TSTR by value>paramName
  <integer>SetSDKDefaultParameter <TSTR by value>paramName
  <mesh>CreateConvexHull <mesh>mesh <integer>vertlimit <float>inflation
  <mesh>CreateConvexFromPoints <&float array>points <integer>vertlimit <float>inflation
     points is In and Out parameter
  <point3 by value>GetGravity()
  <integer>SetGravity <point3 by value>gravity
  <float>SetGeometryScale <float>scaleRate
  <float>GetGeometryScale()
  <boolean>SetUseContactReport <boolean>OnOff
  <integer>GetContactsCount()
  <boolean>SelectFirstContact()
  <boolean>GetNextContact()
  <point3 by value>GetContactForce index:<index>
     index default value: 0
  <point3 by value>GetContactPoint index:<index>
     index default value: 0
  <node>GetContactNode0 index:<index>
     index default value: 0
  <node>GetContactNode1 index:<index>
     index default value: 0
  <float>SetContactFilter <float>force
  <float>GetContactFilter()
  <integer>FindSleepingActors()
  <node>GetSleepingActor <integer>index
  <boolean>RBBroken <node>inode
  <integer>PrintTM <node>inode
  <integer>PrintNodeParams <node>inode
  <node>RagdollGetRootBone <node>inode
  <boolean>IsRagdollNode <node>inode
  <boolean>PhysiqueLoad <node>inode
  <integer>PhysiqueGetNumBones <node>inode
  <node>PhysiqueGetBone <node>inode <integer>boneIndex
  <integer>PhysiqueGetNumBoneVertices <node>inode <node>boneNode
  <point3 by value>PhysiqueGetBoneVertex <node>inode <node>boneNode <integer>verticeIndex
  <boolean>IsConvex <node>inode
  <float>CalcVolume <node>inode
  <boolean>ConnectPVD <string>hostName
  <integer>SaveClothingTemplate <string>filePath <string>fileName
  <integer>LoadClothingTemplate <string>filePath
  <integer>RebuildSelectedClothingNode()
  <integer>SaveAPEXClothing <string>filePath <boolean>useModelSpace <float>scale <boolean>addHulls <boolean>exportCTW <boolean>exportFBX <boolean>exportCTP <boolean>exportSelected <boolean>launchViewer <boolean>reverseWinding <boolean>omitMeshSubpartName
  <void>SetButtonCheck <integer>id <boolean>value
  <void>DestroyPhysX()
  <boolean>ParseSkinInfo <node>inode <float>weightThreshold
  <float by value array>GetVerticesFromSkinnedBone <node>inode
  <integer>GetVerticesCountFromSkinnedBone <node>inode
  <boolean>ReleaseSkinInfo()
  <boolean>HaveBoneFloatLimitControl <node>inode <string>block
  <string>GetBoneFloatLimitValue <node>inode <string>block <string>param
  <boolean>IsBone <node>inode
  <boolean>IsBiped <node>inode
  <boolean>IsBipedRoot <node>inode
  <boolean>IsBipedFootsteps <node>inode
  <void>BipedSetKeys <boolean>setKeys
  <integer>GetSolverIterations()
  <integer>SetSolverIterations <integer>count
  <boolean>CreateGround <float>position <&point3>normal
     normal is In and Out parameter
  <boolean>RemoveGround()
  <boolean>SetRBDisplayMaterial <material>dynamicMat <material>kinematicMat <material>staticMat
  <matrix3 by value>GetBonePose <node>inode
  <boolean>LoadRagdollHelperMesh <mesh by value>mesh
  <boolean>SetNullCM()
  <boolean>RemoveNullCM()
  <boolean>ReadSystemUnit <integer>type <float>scale
  <boolean>CopyRigidbody <node>fromNode <node>toNode
  <integer>GetRBMeshCount <node>inode
  <&matrix3>GetRBMeshTM <node>inode <integer>meshIndex
  <integer>SetRBMeshTM <node>inode <integer>meshIndex <&matrix3>pose
     pose is In and Out parameter
  <integer>AddRBMesh <node>inode
  <boolean>DeleteRBMesh <node>inode <integer>meshIndex
  <boolean>ClipboardCopyRBMesh <node>inode <integer>meshIndex
  <boolean>ClipboardPasteRBMesh <node>inode
  <string>GetRBMeshName <node>inode <integer>meshIndex
  <integer>SetRBMeshName <node>inode <integer>meshIndex <string>meshName
  <string>GetRBMeshType <node>inode <integer>meshIndex
  <integer>SetRBMeshType <node>inode <integer>meshIndex <integer>meshType
  <float>GetRBMeshRadius <node>inode <integer>meshIndex
  <integer>SetRBMeshRadius <node>inode <integer>meshIndex <float>radius
  <float>GetRBMeshLength <node>inode <integer>meshIndex
  <integer>SetRBMeshLength <node>inode <integer>meshIndex <float>Length
  <float>GetRBMeshWidth <node>inode <integer>meshIndex
  <integer>SetRBMeshWidth <node>inode <integer>meshIndex <float>Width
  <float>GetRBMeshHeight <node>inode <integer>meshIndex
  <integer>SetRBMeshHeight <node>inode <integer>meshIndex <float>Height
  <node>GetRBMeshCustomNode <node>inode <integer>meshIndex
  <integer>SetRBMeshCustomNode <node>inode <integer>meshIndex <node>CustomNode
  <integer>GetRBMeshVertexLimit <node>inode <integer>meshIndex
  <integer>SetRBMeshVertexLimit <node>inode <integer>meshIndex <integer>VerticeLimit
  <float>GetRBMeshInflation <node>inode <integer>meshIndex
  <integer>SetRBMeshInflation <node>inode <integer>meshIndex <float>Inflation
  <mesh>GetRBMeshShape <node>inode <integer>meshIndex
  <boolean>SetRBMeshShape <node>inode <integer>meshIndex <mesh>newMesh
  <boolean>GetRBMeshOverrideMasterMat <node>inode <integer>meshIndex
  <boolean>SetRBMeshOverrideMasterMat <node>inode <integer>meshIndex <boolean>overrideIt
  <float>SetMeterToSystemUnit <float>newValue
  <float>GetMeterToSystemUnit()
  <boolean>StartIndirectDrag <node>attach
  <boolean>OnIndirectDrag <&point3>mousepos
     mousepos is In and Out parameter
  <boolean>EndIndirectDrag()
  <class>GetObjectClass <node>node
  <boolean>IsApexAvailable()
  <integer>MaterialGetCount()
  <integer>MaterialGetId <integer>matIndex
  <integer>MaterialGetType <integer>matId
  <boolean>MaterialIsLocked <integer>matId
  <integer>MaterialFind <string>ParamName
  <integer>MaterialCreate <integer>type
  <boolean>MaterialRemove <integer>matId
  <string>MaterialGetParam <integer>matId <string>ParamName
  <integer>MaterialSetParam <integer>matId <string>ParamName <string>ParamValue
  <void>RagdollRegenerate <node>ragdoll <&node array>bones
     bones is In and Out parameter
  <void>RagdollAddBone <node>ragdoll <node>boneNode
  <void>RagdollRemoveBone <node>ragdoll <node>boneNode
  <boolean>RagdollSave <node>ragdoll <string>filename
  <boolean>RagdollLoad <node>ragdoll <string>filename
  <boolean>VisualizerGetEnabled()
  <void>VisualizerSetEnabled <boolean>flag
  <float>VisualizerGetScale()
  <float>VisualizerSetScale <float>newScale
  <integer>VisualizerGetPhysXParamCount()
  <string>VisualizerGetPhysXParamName <integer>index
  <integer>VisualizerGetPhysXParam <string>paramName
  <boolean>VisualizerSetPhysXParam <string>paramName <boolean>flag
  <integer>VisualizerGetApexParamCount()
  <string>VisualizerGetApexParamName <integer>index
  <integer>VisualizerGetApexParam <string>paramName
  <boolean>VisualizerSetApexParam <string>paramName <boolean>flag
  <integer>GetPMVisibleForRigidBodies()
  <void>SetPMVisibleForRigidBodies <integer>visible
  <void>ProfilerBegin <string>name
  <void>ProfilerEnd <string>name
  <void>ProfilerDump()
  <node>CreateRagdollHelper()
  <boolean>SupportMultiThread()
  <boolean>UseMultiThread <boolean>onOff
  <boolean>IsMultiThreadOn()
  <boolean>SupportHardwareScene()
  <boolean>UseHardwareScene <boolean>onOff
  <boolean>IsHardwareSceneOn()
  <void>UnitTest_MaterialCreate <integer>type <string>name
  <boolean>UnitTest_MaterialFind <string>name
  <void>UnitTest_MaterialDelete <string>type
  <void>UnitTest_MaterialAssign <node>node <string>name
  <string>UnitTest_MaterialPick <node>node
  <void>OpenHelpFile()
  <void>PhysXPanelTooltip()
  <void>SetCCDMotionThreshold <float>ccdMotionThreshold
  <integer>GetPhysXPluginCount()
  <integer>GetPhysXPluginVersion <integer>Index
  <string>GetPhysXPluginVersionString <integer>Index
  <integer>GetPhysXPluginVersionMajor <integer>Index
  <integer>GetPhysXPluginVersionMinor <integer>Index
  <integer>GetPhysXPluginVersionBugFix <integer>Index
  <boolean>UsePhysXPlugin <integer>Index
  <void>DetachPhysX()
  <void>AttachPhysX()
  <string>GetScriptPath()
  <bool>IsAutodeskVersion()
  <string>GetPluginCompanyName()
  <void>SetAnimationState <boolean>state
  <boolean>GetAnimationState()
  <void>CreateViewer()
  <void>PreCreateViewer()
  <void>PostCreateViewer()
  <string>GetPluginBuild()
  <void>ShowAboutDialog()
  <integer>GetBehaviorReason()
  <boolean>SetBehaviorReason <integer>Reason <integer>Modifiers
  <boolean>GetBehaviorUseSelection()
  <boolean>SetBehaviorUseSelection <boolean>UseSelection
  <integer>GetBehaviorPlayMode()
  <boolean>SetBehaviorPlayMode <integer>playMode
  <boolean>GetBakedFlag <node>inode
  <boolean>SetBakedFlag <node>inode <boolean>isBaked
  <matrix3 by value>GetInitialPose <node>inode
  <void>SetInitialPose <node>inode <&matrix3>initialPose
     initialPose is In and Out parameter
  <boolean>CaptureInitTransforms <&node array>nodes <boolean>useSelection
     nodes is In and Out parameter
  <boolean>ShouldViewerSync()
  <integer>GetViewerCommand()
  <integer>SetViewerCommand <integer>command
  <void>CheckViewerState()
  <void>UpdateViewerPlayback()
  <integer>GetVirtualScreenX()
  <integer>GetVirtualScreenY()
  <void>DumpContentCore <string>file <integer>Type
  <void>SetShapePerElement <boolean>shapePerElement
  <node>CreateDestruction <&node array>nodes
     nodes is In and Out parameter
  <boolean>GetExporterMode <integer>Parameter
  <boolean>SetExporterMode <integer>Parameter <boolean>onOff
  <void>ToggleBomb()
  <void>ToggleHammer()
  <void>UpdateDamageForces <float>Damage <float>Momentum <float>Radius
  <void>UpdateCCDCtrlState <node>node
  <void>SwitchSDKOnPanelData()
 Actions:

Interface: OverlappingFaces
 Properties:
  .tolerance : float : Read|Write
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: SubstManager
 Properties:
 Methods:
 Actions:

Interface: schematicviews
 Properties:
  .current : Interface : Read
 Methods:
  <Interface>getView <fpvalue>name or index
  <integer>numViews()
  <bool>open <fpvalue>name or index
  <bool>close <fpvalue>name or index
  <bool>delete <fpvalue>name or index
  <bool>isOpen <fpvalue>name or index
  <bool>isCurrent <fpvalue>name or index
  <bool>setCurrent <fpvalue>name or index
  <bool>openLastView()
 Actions:

Interface: OverlappedUVWFaces
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: ITabDialogManager
 Properties:
 Methods:
 Actions:

Interface: NitrousGraphicsManager
 Properties:
  .MakePreviewQuality : integer : Read|Write
  .MultiThreadedShaderCompileMode : bool : Read|Write
  .ChangeCursorOnMouseMove : bool : Read|Write
  .BackfaceCullWireframeEnabled : bool : Read|Write
  .ShadowmapSizeLimit : integer : Read|Write
  .NormalBumpMode : integer : Read|Write
  .BackgroundProgressiveRenderingEnabled : bool : Read|Write
 Methods:
  <bool>IsEnabled()
  <integer>API()
  <bool>IsProgressiveRenderingFinished()
  <bool>ProgressiveRendering()
  <bool>SetAppWindowSize <integer>width <integer>height
  <bool>SetAppWindowPos <integer>x <integer>y
  <bool>PinViewPanelSize <integer>width <integer>height
  <bool>UnpinViewPanelSize()
  <bool>RunMessageLoop()
  <bool>DumpMemoryInfo()
  <INT64>GetSystemMemoryUsed()
  <bool>BeginPerformanceProfiling()
  <bool>EndPerformanceProfiling()
  <bool>DumpMemoryInfoToFile <string>maxFileName <string>logFileName
  <bool>CreateDummyObjects <string>className <integer>numberOfObjects
  <bool>SetTextureSizeLimit <integer>sizeLimit <bool>enabled
  <bool>SetBackgroundTextureSizeLimit <integer>sizeLimit <bool>enabled
  <IObject>GetActiveViewportSetting()
  <IObject>GetViewportSetting <integer>index
  <IObject>GetWorldSetting()
  <bool>ApplyViewportViewSettingToLegacyView <integer>index
  <void>BeginPartialUpdateCompareTest()
  <void>EndPartialUpdateCompareTest()
  <bool>GetPartialUpdateCompareTestResult()
 Actions:

Interface: ATSOps
 Properties:
  .Visible : bool : Read|Write
  .Silent : bool : Read|Write
  .Disabled : bool : Read|Write
  .AutoLogin : bool : Read|Write
  .TreeView : bool : Read|Write
  .TableView : bool : Read|Write
  .CheckNetworkPaths : bool : Read|Write
  .DisplayExcluded : bool : Read|Write
  .ExcludeOutputFiles : bool : Read|Write
 Methods:
  <integer>NumFilesSelected()
     NumFilesSelected - no automatic redraw after invoked
  <integer>GetSelectedFiles <&filename array>FileList
     GetSelectedFiles - no automatic redraw after invoked
     FileList is Out parameter
  <integer>NumFiles()
     NumFiles - no automatic redraw after invoked
  <integer>GetFiles <&filename array>FileList
     GetFiles - no automatic redraw after invoked
     FileList is Out parameter
  <integer>GetDependentFiles <filename>Filename <bool>Recurse <&filename array>FileList IncludeOutputFiles:<bool>
     GetDependentFiles - no automatic redraw after invoked
     FileList is Out parameter
     IncludeOutputFiles default value: true
  <bool>IsInputFile <filename>Filename
     IsInputFile - no automatic redraw after invoked
  <void>SelectFiles <&filename array>FileList
     SelectFiles - no automatic redraw after invoked
     FileList is In parameter
  <void>ClearSelection()
     ClearSelection - no automatic redraw after invoked
  <void>Refresh()
     Refresh - no automatic redraw after invoked
  <void>ShowPromptsDialog()
     ShowPromptsDialog - no automatic redraw after invoked
  <void>ShowWorkingCommentDialog()
     ShowWorkingCommentDialog - no automatic redraw after invoked
  <void>ShowStatusLogDialog()
     ShowStatusLogDialog - no automatic redraw after invoked
  <integer>NumProviders()
     NumProviders - no automatic redraw after invoked
  <string>GetProviderName <index>ProviderIndex
     GetProviderName - no automatic redraw after invoked
  <index>GetActiveProvider()
     GetActiveProvider - no automatic redraw after invoked
  <void>SetActiveProvider <index>ProviderIndex
     SetActiveProvider - no automatic redraw after invoked
  <void>Login <index>ProviderIndex
     Login - no automatic redraw after invoked
  <void>Logout <index>ProviderIndex
     Logout - no automatic redraw after invoked
  <void>OpenProject <index>ProviderIndex <filename>ProjectPath
     OpenProject - no automatic redraw after invoked
  <void>CloseProject <index>ProviderIndex
     CloseProject - no automatic redraw after invoked
  <void>SetWorkingFolder <index>ProviderIndex <filename>Folder
     SetWorkingFolder - no automatic redraw after invoked
  <filename>GetWorkingFolder <index>ProviderIndex
     GetWorkingFolder - no automatic redraw after invoked
  <bool>IsFileExcluded <index>ProviderIndex <filename>Filename
     IsFileExcluded - no automatic redraw after invoked
  <bool>IsFileShareLocked <index>ProviderIndex <filename>Filename
     IsFileShareLocked - no automatic redraw after invoked
  <bool>IsInitialized <index>ProviderIndex
     IsInitialized - no automatic redraw after invoked
  <bool>IsProjectOpen <index>ProviderIndex
     IsProjectOpen - no automatic redraw after invoked
  <void>LaunchOptions <index>ProviderIndex
     LaunchOptions - no automatic redraw after invoked
  <void>LaunchProvider <index>ProviderIndex
     LaunchProvider - no automatic redraw after invoked
  <void>OpenFromVault VaultVersion:<integer>
     OpenFromVault - no automatic redraw after invoked
     VaultVersion default value: -1
  <void>GetFromProvider <index>ProviderIndex <string>FilterName <string>FilterExtensions <bool>AddAllFilesFilter <bool>MultiSelect <bool>Download <&filename array>FileList
     GetFromProvider - no automatic redraw after invoked
     FileList is Out parameter
  <bool>TestFileStatus <index>ProviderIndex <filename>Filename <enum>Status
     TestFileStatus - no automatic redraw after invoked
     Status enums: {#Unknown|#NotControlled|#Controlled|#CheckedOut|#CheckedOutOther|#OutOfDate|#Deleted|#Missing|#Modified|#Hidden|#ShareLock|#CanCheckin|#CanCheckout|#CanUndoCheckout|#CanGetLatest|#CanAddFile|#CanShowHistory|#CanShowProperties}
  <value>GetFileStatus <index>ProviderIndex <filename>Filename
     GetFileStatus - no automatic redraw after invoked
  <void>GetFilesByStatus <index>ProviderIndex <enum>Status <&filename array>FileList
     GetFilesByStatus - no automatic redraw after invoked
     Status enums: {#Unknown|#NotControlled|#Controlled|#CheckedOut|#CheckedOutOther|#OutOfDate|#Deleted|#Missing|#Modified|#Hidden|#ShareLock|#CanCheckin|#CanCheckout|#CanUndoCheckout|#CanGetLatest|#CanAddFile|#CanShowHistory|#CanShowProperties}
     FileList is Out parameter
  <integer>GetFilesByFileSystemStatus <enum>Status <&filename array>FileList
     GetFilesByFileSystemStatus - no automatic redraw after invoked
     Status enums: {#Unknown|#Ok|#Missing|#Found|#NetworkPath}
     FileList is Out parameter
  <bool>TestFileSystemStatus <filename>Filename <enum>Status
     TestFileSystemStatus - no automatic redraw after invoked
     Status enums: {#Unknown|#Ok|#Missing|#Found|#NetworkPath}
  <value>GetFileSystemStatus <filename>Filename
     GetFileSystemStatus - no automatic redraw after invoked
  <integer>GetResolvedPaths <&filename array>FileList <&filename array>ResolvedFileList
     GetResolvedPaths - no automatic redraw after invoked
     FileList is In parameter
     ResolvedFileList is Out parameter
  <integer>GetDependencyFileList <maxObject>Dependent <&filename array>FileList <bool>includeRefHierarchy
     GetDependencyFileList - no automatic redraw after invoked
     FileList is Out parameter
  <bool>Checkin <index>ProviderIndex <&filename array>FileList <&TSTR>Comment
     Checkin - no automatic redraw after invoked
     FileList is In parameter
     Comment is In and Out parameter
  <bool>Checkout <index>ProviderIndex <&filename array>FileList <&TSTR>Comment
     Checkout - no automatic redraw after invoked
     FileList is In parameter
     Comment is In and Out parameter
  <bool>UndoCheckout <index>ProviderIndex <&filename array>FileList
     UndoCheckout - no automatic redraw after invoked
     FileList is In parameter
  <bool>GetLatest <index>ProviderIndex <&filename array>FileList
     GetLatest - no automatic redraw after invoked
     FileList is In parameter
  <integer>GetMinVersion <index>ProviderIndex <filename>Filename
     GetMinVersion - no automatic redraw after invoked
  <integer>GetMaxVersion <index>ProviderIndex <filename>Filename
     GetMaxVersion - no automatic redraw after invoked
  <bool>GetVersion <index>ProviderIndex <filename>Filename <integer>VersionNumber
     GetVersion - no automatic redraw after invoked
  <bool>AddFiles <index>ProviderIndex <&filename array>FileList <&TSTR>Comment IsHidden:<&bool array>
     AddFiles - no automatic redraw after invoked
     FileList is In parameter
     Comment is In and Out parameter
     IsHidden default value: #()
     IsHidden is In parameter
  <void>Properties <index>ProviderIndex <&filename array>FileList
     Properties - no automatic redraw after invoked
     FileList is In parameter
  <void>ShowHistory <index>ProviderIndex <&filename array>FileList
     ShowHistory - no automatic redraw after invoked
     FileList is In parameter
  <bool>CanCheckin()
     CanCheckin - no automatic redraw after invoked
  <bool>CanCheckout()
     CanCheckout - no automatic redraw after invoked
  <bool>CanUndoCheckout()
     CanUndoCheckout - no automatic redraw after invoked
  <bool>CanGetLatest()
     CanGetLatest - no automatic redraw after invoked
  <bool>CanAddFiles()
     CanAddFiles - no automatic redraw after invoked
  <bool>CanProperties()
     CanProperties - no automatic redraw after invoked
  <bool>CanShowHistory()
     CanShowHistory - no automatic redraw after invoked
  <bool>CanGetFromProvider <index>ProviderIndex
     CanGetFromProvider - no automatic redraw after invoked
  <void>CheckForDependentFiles <index>ProviderIndex <filename>Filename
     CheckForDependentFiles - no automatic redraw after invoked
  <void>CheckForCheckedOutFiles <index>ProviderIndex
     CheckForCheckedOutFiles - no automatic redraw after invoked
  <void>CheckForUnControlledFiles <index>ProviderIndex
     CheckForUnControlledFiles - no automatic redraw after invoked
  <void>CheckForOutDatedFiles <index>ProviderIndex
     CheckForOutDatedFiles - no automatic redraw after invoked
  <void>CheckForSceneFileCheckOut <index>ProviderIndex
     CheckForSceneFileCheckOut - no automatic redraw after invoked
  <void>SetWorkingComment <string>Comment
     SetWorkingComment - no automatic redraw after invoked
  <string>GetWorkingComment()
     GetWorkingComment - no automatic redraw after invoked
  <void>AppendStatusLog <string>Status
     AppendStatusLog - no automatic redraw after invoked
  <void>ClearStatusLog()
     ClearStatusLog - no automatic redraw after invoked
  <string>GetStatusLog()
     GetStatusLog - no automatic redraw after invoked
  <bool>RegisterNotification <value>Callback <integer>ID
     RegisterNotification - no automatic redraw after invoked
  <void>UnRegisterNotification <integer>ID
     UnRegisterNotification - no automatic redraw after invoked
  <enum>GetNotificationID()
     GetNotificationID enums: {#NotifyPreLogin|#NotifyPostLogin|#NotifyPreLogout|#NotifyPostLogout|#NotifyPreOpenProject|#NotifyPostOpenProject|#NotifyPreCloseProject|#NotifyPostCloseProject|#NotifyPreLaunchOptions|#NotifyPostLaunchOptions|#NotifyPreLaunchProvider|#NotifyPostLaunchProvider|#NotifyPreCheckin|#NotifyPostCheckin|#NotifyPreCheckout|#NotifyPostCheckout|#NotifyPreUndoCheckout|#NotifyPostUndoCheckout|#NotifyPreAddFiles|#NotifyPostAddFiles|#NotifyPreGetLatest|#NotifyPostGetLatest|#NotifyPreProperties|#NotifyPostProperties|#NotifyPreShowHistory|#NotifyPostShowHistory|#NotifyFileListUpdate|#NotifyPreExploreProvider|#NotifyPostExploreProvider|#NotifyPreGetVersion|#NotifyPostGetVersion
     GetNotificationID - no automatic redraw after invoked
  <index>GetNotificationProviderIndex()
     GetNotificationProviderIndex - no automatic redraw after invoked
  <integer>GetNotificationFileList <&filename array>FileList
     GetNotificationFileList - no automatic redraw after invoked
     FileList is Out parameter
  <bool>AddAttachmentToNotificationFileListEntry <index>FileListIndex <filename>Filename
     AddAttachmentToNotificationFileListEntry - no automatic redraw after invoked
  <bool>IsNotificationCancelled()
     IsNotificationCancelled - no automatic redraw after invoked
  <bool>AddFileToNotificationFileList <filename>Filename
     AddFileToNotificationFileList - no automatic redraw after invoked
  <bool>RemoveFileFromNotificationFileList <index>FileListIndex
     RemoveFileFromNotificationFileList - no automatic redraw after invoked
  <bool>SetPathOnSelection <filename>NewPath CreateOutputFolder:<bool>
     CreateOutputFolder default value: false
  <bool>RetargetCommonRootOfSelection <filename>NewPath CreateOutputFolder:<bool>
     CreateOutputFolder default value: false
  <bool>RetargetSelection <filename>NewPath CreateOutputFolder:<bool>
     CreateOutputFolder default value: false
  <bool>SetPath <filename>NewPath CreateOutputFolder:<bool>
     CreateOutputFolder default value: false
  <bool>RetargetCommonRoot <filename>NewPath CreateOutputFolder:<bool>
     CreateOutputFolder default value: false
  <bool>RetargetAssets <&maxObject>AssetOwner <filename>OldPath <filename>NewPath CreateOutputFolder:<bool>
     AssetOwner is In parameter
     CreateOutputFolder default value: false
  <bool>ResolveSelectionToUNC()
  <bool>ResolveSelectionRelativeToProjectFolder()
  <bool>ResolveSelectionToAbsolute()
 Actions:

Interface: objXRefMgr
 Properties:
  .recordCount : DWORD : Read
  .dupObjNameAction : enum : Read|Write
     dupObjNameAction enums: {#prompt|#xref|#skip|#deleteOld|#autoRename}
  .dupMtlNameAction : enum : Read|Write
     dupMtlNameAction enums: {#prompt|#useXRefed|#useScene|#autoRename}
  .mergeTransforms : bool : Read|Write
  .mergeMaterials : bool : Read|Write
  .mergeManipulators : bool : Read|Write
  .mergeModifiers : enum : Read|Write
     mergeModifiers enums: {#xrefModifiers|#ignoreModifiers|#mergeModifiers}
  .mergeTransforms : bool : Read|Write
  .getAutoUpdate : bool : Read|Write
 Methods:
  <Interface>GetRecord <index>index
  <Interface>FindRecord <DWORD>handle
  <bool>RemoveRecordFromScene <Interface>record
     record Validated by Validator function
  <bool>MergeRecordIntoScene <Interface>record
     record Validated by Validator function
  <bool>SetRecordSrcFile <Interface>xrefRecord <filename>fileName
  <bool>UpdateAllRecords()
  <bool>SetXRefItemSrcName <&maxObject>xrefItem <string>itemName
     xrefItem is In parameter
  <bool>SetProxyItemSrcName <&maxObject>proxyItem <string>itemName
     proxyItem is In parameter
  <bool>SetXRefItemSrcFile <&maxObject>xrefItem <filename>fileName
     xrefItem is In parameter
  <bool>SetProxyItemSrcFile <&maxObject>proxyItem <filename>fileName
     proxyItem is In parameter
  <bool>AddXRefItemsToRecord <Interface>record promptObjNames:<bool> objNames:<string array>
     record Validated by Validator function
     promptObjNames default value: false
     objNames default value: #()
  <Interface>AddXRefItemsFromFile <filename>fileName promptObjNames:<bool> objNames:<string array> xrefOptions:<&enum array>
     promptObjNames default value: false
     objNames default value: #()
     xrefOptions enums: {#asProxy|#xrefModifiers|#dropModifiers|#mergeModifiers|#mergeManipulators|#selectNodes|#mergeControllers|#mergeMaterials}
     xrefOptions default value: #()
     xrefOptions is In parameter
  <bool>CanCombineRecords <Interface>firstRecord <Interface>secondRecord
     firstRecord Validated by Validator function
     secondRecord Validated by Validator function
  <Interface>CombineRecords <&Interface array>records
     records Validated by Validator function
     records is In parameter
  <bool>RemoveXRefItemsFromScene <&maxObject array>xrefItems
     xrefItems is In parameter
  <bool>MergeXRefItemsIntoScene <&maxObject array>xrefItems
     xrefItems is In parameter
  <void>ApplyXRefMaterialsToXRefObjects <&maxObject array>objectXRefItems
     objectXRefItems is In parameter
  <Interface>IsNodeXRefed <node>node
  <void>ApplyXRefControllersToXRefObjects <&maxObject array>objectXRefItems
     objectXRefItems is In parameter
  <boolean>ResetXRefControllersPRSOffset <&maxObject array>xrefItems
     xrefItems is In parameter
  <boolean>CanResetXRefControllersPRSOffset <&maxObject>xrefItem
     xrefItem is In parameter
 Actions:

Interface: DisplayManager
 Properties:
 Methods:
  <bool>IsEnabled()
 Actions:

Interface: actionMan
 Properties:
  .numActionTables : integer : Read
 Methods:
  <boolean>executeAction <integer>tableId <string>persistentId
  <boolean>loadKeyboardFile <filename>file
  <boolean>saveKeyboardFile <filename>file
  <filename>getKeyboardFile()
  <Interface>getActionTable <index>index
     getActionTable - no automatic redraw after invoked
 Actions:

Interface: simpleFaceManager
 Properties:
 Methods:
  <Interface>addChannel <object>object type:<enum> id:<DWORD array> name:<string>
     object Validated by Validator function
     type enums: {#integer|#index|#float|#boolean|#point2|#point3}
     type default value: #integer
     id default value: #()
     id Validated by Validator function
     name default value: undefined
  <void>removeChannel <object>object <DWORD array>id
     id Validated by Validator function
  <Interface>getChannel <object>object <DWORD array>id
     object Validated by Validator function
     id Validated by Validator function
  <Interface by value array>getChannels <object>object
     object Validated by Validator function
 Actions:

Interface: radiosityMeshOps
 Properties:
 Methods:
  <mesh by value>getRadiosityMesh <node>radiosity_Node
  <boolean>isRadiosityValid()
  <boolean>isNodeInSolution <node>radiosity_Node
 Actions:

Interface: assemblyMgr
 Properties:
 Methods:
  <node>Assemble <node array>nodes name:<string> classDesc:<class> select:<bool>
     name default value: undefined
     classDesc default value: undefined
     select default value: true
  <bool>Disassemble <node array>nodes
  <bool>Open <node array>nodes clearSelection:<bool>
     clearSelection default value: true
  <bool>Close <node array>nodes select:<bool>
     select default value: true
  <bool>Explode <node array>nodes
  <bool>Attach <node array>nodes assembly:<node>
     assembly default value: undefined
  <bool>Detach <node array>nodes
  <bool>CanAssemble <node array>nodes
  <bool>CanDisassemble <node array>nodes
  <bool>CanExplode <node array>nodes
  <bool>CanOpen <node array>nodes
  <bool>CanClose <node array>nodes
  <bool>CanAttach <node array>nodes assembly:<node>
     assembly default value: undefined
  <bool>CanDetach <node array>nodes
  <node>IsAssembly <node array>nodes
  <bool>FilterAssembly <node>assemblyHead <value>filterSClassID <&node array>filteredNodes
     filteredNodes is Out parameter
 Actions:

Interface: PerezAllWeather
 Properties:
 Methods:
 Actions:

Interface: ViewCubeOps
 Properties:
  .All3DViewportsDisplay : bool : Read|Write
  .Visibility : bool : Read|Write
  .DragSnapping : bool : Read|Write
  .FitToView : bool : Read|Write
  .AnimatedTransition : bool : Read|Write
  .KeepSceneUp : bool : Read|Write
  .DrawCompass : bool : Read|Write
  .MinOpacity : float : Read|Write
  .AngleOfNorth : float : Read|Write
  .Size : integer : Read|Write
 Methods:
  <void>GoHome()
     GoHome - no automatic redraw after invoked
  <void>SetCurrentViewAsHome()
     SetCurrentViewAsHome - no automatic redraw after invoked
  <void>SetCurrentViewAsFront()
     SetCurrentViewAsFront - no automatic redraw after invoked
  <void>Orthographic()
     Orthographic - no automatic redraw after invoked
  <void>Perspective()
     Perspective - no automatic redraw after invoked
  <void>ResetFront()
     ResetFront - no automatic redraw after invoked
  <void>SaveOptions()
     SaveOptions - no automatic redraw after invoked
 Actions:

Interface: SteeringWheelsOps
 Properties:
  .IsActive : bool : Read|Write
  .PreserveSceneUp : bool : Read|Write
  .IncrementalZoom : bool : Read|Write
  .SpeedFactor : double : Read|Write
  .InvertVerticalAxis : bool : Read|Write
  .ShowHUDMessages : bool : Read|Write
  .ShowToolTips : bool : Read|Write
  .MiniWheelOpacityFactor : double : Read|Write
  .LargeWheelOpacityFactor : double : Read|Write
  .MiniWheelSize : integer : Read|Write
  .LargeWheelSize : integer : Read|Write
  .AlwaysShowWelcome : bool : Read|Write
  .HaveShownWelcome : bool : Read|Write
  .SelectionSensitivity : bool : Read|Write
  .ConstrainWalk : bool : Read|Write
 Methods:
  <void>StartSteeringWheelMode()
     StartSteeringWheelMode - no automatic redraw after invoked
  <void>StopSteeringWheelMode()
     StopSteeringWheelMode - no automatic redraw after invoked
  <void>MiniViewObjectWheel()
     MiniViewObjectWheel - no automatic redraw after invoked
  <void>MiniTourBuildingWheel()
     MiniTourBuildingWheel - no automatic redraw after invoked
  <void>MiniFullNavWheel()
     MiniFullNavWheel - no automatic redraw after invoked
  <void>FullNavWheel()
     FullNavWheel - no automatic redraw after invoked
  <void>ViewObjectWheel()
     ViewObjectWheel - no automatic redraw after invoked
  <void>TourBuildingWheel()
     TourBuildingWheel - no automatic redraw after invoked
  <void>IncreaseWalkSpeed()
     IncreaseWalkSpeed - no automatic redraw after invoked
  <void>DecreaseWalkSpeed()
     DecreaseWalkSpeed - no automatic redraw after invoked
  <void>RestoreCenter()
     RestoreCenter - no automatic redraw after invoked
  <void>SaveOptions()
     SaveOptions - no automatic redraw after invoked
  <void>ClearRewindHistory()
     ClearRewindHistory - no automatic redraw after invoked
 Actions:

Interface: defaultActions
 Properties:
 Methods:
  <boolean>getAction <enum>eventID <&enum array>action
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
     action enums: {#logToFile|#logmsg|#abort}
     action is Out parameter
  <boolean>setAction <enum>eventID <&enum array>action title:<string> oldAction:<&enum array>
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
     action enums: {#logToFile|#logmsg|#abort}
     action is In parameter
     title default value: undefined
     oldAction enums: {#logToFile|#logmsg|#abort}
     oldAction default value: #()
     oldAction is Out parameter
  <boolean>deleteAction <enum>eventID
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <integer>getActionCount()
  <TSTR by value>getActionTitle <enum>eventID
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <TSTR by value>getActionTitleByIndex <index>index
  <enum>getActionIDByIndex <index>index
     getActionIDByIndex enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles
  <boolean>logEntry <enum>eventID <string>message
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <void>MsgLogClear <enum>eventID
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <integer>getMsgLogCount <enum>eventID
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <TSTR by value>getMsgLogMsg <enum>eventID <index>index
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <TSTR by value array>getMsgLogMsgs <enum>eventID
     eventID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles}
  <enum>getMsgLogID <index>index
     getMsgLogID enums: {#missingExtFiles|#missingDLLs|#missingXRefs|#missingUVW|#unsupportedRendereffect|#invalidXRefFiles
  <integer>setMsgLogMaxCount <integer>count
 Actions:

Interface: LockedComponentsMan
 Properties:
 Methods:
 Actions:

Interface: gridPrefs
 Properties:
  .spacing : float : Read|Write
  .majorLines : integer : Read|Write
  .perspViewGridExtents : integer : Read|Write
  .inhibitGridSubdivision : boolean : Read|Write
  .inhibitPerspViewGridResize : boolean : Read|Write
  .dynamicUpdateAllVpts : boolean : Read|Write
 Methods:
 Actions:

Interface: FileLinkMgr
 Properties:
  .numLinks : integer : Read
 Methods:
  <bool>Attach <&TSTR>filename fileformat:<enum> showUI:<bool>
     filename is In parameter
     fileformat enums: {#UseFileExt|#DWG|#DXF}
     fileformat default value: #UseFileExt
     showUI default value: false
  <bool>AttachWithPreset <&TSTR>filename <&TSTR>preset showUI:<bool>
     filename is In parameter
     preset is In parameter
     showUI default value: false
  <bool>Reload <integer>which showUI:<bool> translateMaterials:<bool>
     showUI default value: false
     translateMaterials default value: true
  <bool>Detach <integer>which
  <bool>Bind <integer>which
  <bool>IsAnyLinked <&node array>nodes
     nodes is In parameter
  <bool>ChangeFilename <integer>which <&TSTR>filename
     filename is In parameter
  <bool>SelectNodes <integer>which clearCurrentSel:<bool>
     clearCurrentSel default value: true
  <bool>IsNodeLinked <node>node
  <integer>GetRecord <node>node
  <IObject>GetRecordFile <integer>which
     which Validated by Range: 0 to 0
     which Validated by Validator function
  <void>SetDefaultView <&TSTR>viewName
     viewName is In parameter
 Actions:

Interface: BatchProOptimizer
 Properties:
  .SourceFileMode : integer : Read|Write
  .SourceFileFiles : filename by value array : Read|Write
  .SourceFileDir : string : Read|Write
  .SourceFileSubDir : bool : Read|Write
  .OptimizationLevel1 : integer : Read|Write
  .OptimizationLevel2 : integer : Read|Write
  .OptimizationLevel3 : integer : Read|Write
  .OptimizationLevel4 : integer : Read|Write
  .OptimizationLevel5 : integer : Read|Write
  .OptimizationLevelSteps : integer : Read|Write
  .OptimizationLevelMode : integer : Read|Write
  .OptimizeBordersMode : integer : Read|Write
  .OptimizeHidden : bool : Read|Write
  .MergePoints : bool : Read|Write
  .MergePointsThreshold : float : Read|Write
  .MergeFaces : bool : Read|Write
  .MergeFacesThreshold : float : Read|Write
  .KeepMaterialBoundaries : bool : Read|Write
  .CompactFaces : bool : Read|Write
  .PreventFlippedNormals : bool : Read|Write
  .KeepVertexColors : bool : Read|Write
  .KeepVertexColorsBoundaries : bool : Read|Write
  .VertexColorsTolerance : integer : Read|Write
  .KeepTexture : bool : Read|Write
  .KeepUVBoundaries : bool : Read|Write
  .UVTolerance : float : Read|Write
  .KeepNormals : bool : Read|Write
  .NormalMode : integer : Read|Write
  .NormalThreshold : float : Read|Write
  .SymmetryMode : integer : Read|Write
  .SymmetryTolerance : integer : Read|Write
  .DestFileNameMode : integer : Read|Write
  .AutoRename : bool : Read|Write
  .DestFileNamePrefix : string : Read|Write
  .DestFileNameSuffix : string : Read|Write
  .DestFolderMode : integer : Read|Write
  .DestFolderName : string : Read|Write
  .RecreateFolderTree : bool : Read|Write
  .DestFormatMode : integer : Read|Write
  .DestFormatExt : string : Read|Write
  .LogFilePath : string : Read|Write
  .ApplyModifier : boolean : Read|Write
  .ValidateDialogs : boolean : Read|Write
 Methods:
  <void>batch()
 Actions:

Interface: NetRender
 Properties:
 Methods:
  <Interface>GetManager()
 Actions:

Interface: MainThreadExecuteRequestManager
 Properties:
 Methods:
 Actions:

Interface: globalDXDisplayManager
 Properties:
  .forceSoftware : boolean : Read|Write
  .forceSelected : boolean : Read|Write
  .sceneEffectActive : boolean : Read|Write
 Methods:
  <boolean>isDXActive()
 Actions:

Interface: iParserLoader
 Properties:
 Methods:
 Actions:

Interface: BoneSys
 Properties:
 Methods:
  <node>createBone <point3>startPos <point3>endPos <point3>zAxis
  <boolean>refineBone()
 Actions:

Interface: heightManager
 Properties:
 Methods:
  <void>customizeHeights()
  <void>setCurrentHeightIndex <index>index
     index Validated by Validator function
  <float>getHeight <index>index
     index Validated by Validator function
  <integer>getCurrentHeightIndex()
  <float>getNumHeights()
  <string>getHeightString <index>index
     index Validated by Validator function
 Actions:

Interface: pftParticleView
 Properties:
 Methods:
  <bool>redraw()
 Actions:

Interface: ActionItemOverrideManager
 Properties:
  .overridesActive : boolean : Read|Write
  .timeToStartOverride : float : Read|Write
 Methods:
 Actions:

Interface: SceneMissingPlugIns
 Properties:
 Methods:
  <integer>GetMissingPlugInCount()
  <string>GetMissingPlugInClassName <index>Index
  <string>GetMissingPlugInFileName <index>Index
  <string>GetMissingPlugInDescription <index>Index
 Actions:

Interface: IMetaDataManager
 Properties:
 Methods:
 Actions:

Interface: TVerts
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: MtlBrowserFilter_Manager
 Properties:
 Methods:
 Actions:

Interface: InstanceMgr
 Properties:
  .autoMtlPropagation : boolean : Read|Write
 Methods:
  <DWORD>GetInstances <node>source <&node array>instances
     instances is Out parameter
  <DWORD>SetMtlOnInstances <node>source <material>newMtl
  <bool>MakeObjectsUnique <&node array>nodes <enum>multiNodeOption
     nodes is In parameter
     multiNodeOption enums: {#prompt|#individual|#group}
  <bool>CanMakeObjectsUnique <&node array>nodes
     nodes is In parameter
  <bool>MakeModifiersUnique <&node array>nodes <&maxObject array>modifiers <enum>multiNodeOption
     nodes is In parameter
     modifiers is In parameter
     multiNodeOption enums: {#prompt|#individual|#group}
  <bool>CanMakeModifiersUnique <&node array>nodes <&maxObject array>modifiers
     nodes is In parameter
     modifiers is In parameter
  <bool>MakeControllersUnique <&node array>nodes <&maxObject array>controllers <enum>multiNodeOption
     nodes is In parameter
     controllers is In parameter
     multiNodeOption enums: {#prompt|#individual|#group}
  <bool>CanMakeControllersUnique <&node array>nodes <&maxObject array>controllers
     nodes is In parameter
     controllers is In parameter
 Actions:

Interface: SceneRadiosity
 Properties:
  .radiosity : value : Read|Write|Validated by Validator function
 Methods:
  <void>showPanel()
  <void>closePanel()
  <void>minimizePanel()
 Actions:

Interface: RadiosityPreferences
 Properties:
  .autoProcessObjectRefine : boolean : Read|Write
  .displayReflectanceInMEditor : boolean : Read|Write
  .displayInViewport : boolean : Read|Write
  .displayResetWarning : boolean : Read|Write
  .updateDataWhenRequiredOnStart : boolean : Read|Write
  .saveScene : boolean : Read|Write
  .useRadiosity : boolean : Read|Write
  .computeRadiosity : boolean : Read|Write
  .useAdvancedLighting : boolean : Read|Write
  .computeAdvancedLighting : boolean : Read|Write
 Methods:
 Actions:

Interface: UIAccessor
 Properties:
 Methods:
  <string>GetWindowText <HWND>hwnd
     GetWindowText - no automatic redraw after invoked
  <string>GetWindowClassName <HWND>hwnd
     GetWindowClassName - no automatic redraw after invoked
  <integer>GetWindowResourceID <HWND>hwnd
     GetWindowResourceID - no automatic redraw after invoked
  <HWND by value array>GetChildWindows <HWND>hwnd
     GetChildWindows - no automatic redraw after invoked
  <HWND by value array>GetPopupDialogs()
     GetPopupDialogs - no automatic redraw after invoked
  <HWND>GetParentWindow <HWND>hwnd
     GetParentWindow - no automatic redraw after invoked
  <HWND>GetFirstChildWindow <HWND>hwnd
     GetFirstChildWindow - no automatic redraw after invoked
  <HWND>GetPrevWindow <HWND>hwnd
     GetPrevWindow - no automatic redraw after invoked
  <HWND>GetNextWindow <HWND>hwnd
     GetNextWindow - no automatic redraw after invoked
  <bool>IsWindow <HWND>hwnd
     IsWindow - no automatic redraw after invoked
  <string>GetWindowDllFileName <HWND>hwnd
     GetWindowDllFileName - no automatic redraw after invoked
  <string>GetWindowDllDescription <HWND>hwnd
     GetWindowDllDescription - no automatic redraw after invoked
  <void>CloseDialog <HWND>hwnd
     CloseDialog - no automatic redraw after invoked
  <void>PressDefaultButton()
     PressDefaultButton - no automatic redraw after invoked
  <void>PressButton <HWND>hwnd
     PressButton - no automatic redraw after invoked
  <bool>PressButtonByName <HWND>hwnd <string>name
     PressButtonByName - no automatic redraw after invoked
  <bool>SetWindowText <HWND>hwnd <string>text
     SetWindowText - no automatic redraw after invoked
  <bool>SendMessageID <HWND>hwndDlg <enum>ID
     SendMessageID - no automatic redraw after invoked
     ID enums: {#IDOK|#IDCANCEL|#IDABORT|#IDRETRY|#IDIGNORE|#IDYES|#IDNO|#IDCLOSE}
  <bool>SendMessage <HWND>hwndDlg <integer>MessageID <integer>wParam <integer>lParam
     SendMessage - no automatic redraw after invoked
 Actions:

Interface: SceneExplorerManager
 Properties:
 Methods:
  <void>AddProperty <string>propertyName <value>getFunction <value>setFunction
     AddProperty - no automatic redraw after invoked
  <void>AddReadOnlyProperty <string>propertyName <value>getFunction
     AddReadOnlyProperty - no automatic redraw after invoked
  <void>RemoveProperty <string>propertyName
     RemoveProperty - no automatic redraw after invoked
  <integer>GetExplorerCount()
     GetExplorerCount - no automatic redraw after invoked
  <TSTR by value>GetExplorerName <index>explorerIndex
     GetExplorerName - no automatic redraw after invoked
  <boolean>ExplorerExists <&TSTR>explorerName
     ExplorerExists - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>ExplorerIsOpen <&TSTR>explorerName
     ExplorerIsOpen - no automatic redraw after invoked
     explorerName is In parameter
  <bool>CreateADefaultExplorer <&TSTR>explorerName
     CreateADefaultExplorer - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>OpenExplorer <&TSTR>explorerName
     OpenExplorer - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>CloseExplorer <&TSTR>explorerName
     CloseExplorer - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>DeleteExplorer <&TSTR>explorerName
     DeleteExplorer - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>RenameExplorer <&TSTR>oldExplorerName <&TSTR>newExplorerName
     RenameExplorer - no automatic redraw after invoked
     oldExplorerName is In parameter
     newExplorerName is In parameter
  <boolean>ClearAllExplorers()
     ClearAllExplorers - no automatic redraw after invoked
  <void>SortExplorerByColumnFieldName <string>explorerName <string>fieldName <boolean>ascending
     SortExplorerByColumnFieldName - no automatic redraw after invoked
  <void>SortExplorerByColumnCaption <string>explorerName <string>caption <boolean>ascending
     SortExplorerByColumnCaption - no automatic redraw after invoked
  <point2 by value>GetExplorerPosition <&TSTR>explorerName
     GetExplorerPosition - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>SetExplorerPosition <&TSTR>explorerName <point2 by value>position
     SetExplorerPosition - no automatic redraw after invoked
     explorerName is In parameter
  <point2 by value>GetExplorerSize <&TSTR>explorerName
     GetExplorerSize - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>SetExplorerSize <&TSTR>explorerName <point2 by value>size
     SetExplorerSize - no automatic redraw after invoked
     explorerName is In parameter
  <boolean>ConfigureExplorer <&TSTR>explorerName <&TSTR>configurationFile
     ConfigureExplorer - no automatic redraw after invoked
     explorerName is In parameter
     configurationFile is In parameter
  <boolean>LoadExplorerConfiguration <&TSTR>configurationFile
     LoadExplorerConfiguration - no automatic redraw after invoked
     configurationFile is In parameter
  <boolean>SaveExplorerConfiguration <&TSTR>explorerName <&TSTR>outputConfigurationFile
     SaveExplorerConfiguration - no automatic redraw after invoked
     explorerName is In parameter
     outputConfigurationFile is In parameter
  <void>OpenManageInstancesDialog()
     OpenManageInstancesDialog - no automatic redraw after invoked
  <void>CloseManageInstancesDialog()
     CloseManageInstancesDialog - no automatic redraw after invoked
  <void>AddLocalizableProperty <string>propertyName <string>displayName <value>getFunction <value>setFunction
     AddLocalizableProperty - no automatic redraw after invoked
  <void>AddLocalizableReadOnlyProperty <string>propertyName <string>displayName <value>getFunction
     AddLocalizableReadOnlyProperty - no automatic redraw after invoked
  <void>CreateExplorer <string>explorerName <value>visibleColumns
     CreateExplorer - no automatic redraw after invoked
  <bool>SetExplorerVisibleColumns <string>explorerName <value>visibleColumns
     SetExplorerVisibleColumns - no automatic redraw after invoked
  <bool>GetExplorerVisibleColumns <string>explorerName <&TSTR array>visibleColumns
     GetExplorerVisibleColumns - no automatic redraw after invoked
     visibleColumns is In and Out parameter
 Actions:

Interface: IsolateSelection
 Properties:
  .ZoomExtents : boolean : Read|Write
 Methods:
  <boolean>EnterIsolateSelectionMode()
  <boolean>ExitIsolateSelectionMode()
  <boolean>IsolateSelectionModeActive()
  <boolean>IsNodeIsolated <node>node
  <void>SuppressIsolateSelectionWarningDialogue <boolean>bSuppress
 Actions:

Interface: nvpxConsts
 Properties:
  .PX_RBTYPE_DYNAMIC : integer : Read
  .PX_RBTYPE_KINEMATIC : integer : Read
  .PX_RBTYPE_STATIC : integer : Read
  .PX_SHAPE_SPHERE : integer : Read
  .PX_SHAPE_BOX : integer : Read
  .PX_SHAPE_CAPSULE : integer : Read
  .PX_SHAPE_CONVEX : integer : Read
  .PX_SHAPE_ORIGINAL : integer : Read
  .PX_SHAPE_CUSTOM : integer : Read
  .PX_SHAPE_COMPOSITE : integer : Read
  .PX_DOF_LOCKED : integer : Read
  .PX_DOF_LIMITED : integer : Read
  .PX_DOF_FREE : integer : Read
  .PX_SIM_DISABLED : integer : Read
  .PX_SIM_PREPARING : integer : Read
  .PX_SIM_RUNNING : integer : Read
  .PX_SIM_REWINDING : integer : Read
  .PX_HOST_PLAYBACK : integer : Read
  .PX_HOST_BAKE : integer : Read
  .PX_HOST_UNBAKE : integer : Read
  .PX_HOST_EXPORT : integer : Read
  .PX_HOST_SETTLE : integer : Read
  .PX_HOST_MODIFIER_CANCEL : integer : Read
  .PX_HOST_MODIFIER_SELECTED : integer : Read
  .PX_CONSTRAINT_RIGID : integer : Read
  .PX_CONSTRAINT_SLIDE : integer : Read
  .PX_CONSTRAINT_HINGE : integer : Read
  .PX_CONSTRAINT_TWIST : integer : Read
  .PX_CONSTRAINT_UNIV : integer : Read
  .PX_CONSTRAINT_BALLSOCK : integer : Read
  .PX_CONSTRAINT_GEAR : integer : Read
  .PX_ONLASTFRAME_CONTINUE : integer : Read
  .PX_ONLASTFRAME_STOP : integer : Read
  .PX_ONLASTFRAME_LOOP : integer : Read
  .PX_LOOP_RESET : integer : Read
  .PX_LOOP_CONTINUE : integer : Read
  .PX_ACTORTYPE_DYNAMIC : integer : Read
  .PX_ACTORTYPE_KINEMATIC : integer : Read
  .PX_ACTORTYPE_STATIC : integer : Read
  .PX_ACTORTYPE_RB_OVER : integer : Read
  .PX_ACTORTYPE_UNDEFINED : integer : Read
  .PX_ACTORTYPE_CLOTH : integer : Read
  .PX_ACTORTYPE_SOFTBODY : integer : Read
  .PX_ACTORTYPE_FORCEFIELD : integer : Read
  .PX_ACTORTYPE_FLUID : integer : Read
  .PX_ACTORTYPE_METAL_CLOTH : integer : Read
  .PX_ACTORTYPE_RB : integer : Read
  .PX_ACTORTYPE_RB_RAGDOLL : integer : Read
  .PX_ACTORTYPE_RB_BONE : integer : Read
  .PX_ACTORTYPE_CLOTHING : integer : Read
  .PX_ACTORTYPE_D6 : integer : Read
  .PX_ACTORTYPE_RIGIDSHAPE : integer : Read
  .PX_ACTORTYPE_SBCLOTHING : integer : Read
  .PX_ACTORTYPE_DESTRUCTION : integer : Read
  .PX_PANELPROP_VERSION : integer : Read
  .PX_SDK_MAXANGVEL : float : Read
  .PX_GRAVITYMODE_NONE : integer : Read
  .PX_GRAVITYMODE_DIR : integer : Read
  .PX_GRAVITYMODE_FORCE : integer : Read
 Methods:
 Actions:

Interface: DaylightSystemFactory2
 Properties:
 Methods:
  <Interface>Create sunClass:<class> skyClass:<class>
     sunClass default value: undefined
     skyClass default value: undefined
 Actions:

Interface: NetCreateHelpers
 Properties:
 Methods:
 Actions:

Interface: ParamCollectorOps
 Properties:
  .visible : bool : Read|Write
  .multiEdits : bool : Read|Write
  .isAbsolute : bool : Read|Write
  .showTrackBarKeys : bool : Read|Write
  .showTrackBarSelectedKeys : bool : Read|Write
  .hideOtherKeys : bool : Read|Write
 Methods:
  <void>newCollection()
     newCollection - no automatic redraw after invoked
  <void>duplicateCollection()
     duplicateCollection - no automatic redraw after invoked
  <void>deleteCollection()
     deleteCollection - no automatic redraw after invoked
  <integer>numCollections()
     numCollections - no automatic redraw after invoked
  <index>getActiveCollection()
     getActiveCollection - no automatic redraw after invoked
  <void>setCollectionName <index>collectionIndex <string>name
     setCollectionName - no automatic redraw after invoked
  <string>getCollectionName <index>collectionIndex
     getCollectionName - no automatic redraw after invoked
  <integer>getNumParametersInCollection <index>collectionIndex
     getNumParametersInCollection - no automatic redraw after invoked
  <int by value array>getSelectedParameters <index>collectionIndex
     getSelectedParameters - no automatic redraw after invoked
  <void>doLinkToObjectDialog()
     doLinkToObjectDialog - no automatic redraw after invoked
  <void>linkToObject <node>node
     linkToObject - no automatic redraw after invoked
  <void>removeLinkToObject()
     removeLinkToObject - no automatic redraw after invoked
  <void>doPutToObjectDialog()
     doPutToObjectDialog - no automatic redraw after invoked
  <void>putToObject <node>node
     putToObject - no automatic redraw after invoked
  <void>doGetFromObjectDialog()
     doGetFromObjectDialog - no automatic redraw after invoked
  <void>getFromObject <node>node
     getFromObject - no automatic redraw after invoked
  <void>doRemoveFromObjectDialog()
     doRemoveFromObjectDialog - no automatic redraw after invoked
  <void>removeFromObject <node>node
     removeFromObject - no automatic redraw after invoked
  <void>doAddToSelectedDialog()
     doAddToSelectedDialog - no automatic redraw after invoked
  <void>doAddDialog()
     doAddDialog - no automatic redraw after invoked
  <void>deleteSelectedParameters()
     deleteSelectedParameters - no automatic redraw after invoked
  <void>deleteAllParameters()
     deleteAllParameters - no automatic redraw after invoked
  <void>addNewRollout <string>name <bool>addSelectedParameters
     addNewRollout - no automatic redraw after invoked
  <void>deleteRollout <index>index
     deleteRollout - no automatic redraw after invoked
  <void>deleteRolloutMoveUp <index>index
     deleteRolloutMoveUp - no automatic redraw after invoked
  <void>deleteRolloutMoveDown <index>index
     deleteRolloutMoveDown - no automatic redraw after invoked
  <void>DoRenameRolloutDialog()
     DoRenameRolloutDialog - no automatic redraw after invoked
  <void>RenameRollout <index>index <string>name
     RenameRollout - no automatic redraw after invoked
  <bool>isRolloutSelected()
     isRolloutSelected - no automatic redraw after invoked
  <index>getSelectedRollout()
     getSelectedRollout - no automatic redraw after invoked
  <integer>numRollouts <index>collectionIndex
     numRollouts - no automatic redraw after invoked
  <void>setRolloutName <index>collectionIndex <index>rolloutIndex <string>name
     setRolloutName - no automatic redraw after invoked
  <string>getRolloutName <index>collectionIndex <index>rolloutIndex
     getRolloutName - no automatic redraw after invoked
  <integer>getNumParameters <index>collectionIndex <index>rolloutIndex
     getNumParameters - no automatic redraw after invoked
  <integer>getNumSelectedParameters <index>collectionIndex <index>rolloutIndex
     getNumSelectedParameters - no automatic redraw after invoked
  <bool>anyParameters()
     anyParameters - no automatic redraw after invoked
  <bool>anyRollouts()
     anyRollouts - no automatic redraw after invoked
  <bool>anySelected()
     anySelected - no automatic redraw after invoked
  <integer>numSelected()
     numSelected - no automatic redraw after invoked
  <void>selectAll()
     selectAll - no automatic redraw after invoked
  <void>selectAllRollout()
     selectAllRollout - no automatic redraw after invoked
  <void>selectNone()
     selectNone - no automatic redraw after invoked
  <void>selectInvert()
     selectInvert - no automatic redraw after invoked
  <bool>addParameterBySubNum <fpvalue>animOwner <index>subNum <index>collectionIndex <index>rolloutIndex <string>name
     addParameterBySubNum - no automatic redraw after invoked
  <void>moveSelectedParameters <enum>type
     moveSelectedParameters - no automatic redraw after invoked
     type enums: {#moveUp|#moveDown|#moveUpRollout|#moveDownRollout}
  <void>keyParameters <bool>selectedOnly
     keyParameters - no automatic redraw after invoked
  <void>resetParameters <bool>selectedOnly
     resetParameters - no automatic redraw after invoked
  <bool>addParameter <fpvalue>anim <index>collectionIndex <index>rolloutIndex <string>name
     addParameter - no automatic redraw after invoked
  <bool>addParameterTraverse <fpvalue>anim <bool>addChildren <index>collectionIndex <index>rolloutIndex <string>name
     addParameterTraverse - no automatic redraw after invoked
  <integer>getParameterIndex <index>collectionIndex <index>rolloutIndex <index>paramIndexInRollout
     getParameterIndex - no automatic redraw after invoked
  <maxObject>getParameterParentAnim <index>paramIndex
     getParameterParentAnim - no automatic redraw after invoked
  <integer>getParameterSubAnimNum <index>paramIndex
     getParameterSubAnimNum - no automatic redraw after invoked
  <maxObject>getParameterAnim <index>paramIndex
     getParameterAnim - no automatic redraw after invoked
  <void>setParameterNotesTitle <index>paramIndex <string>text
     setParameterNotesTitle - no automatic redraw after invoked
  <string>getParameterNotesTitle <index>paramIndex
     getParameterNotesTitle - no automatic redraw after invoked
  <void>setParameterNotesNotes <index>paramIndex <string>text
     setParameterNotesNotes - no automatic redraw after invoked
  <string>getParameterNotesNotes <index>paramIndex
     getParameterNotesNotes - no automatic redraw after invoked
  <void>setParameterNotesURL <index>paramIndex <string>text
     setParameterNotesURL - no automatic redraw after invoked
  <string>getParameterNotesURL <index>paramIndex
     getParameterNotesURL - no automatic redraw after invoked
  <void>setParameterSelected <index>paramIndex <bool>selected
     setParameterSelected - no automatic redraw after invoked
  <bool>getParameterSelected <index>paramIndex
     getParameterSelected - no automatic redraw after invoked
  <node by value array>getParameterNodes <index>paramIndex
     getParameterNodes - no automatic redraw after invoked
  <void>doEditNotesDialog()
     doEditNotesDialog - no automatic redraw after invoked
  <void>refresh()
     refresh - no automatic redraw after invoked
 Actions:

Interface: IViewportShadingMgr
 Properties:
  .ShadingLimits : enum : Read|Write
     ShadingLimits enums: {#None|#Good|#Best}
  .AutoDisplaySelLights : bool : Read|Write
  .DefaultLightCastShadows : bool : Read|Write
  .GlobalShadowIntensity : float : Read|Write
  .UseTransparencyInShadows : bool : Read|Write
  .UpdateShadowsInActiveViewportOnly : bool : Read|Write
  .MaxActiveLight : integer : Read|Write
  .UseGITransparency : bool : Read|Write
  .ShadowFilterSize : float : Read|Write
 Methods:
  <void>SelectShadowCastingLights()
  <void>SelectIlluminatingLights()
  <void>DisplayOnlySelectedLights()
  <void>LockSelectedLights <bool>locked
  <void>GetViewportShadingLights <&node array>nodeList <enum>lightProperty
     nodeList is In and Out parameter
     lightProperty enums: {#ShadowCasting|#Illuminating|#Locked}
  <void>CastShadowsSelectedOnly <bool>Enabled
  <bool>IsLightNodeSupported <node>LightNode
  <bool>IsShadingLimitValid <enum>ShadingLimits
     ShadingLimits enums: {#None|#Good|#Best}
  <void>ReviewGPUDiagnostics()
  <void>SetViewportShadingLimits <enum>ShadingLimits Quiet:<bool>
     ShadingLimits enums: {#None|#Good|#Best}
     Quiet default value: true
 Actions:

Interface: HDIKSys
 Properties:
 Methods:
  <void>ikChain <node>startJoint <node>endJoint <boolean>createEndEffector
  <boolean>RemoveChain <node>chainNode
     RemoveChain - no automatic redraw after invoked
 Actions:

Interface: statusPanel
 Properties:
  .visible : boolean : Read|Write
 Methods:
 Actions:

Interface: mental_ray_string_options
 Properties:
  .numOptions : integer : Read
 Methods:
  <void>AddOption <string>string <fpvalue>option index:<index>
     index default value: 0
  <void>RemoveOption <index>index
  <TSTR by value>GetOptionString <index>index
  <fpvalue by value>GetOptionValue <index>index
 Actions:

Interface: FacesOrientation
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: NodeCloneMgrTest
 Properties:
 Methods:
  <boolean>CloneNodes <&node array>nodes cloneType:<enum> offset:<point3 by value> actualNodes:<&node array> newNodes:<&node array>
     nodes is In parameter
     cloneType enums: {#copy|#instance|#reference}
     cloneType default value: #copy
     offset default value: [0,0,0]
     actualNodes default value: #()
     actualNodes is Out parameter
     newNodes default value: #()
     newNodes is Out parameter
 Actions:

Interface: WorkingPivot
 Properties:
  .EditMode : boolean : Read|Write
  .UseMode : boolean : Read|Write
  .AxisSize : float : Read|Write
 Methods:
  <matrix3 by value>getTM()
  <void>setTM <&matrix3>tm
     tm is In and Out parameter
  <void>alignToView()
  <void>resetTMToNode <node>node
  <void>setPlacePivotViewMode <boolean>on <boolean>alignToView
  <boolean>getPlacePivotViewMode()
  <void>setPlacePivotSurfaceMode <boolean>on <boolean>alignToView
  <boolean>getPlacePivotSurfaceMode()
  <boolean>getPlacePivotAlignToView()
 Actions:

Interface: batchRenderMgr
 Properties:
  .numViews : integer : Read
  .displayRenderedViews : bool : Read|Write
  .netRender : bool : Read|Write
 Methods:
  <Interface>GetView <index>index
  <index>FindView <string>name
  <Interface>CreateView <node>camera
  <bool>DeleteView <index>index
  <Interface>DuplicateView <index>index
  <void>Render()
 Actions:

Interface: BipFixer
 Properties:
 Methods:
  <void>DoAngSmoothing <&node array>nodeTab <integer>width <float>damping
     nodeTab is In and Out parameter
  <void>DoAngBlurring <&node array>nodeTab <integer>width <float>damping
     nodeTab is In and Out parameter
  <void>DoAdvAngSmoothing <&node array>nodeTab <integer>width <float>damping
     nodeTab is In and Out parameter
  <void>DoPosSmoothing <&node array>nodeTab <integer>width <float>damping
     nodeTab is In and Out parameter
  <void>DoPosBlurring <&node array>nodeTab <integer>width <float>damping
     nodeTab is In and Out parameter
  <void>DoRemoveKeys <&node array>nodeTab <integer>intervalWidth <boolean>deleteKeys
     nodeTab is In and Out parameter
  <void>DoKneeWobbleFix <&node array>nodeTab <float>frameThreshold <float>fluctuationThreshold
     nodeTab is In and Out parameter
  <void>DoKneeExtensionFix <&node array>nodeTab <float>kneeAngle
     nodeTab is In and Out parameter
 Actions:

Interface: trackSelectionSets
 Properties:
  .count : integer : Read
 Methods:
  <boolean>create <TSTR by value>name <maxObject by value array>tracks trackNames:<string by value array>
     trackNames default value: #()
  <boolean>delete <TSTR by value>name
  <TSTR by value>getName <index>index
  <void>setName <index>index <TSTR by value>name
  <TSTR by value>getCurrent <Interface>trackview
  <maxObject by value array>getTracks <TSTR by value>name <&maxObject array>tracks trackNames:<&string array>
     tracks is Out parameter
     trackNames default value: #()
     trackNames is Out parameter
  <boolean>add <TSTR by value>name <maxObject by value array>tracks trackNames:<string by value array>
     trackNames default value: #()
  <boolean>remove <TSTR by value>name <maxObject by value array>tracks
 Actions:

Interface: trackviews
 Properties:
  .currentTrackView : Interface : Read
  .current : Interface : Read
  .lastUsedTrackViewName : string : Read
 Methods:
  <Interface>getTrackView <fpvalue>name or index
  <Interface by value array>getAllOpenTrackViews()
  <integer>numTrackViews()
  <boolean>open <fpvalue>name or index layoutName:<TSTR by value> pos:<point2 by value> width:<integer> height:<integer> dock:<enum>
     layoutName default value: ""
     pos default value: [-1,-1]
     width default value: -1
     height default value: -1
     dock enums: {#float|#top|#bottom|#canDockOnTop}
     dock default value: #float
  <boolean>close <fpvalue>name or index
  <void>delete <fpvalue>name or index
  <string>getTrackViewName <index>index
  <boolean>zoomSelected <TSTR>name
  <boolean>zoomOn <TSTR>name <maxObject>object <index>subNum
  <boolean>setFilter()
     setFilter has variable number of arguments
  <boolean>clearFilter()
     clearFilter has variable number of arguments
  <fpvalue by value>pickTrackDlg()
     pickTrackDlg has variable number of arguments
  <boolean>isOpen <fpvalue>name or index
  <boolean>openLastUsedTrackView()
  <boolean>isCurrent <fpvalue>name or index
  <boolean>setCurrent <fpvalue>name or index
  <boolean>exists <fpvalue>name or index
 Actions:

Interface: ILightRef
 Properties:
 Methods:
 Actions:

Interface: FrameTagManager
 Properties:
 Methods:
  <integer>GetTagCount()
  <DWORD>GetTagID <index>index
  <time>GetTimeByID <DWORD>id relative:<boolean>
     relative default value: false
  <void>SetTimeByID <DWORD>id <time>time relative:<boolean>
     relative default value: false
  <DWORD>GetLockIDByID <DWORD>id
  <boolean>SetLockIDByID <DWORD>id <DWORD>lockID
  <TSTR>GetNameByID <DWORD>id
  <void>SetNameByID <DWORD>id <&TSTR>name
     name is In parameter
  <boolean>GetScaleByID <DWORD>id
  <void>SetScaleByID <DWORD>id <boolean>scale
  <index>FindItemByTime <time>time
  <index>FindItem <DWORD>id
  <DWORD>CreateNewTag <string>name <time>time lockID:<DWORD> scale:<boolean>
     lockID default value: 0
     scale default value: true
  <void>DeleteTag <DWORD>id
  <void>ResetFrameTags()
  <boolean>CheckForLoop <DWORD>testID <DWORD>id
 Actions:

Interface: RenderEnhancements
 Properties:
 Methods:
 Actions:

Interface: medit
 Properties:
 Methods:
  <maxObject>GetCurMtl()
  <void>SetActiveMtlSlot <index>slot <boolean>forceUpdate
  <index>GetActiveMtlSlot()
  <void>PutMtlToMtlEditor <maxObject>mtl <index>slot
  <maxObject>GetTopMtlSlot <index>slot
  <boolean>OkMtlForScene <material>mtl
  <void>UpdateMtlEditorBrackets()
 Actions:

Interface: BrushPresetMgr
 Properties:
 Methods:
  <boolean>IsActive()
  <void>OpenPresetMgr()
  <void>AddPreset()
  <void>LoadPresetFile <filename>file
  <void>SavePresetFile <filename>file
 Actions:

Interface: renderpresets
 Properties:
 Methods:
  <boolean>Save <integer>which <filename>file <bitArray>categories
  <boolean>Load <integer>which <filename>file <bitArray>categories loadNodes:<enum>
     loadNodes enums: {#prompt|#yes|#no|#cancel}
     loadNodes default value: #prompt
  <boolean>SaveAll <integer>which <filename>file
  <boolean>LoadAll <integer>which <filename>file
  <boolean>IsFileCompatible <integer>which <filename>file
  <string>MapIndexToCategory <filename>file <integer>index
  <integer>MapCategoryToIndex <filename>file <string>category
  <string>MapSceneIndexToCategory <integer>which <integer>index
  <integer>MapSceneCategoryToIndex <integer>which <string>category
  <bitArray>LoadCategories <filename>file
  <bitArray>SaveCategories <integer>which
 Actions:

Interface: OverlappingVertices
 Properties:
  .tolerance : float : Read|Write
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: LightMeterManager
 Properties:
  .deleteCacheBeforeCalculation : bool : Read|Write
 Methods:
  <integer>getNumLightMeterHelpers()
  <Interface>getNthLightMeterHelper <index>index
  <node>getNthLightMeterHelperNode <index>index
  <integer>getNumActiveLightMeterHelpers()
  <bool>isCalculatingMeters()
  <bool>calculateMeters <index>index <bool>useRenderTimes <bool>useRenderSettings
  <void>outputActiveMetersToCSVFiles <string>namePrefix
 Actions:

Interface: s3dexporter
 Properties:
 Methods:
  <void>preview()
  <void>analyze()
  <void>authcheck()
 Actions:

Interface: cmdPanel
 Properties:
 Methods:
  <integer>GetRollupThreshold()
  <void>SetRollupThreshold <integer>threshold
 Actions:

Interface: FlightStudioImport
 Properties:
 Methods:
  <float>GetVertexThreshold()
  <void>SetVertexThreshold <float>VertexThreshold
  <float>GetTrivialArea()
  <void>SetTrivialArea <float>TrivialArea
  <boolean>GetReadXRefs()
  <void>SetReadXRefs <boolean>KeepFaces
  <boolean>GetKeepFaces()
  <void>SetKeepFaces <boolean>KeepFaces
  <void>SetIgnoreMaterials <boolean>IgnoreMaterials
  <void>SetIgnoreTextures <boolean>IgnoreTextures
  <void>SetIgnoreBead <string>Opcode <boolean>IgnoreBead
  <void>SetMapFacesToSelections <boolean>MapFacesToSelections
  <string>GetStats()
  <string>GetTextureStats()
 Actions:

Interface: SceneExposureControl
 Properties:
  .exposureControl : value : Read|Write|Validated by Validator function
 Methods:
 Actions:

Interface: styleMgr
 Properties:
  .numInstances : integer : Read
  .numCategories : integer : Read
 Methods:
  <Interface>GetStyle <&TSTR>categName <&TSTR>styleName
     categName is In parameter
     styleName is In parameter
  <Interface>IsInstance <node>node
  <node>GetInstanceTop <node>node
  <integer>GetCategories <&Interface array>categories
     categories is In and Out parameter
 Actions:

Interface: Hair
 Properties:
 Methods:
  <void>Purge()
  <void>AddMod <node array>nodes
  <void>AddEffect <boolean>showGUI
  <boolean>CanUseLights <node array>nodes
  <void>AddHairProperties <node array>nodes
  <void>RemoveHairProperties <node array>nodes
  <void>ExportDRA <filename>draFileName <time>time <integer>voxels
  <void>ExportDRA2 <filename>draFileName <time>time <integer>voxels <&integer array>shaveNodeIDs
     shaveNodeIDs is In and Out parameter
 Actions:

Interface: BipWorkBench
 Properties:
 Methods:
  <void>ToggleShowX()
  <boolean>GetShowX()
  <void>ToggleShowY()
  <boolean>GetShowY()
  <void>ToggleShowZ()
  <boolean>getShowZ()
  <void>ToggleLayerEdit()
  <boolean>GetLayerEdit()
  <void>ToggleDrawDuringMove()
  <boolean>GetDrawDuringMove()
  <void>ToggleLimit180()
  <boolean>GetLimit180()
  <void>ShowQuatCurve()
  <void>ShowPosCurve()
  <void>ShowAngSpeedCurve()
  <void>ShowAngAccelCurve()
  <void>ShowAngJerkCurve()
  <void>ShowPosSpeedCurve()
  <void>ShowPosAccelCurve()
  <void>ShowPosJerkCurve()
  <void>PosCurveToWorld()
  <void>PosCurveToBipRoot()
  <void>PosCurveToThisNode <node>relativeToNode
  <void>Open()
  <void>ShowQuatXYZ()
  <void>ShowQuatXZY()
  <void>ShowQuatYXZ()
  <void>ShowQuatYZX()
  <void>ShowQuatZXY()
  <void>ShowQuatZYX()
 Actions:

Interface: SME
 Properties:
  .activeView : index : Read|Write
 Methods:
  <void>Open()
  <void>Close()
  <bool>IsOpen()
  <integer>GetNumViews()
  <index>CreateView <string>name
  <IObject>GetView <index>index
  <index>GetViewIndex <IObject>view
  <index>GetViewByName <string>name
  <void>DeleteView <index>index <bool>ask_user
  <maxObject>GetMtlInParamEditor()
  <void>SetMtlInParamEditor <maxObject>mtlbase
  <Interface>GetNavigator()
  <Interface>GetMaterialPool()
  <Interface>GetParamEditor()
  <Interface>GetMainframe()
  <maxObject>DoMtlBrowseDlg <HWND>parent <DWORD>flags <&boolean>newMat <&boolean>cancel fromLibrary:<*boolean> copiedMaterial:<*boolean>
     newMat is In and Out parameter
     cancel is In and Out parameter
     fromLibrary default value: undefined
     fromLibrary is In and Out parameter
     copiedMaterial default value: undefined
     copiedMaterial is In and Out parameter
  <void>OpenMtlBrowseDlg()
 Actions:

Interface: FlippedUVWFaces
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: objXRefs
 Properties:
 Methods:
  <maxObject>addNewXRefObject <filename>fname <string>objname <integer>flags
  <integer>getNumXRefObjects <filename>fname
  <maxObject>getXRefObject <filename>fname <index>index
  <integer>getNumFiles()
  <filename>getFileName <index>index
  <boolean>reloadFile <filename>fname
  <boolean>isFileUnresolved <filename>fname
  <boolean>isFileDisabled <filename>fname
  <maxObject by value array>getAllXRefObjects()
  <integer>getEmptyXRefRecCount()
 Actions:

Interface: blockMgr
 Properties:
 Methods:
  <Interface>IsInstance <node>node
  <Interface>GetInstance <node>node <&node array>instances
     instances is In and Out parameter
  <node>GetTopBlock <node>node
  <Interface>MakeBlockRefComponent <node>node
  <bool>RemoveBlockRefComponent <node>node
 Actions:

Interface: pluginManager
 Properties:
  .visible : boolean : Read|Write
  .pluginDllCount : integer : Read
  .loadedPluginDllSize : integer : Read
 Methods:
  <string>pluginDllName <index>index
     pluginDllName - no automatic redraw after invoked
  <string>pluginDllDirectory <index>index
     pluginDllDirectory - no automatic redraw after invoked
  <TSTR by value>pluginDllFullPath <index>index
     pluginDllFullPath - no automatic redraw after invoked
  <integer>pluginDllSize <index>index
     pluginDllSize - no automatic redraw after invoked
  <boolean>isPluginDllLoaded <index>index
     isPluginDllLoaded - no automatic redraw after invoked
  <boolean>loadPluginDll <index>index
     loadPluginDll - no automatic redraw after invoked
  <void>loadClass <class>class
 Actions:

Interface: particleFlowUtility
 Properties:
 Methods:
  <integer>cleanUpParticleFlow <bool>doReport
  <void>resetParticleView()
  <integer>synchronizeLayers <bool>doReport
  <void>repairCacheSystem <bool>doReport
  <void>presetManager()
 Actions:

Interface: ICEFlowFileBirthSetup
 Properties:
 Methods:
 Actions:

Interface: ICEFlowSystemFactory
 Properties:
 Methods:
 Actions:

Interface: srr_exports
 Properties:
 Methods:
 Actions:

Interface: ProjectionIntersectorMgr
 Properties:
 Methods:
 Actions:

Interface: IBitmapPager
 Properties:
  .enabled : boolean : Read|Write
  .pageFilePath : filename : Read|Write
  .memoryLimit_percent : float : Read|Write|Validated by Range: 0.0 to 1.0
  .memoryPadding_percent : float : Read|Write|Validated by Range: 0.0 to 1.0
  .memoryLimitAutoMode : boolean : Read|Write
  .memoryLimit_megabytes : integer : Read
  .memoryUsedForPager_megabytes : integer : Read
  .memoryTotalForPager_megabytes : integer : Read
  .memoryPadding_megabytes : integer : Read
  .memoryAvailablePadded_megabytes : integer : Read
 Methods:
 Actions:

Interface: PaintSoftSelPresetContext
 Properties:
 Methods:
 Actions:

Interface: IsolatedVertices
 Properties:
 Methods:
  <enum>Check <time>time <node>nodeToCheck <&index array>results
     Check enums: {#Failed|#Vertices|#Edges|#Faces
     results is In and Out parameter
  <bool>hasPropertyDlg()
  <void>showPropertyDlg()
 Actions:

Interface: pop
 Properties:
  .DisplayType : enum : Read|Write
     DisplayType enums: {#StickFigure|#Segmented|#CrowdCustom|#CrowdSkin|#HighSkin}
  .NumFrames : integer : Read|Write
  .RealWorldScale : float : Read|Write
 Methods:
  <bool>AddIdleArea <node>IdleArea
  <bool>AddFlow <node>Flow
  <void>Simulate()
  <void>RegenerateSelected()
  <void>DeletePeople()
  <void>DisplayEnv <boolean>show
  <void>DisplayPeople <boolean>show
 Actions:

Interface: BipFilter
 Properties:
 Methods:
  <void>angSmoothing <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>angBlurring <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>angBoosting <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>advAngSmoothing <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>posSmoothing <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>posBlurring <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>posBoosting <&node array>nodeTab <integer>width <float>damping <interval>range
     nodeTab is In and Out parameter
  <void>keyReduction <&node array>nodeTab <float>tolerance <integer>keySpacing <float>COMTolerance <float>COMKeySpacing <interval>range
     nodeTab is In and Out parameter
  <void>keyPerFrame <&node array>nodeTab
     nodeTab is In and Out parameter
  <void>enablePosSubAnim <&node array>nodeTab <boolean>enable
     nodeTab is In and Out parameter
  <void>enableRotSubAnim <&node array>nodeTab <boolean>enable
     nodeTab is In and Out parameter
  <void>enableScaleSubAnim <&node array>nodeTab <boolean>enable
     nodeTab is In and Out parameter
  <void>collapsePosSubAnim <&node array>nodeTab <boolean>perFrame <boolean>delete
     nodeTab is In and Out parameter
  <void>collapseRotSubAnim <&node array>nodeTab <boolean>perFrame <boolean>delete
     nodeTab is In and Out parameter
  <void>createPosSubAnim <&node array>nodeTab <control>controlToClone <boolean>checkForExistence
     nodeTab is In and Out parameter
  <void>createRotSubAnim <&node array>nodeTab <control>controlToClone <boolean>checkForExistence
     nodeTab is In and Out parameter
  <void>createScaleSubAnim <&node array>nodeTab <control>controlToClone <boolean>checkForExistence
     nodeTab is In and Out parameter
  <void>DoKneeWobbleFilter <&node array>nodeTab <float>frameThreshold <float>fluctuationThreshold <interval>range
     nodeTab is In and Out parameter
  <void>DoKneeExtensionFilter <&node array>nodeTab <float>kneeAngle <interval>range
     nodeTab is In and Out parameter
 Actions:

Interface: dxshadermanager
 Properties:
 Methods:
  <maxObject>getViewportManager <material>material
  <boolean>IsVisible()
  <float>SetVisible <boolean>show
  <maxObject>addViewportManager <material>material
 Actions:

Interface: IKSys
 Properties:
 Methods:
  <node>ikChain <node>startJoint <node>endJoint <string>solver
  <integer>solverCount()
  <TSTR by value>solverName <integer>solverIndex
  <TSTR by value>solverUIName <integer>solverIndex
  <void>suspendLinkNotify()
  <void>resumeLinkNotify()
  <bool>isLinkNotifySuspended()
 Actions:

Interface: MaxRibbon
 Properties:
 Methods:
  <void>SetRibbonOrientation <enum>orientation
     SetRibbonOrientation - no automatic redraw after invoked
     orientation enums: {#Horizontal|#Vertical}
  <enum>GetRibbonOrientation()
     GetRibbonOrientation enums: {#Horizontal|#Vertical
     GetRibbonOrientation - no automatic redraw after invoked
  <void>ShowRibbon <boolean>show
     ShowRibbon - no automatic redraw after invoked
  <boolean>IsRibbonOpen()
     IsRibbonOpen - no automatic redraw after invoked
  <void>LoadRibbonConfig <&TSTR>configFile
     LoadRibbonConfig - no automatic redraw after invoked
     configFile is In and Out parameter
  <void>SaveRibbonConfig <&TSTR>configFile
     SaveRibbonConfig - no automatic redraw after invoked
     configFile is In and Out parameter
  <void>ResetRibbon()
     ResetRibbon - no automatic redraw after invoked
  <void>SetRibbonDockState <enum>dockState
     SetRibbonDockState - no automatic redraw after invoked
     dockState enums: {#TopDock|#BottomDock|#LeftDock|#RightDock|#Floating}
  <boolean>IsRibbonFloating()
     IsRibbonFloating - no automatic redraw after invoked
 Actions:

Interface: walkThroughOps
 Properties:
  .isEnabled : bool : Read
  .isActive : bool : Read
  .stepSize : float : Read|Write
  .sensitivity : float : Read|Write
  .invertVertical : bool : Read|Write
  .lockVertical : bool : Read|Write
  .lockHorizontal : bool : Read|Write
  .accelerate : bool : Read|Write
 Methods:
  <void>start()
  <void>stop()
  <void>level()
  <void>resetStepSize()
 Actions:

OK

```
