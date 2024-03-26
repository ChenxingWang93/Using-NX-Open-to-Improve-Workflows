- 99
  - Cycling Through CAM Objects 遍历 CAM 对象
<details>
<summary> 截图 </summary>

![6531697786983_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/96743e54-49c0-4c4f-8893-003a4a25c9af)
</details>

``` vb
Dim workPart As Part = NXOpen.Session.GetSession.Parts.Work
Dim setup As NXOpen.CAM.CAMSetup = workPart.CAMsetup
```

#### Cycling through CAM Objects

``` vb
Dim setup As NXOpen.CAMSetup = workPart.CAMSetup
Dim opCollection As NXOpen.CAM.OperationCollection = setup.CAMOperationCollection

For Each op As NXOpen.CAM.Operation In opCollection
   Dim opType As System.Type = op.GetType
   Guide.InfoWriteLine(opType.ToString)
Next
```

``` vb
Dim setup As NXOpen.CAM.CAMSetup = workPart.CAMSetup
Dim groups As NXOpen.CAM.NCGroupCollection = setup.CAMGroupCollection

For Each group As NXOpen.CAM.NCGroup In groups
   If TypeOf(group) Is NXOpen.CAM.Tool = DirectCast(group, NXOpen.CAM.Tool)
   Dim toolType As NXOpen.CAM.Tool.Types                /*类型*/
   Dim toolSubType As NXOpen.CAM.Tool.Subtypes          /*亚型*/
   tool.GetTypeAndSubtype(toolType, toolSubType)        /**/
   Guide.InfoWriteLine("Tool type:    " & toolType.ToString)
   Guide.InfoWriteLine("Tool subtypes:" & toolSubType.ToString)
```

- 100
  - editing CAM Objects 编辑 CAM 对象
<details>
<summary> 截图 </summary>
  
![6541697786989_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/7e46ddc2-d639-4427-965b-6f08ce95b085)
</details>

``` vb
Dim setup As NXOpen.CAM.CAMSetup = workPart.CAMSetup
Dim opCollection As NXOpen.CAM.OperationCollection = setup.CAMOperationCollection

For Each op As NXOpen.CAM.Operation In opCollection
   If TypeOf(op) Is NXOpen.CAM.HoleDrilling Then
      Dim drillop As CAM.HoleDrilling = CType(op, CAM.HoleDrilling)
      Dim builder As CAM.HoleDrillingBuilder = opCollection.CreateHoleDrillingBuilder(drillop)
      builder.CollisionCheck = True
      builder.Commit
   End If
Next
```

|Function 函数|Creates a builder for 创建一个|
|-------------|-----------------------------|
|CreateCavityMillingBuilder          |A planar milling cavity operation 平面铣削打孔操作     |
|CreateCenterlineDrillTurningBuilder |A centerline drill turning operation 中心线打孔转动操作|
|CreateEngravingBuilder              |A planar milling text operation 平面铣削文字操作       |
|CreateFaceMillingBuilder            |A planar milling facing operation 平面铣削文字操作     |
|CreateHoleDillingBuilder            |A hole drilling operation 打孔操作                    |
|CreatePlanarMillingBuilder          |A planar milling planar operation 铣削平面操作         |


|Function 函数|Creates a builder for 创建一个|
|-------------|-----------------------------|
|CreateBarrelToolBuilder|A barrel tool 桶工具|
|CreateDrillGeomBuilder |A drill geometry 一种打孔几何|
|CreateDrillMethodBuilder|A drill method  一种打孔方法|
|CreateDrillTapToolBuilder|A drill tap tool 一种钻丝锥工具|
|CreateMachineTurretGroupBuilder|A machine turret group|
|CreateMillToolBuilder|A mill tool|
|CreateMillGeomBuilder|A mill geometry|
|CreateProgramOrderGroupBuilder|A program order group|


- 101
  - CAM views CAM 视图
<details>
<summary> 截图 </summary>

![6551697786995_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/675db386-be45-4e1f-b0c3-a7ea43625835)
</details>

