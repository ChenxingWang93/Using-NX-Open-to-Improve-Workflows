- 99
  - Cycling Through CAM Objects 遍历 CAM 对象
<details>
<summary> 截图 </summary>

![6531697786983_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/96743e54-49c0-4c4f-8893-003a4a25c9af)
</details>


- 100
  - editing CAM Objects 编辑 CAM 对象
<details>
<summary> 截图 </summary>
  
![6541697786989_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/7e46ddc2-d639-4427-965b-6f08ce95b085)
</details>


- 101
  - CAM views CAM 视图
<details>
<summary> 截图 </summary>

![6551697786995_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/675db386-be45-4e1f-b0c3-a7ea43625835)
</details>


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

|Tool Type 工具类型|Tool Subtype 工具亚型|
|-----------------|-------------------|
|mill_planar      |MILL               |
|mill_planar      |CHAMFER_MILL       |
|mill_planar      |BALL_MILL          |
|mill_planar      |SPHERICAL_MILL     |
|mill_planar      |T_CUTTER           |
|mill_planar      |BARREL             |
|hole_making      |COUNTER_SINK       |
|hole_making      |COUNTER_BORE       |
|drill            |COUNTERSINKING_TOOL|
|drill            |COUNTERBORING_TOOL |

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
