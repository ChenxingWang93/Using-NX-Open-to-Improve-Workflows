- 15
  - Installing Visual Studio 安装 Visual Studio

<details>

<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_15](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/db08a71a-9167-4824-b65c-ce22d6dc29e1)
</details>

- 16
  - Installing NXOpen Templates NXOpen 模版
  - Licensing Issues Again 许可问题
  - Example 1: Hello World Again 

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_16](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/61ec940f-debb-4518-a2c8-64816eaadae7)
</details>

- 17

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_17](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/f74d1ad9-77b0-4329-a1e5-4416b1df40eb)
</details>

- 18

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_18](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/a763305b-0b28-47fb-b3d5-9109243e0265)
</details>

- 19
  - Example 2: Declaring Variables 声明变量

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_19](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/4b1d6746-f9e6-4ef6-84ab-53571564d76c)
</details>

``` vb
Dim sel = NXOpen.UI.GetUI.SelectionManager
Dim myView As View
Dim p1, p2, p3 As Point3d
sel.SelectScreenPosition("Specify first point",myView, p1)   ' Get first point from user '
sel.SelectScreenPosition("Specify second point",myView, p2)  ' Get second point '
sel.SelectScreenPosition("Specify third point",myView, p3)   ' Get third point '
u As New Vector3d(p2.X - p1.X, p2.Y - p1.Y, p2.Z - p1.Z)  'Vector3d from p1 to p2'
v As New Vector3d(p3.X - p1.X, p3.Y - p1.Y, p3.Z - p1.Z)  'Vector3d from p1 to p3'
uu = u.X * u.X + u.Y * u.Y + u.Z * u.Z   'Dot product of vectors'
uv = u.X * v.X + u.Y * v.Y + u.Z * v.Z
vv = v.X * v.X + v.Y * v.Y + v.Z * v.Z
det = uu * vv - uv * uv                  ' Determinate for solving linear equations '
alpha = (uu * vv - uv * uv) / (2 * det)
beta = (uu * vv - uu * uv) / (2 * det)
rx = alpha * u.X + beta * v.X            ' Radius vector components '
ry = alpha * u.Y + beta * v.Y 
rz = alpha * u.Z + beta * v.Z
radius = Math.Sqrt(rx*rx + ry*ry + rz*rz)' Radius is length (norm) of this vector '

Guide.InfoWriteLine(radius)              ' Output to Info window '
```

- 20
  - Example 3: WinForms Again

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_20](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/0884c6f1-506d-45c1-b5aa-511eb07f994f)
</details>

- 21

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_21](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/db6131c1-a317-4454-8176-7c41bd19b2c3)
</details>

- 22
  - Example 4: Hello World Yet Again(the hard way) 

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_22](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/fe372858-2e24-4650-932f-982190bed3a7)
</details>

- 23

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_23](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/6a21ea76-a658-4714-a6e5-2ba0bfe0ae84)
</details>

- 24
  - Example 5: Editing a Recorded Journal 编辑一个记录

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_24](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/81a23eb1-7452-4d40-bd37-79892a1f2226)
</details>

- 25

<details>
<summary> 截图 </summary>
  
![Chapter3_UsingVisualStudioExpress_20230913_25](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/29cac710-53a1-4049-b910-5790fcf34ace)
</details>

- 26

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_26](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/726bd693-b507-4ea2-b10a-729c9e05d2d6)
</details>

- 27
  - Debugging 调试
    - Using Debugger.Launch 调试
    - Using Attach to Process 附上流程

<details>
<summary> 截图 </summary>

![Chapter3_UsingVisualStudioExpress_20230913_27](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/4fcbddb9-7eb7-4937-9b60-20860dbe54e6)
![5151695718819_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/6a1078a9-3dd8-4f03-9756-ffa289b51cbf)
</details>