``` vb
Dim setup As NXOpen.CAM.CAMSetup = workPart.CAMSetup
Dim groups As NXOpen.CAM.NCGroupCollection = setup.CAMGroupCollection

For Each group As NXOpen.CAM.NCGroup In groups
   If TypeOf(group) Is NXOpen.CAM.Tool Then
      Dim toolType As NXOpen.CAM.Tool.Types
      Dim toolSubType As NXOpen.CAM.Tool.Subtypes
      tool.GetTypeAndSubtype(toolType, toolSubtype)
      If toolType = CAM.Tool.Types.Mill
         Dim builder As NXOpen.CAM.MillingToolBuilder = groups.CreateMillToolBuilder(tool)
         builder.CoolantThrough = True
         builder.Commit
      End If
    End If
Next Next
```

#### ProgramView 程序视图

#### MachineToolView 机械工具视图

#### GeometryView 几何视图

#### MethodView 方法视图

``` vb
Dim setup As NXOpen.CAM.CAMSetup = workPart.CAMSetup

Dim geometryRoot As NXOpen.CAM.NCGroup = setup.GetRoot(NXOpen.CAM.CAMSetup.View.Geometry)
Dim methodRoot   As NXOpen.CAM.NCGroup = setup.GetRoot(NXOpen.CAM.CAMSetup.View.MachineMethod)
Dim machineRoot  As NXOpen.CAM.NCGroup = setup.GetRoot(NXOpen.CAM.CAMSetup.View.ProgramOrder)

Dim geometryRootMembers As NXOpen.CAM.CAMObject() = geometryRoot.GetMembers
Dim methodRootMembers   As NXOpen.CAM.CAMObject() =   methodRoot.GetMembers
Dim machineRootMembers  As NXOpen.CAM.CAMObject() =  machineRoot.GetMembers
Dim programRootMembers  As NXOpen.CAM.CAMObject() =  programRoot.GetMembers
```

- 102
  - Creating a Tool 创建一个工具🔧
<details>
<summary> 截图 </summary>

![6561697787001_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/61d9e88a-6203-4f20-9859-70b86613ee74)
</details>

``` vb
Dim setup As NXOpen.CAM.CAMSetup = workPart.CAMSetup
Dim group As NXOpen.CAM.NCGroupCollection = setup.CAMGroupCollection
Dim machineRoot As NXOpen.CAM.NCGroup = setup.GetRoot(NXOpen.CAM.CAMSetup.View.MachineTool)

Dim camFalse As CAM.NCGroupCollection.UseDefaultName = CAM.NCGroupCollection.UseDefaultName.False

Dim toolGroup As CAM.NCGroup
toolGroup = groupCollection.CreateTool(machineRoot, "mill_planar", "BALL_MILL", camFalse, "T24")
Dim myTool As CAM.Tool = CType(toolGroup, CAM.Tool)
```

|Tool Type 工具类型|Tool Subtype 工具亚型          |
|-----------------|-----------------------------|
|mill_planar      |MILL铣削                      |
|mill_planar      |CHAMFER_MILL倒角铣削           |
|mill_planar      |BALL_MILL球体铣削              |
|mill_planar      |SPHERICAL_MILL球形铣削         |
|mill_planar      |T_CUTTERT型切                 |
|mill_planar      |BARREL桶                      |
|hole_making      |COUNTER_SINK柜台_水槽          |
|hole_making      |COUNTER_BORE沉孔              |
|drill            |COUNTERSINKING_TOOL柜台_水槽工具|
|drill            |COUNTERBORING_TOOL沉孔工具     |

``` vb
Dim toolBuilder As CAM.MillToolBuilder = groupCollection.CreateMillToolBuilder(myTool)

toolBuilder.TlDiameterBuilder.Value = 4.5
toolBuilder.TlHeightBuilder.Value = 15
toolBuilder.TlHeightBuilder.Value = 4
toolBuilder.Description = "Example ball mill"
toolBuilder.HelicalDiameter.Value = 80.0

toolBuilder.Commit

toolBuilder.Destroy
```
