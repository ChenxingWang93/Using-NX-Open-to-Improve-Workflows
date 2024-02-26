
- 4
  - System Requirement - The .NET Framework
  - Typographic Convensions
  - Licensing

<details>
<summary> 截图 </summary>
  
![4831695030602_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/9851fd9d-658f-4032-9113-d85d22d5027f)
</details>

- 5
  - The Guide Functions
  - Example 1: Hello World

<details>
<summary> 截图 </summary>
  
![4851695030602_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/05f32edd-2ad3-4740-8869-ae9d0dfbcdd9)
</details>


- 6
  - Example 2: Collections 集

<details>
<summary> 截图 </summary>

![4861695030603_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/5ff5cf66-65c3-468a-9b10-b8bd2094dba9)
</details>

[...NX]\UGOPEN\NXOpenExamples\VB\Templates

[...NX] shorthand for the location where NX is installed

somewhere like C:\Program Files\Siemens\NX 12

``` vb
Imports System
Imports NXOpen

Module NXOpenSample
  Sub Main ()

    Dim theSession = Session.GetSession()

    'Your code goes here'
  End Sub
End Module
```

```
Guide.InfoWriteLine("Hello, World!")
```

- 7
<details>
<summary> 截图 </summary>
  
![4871695030603_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/a3340f2c-7114-4852-802c-5ff149ea1a87)
</details>

``` vb
Imports NXOpen

Module NXJournal
   Sub Main ()
      
      Dim theSession = NXOpen.Session.GetSession()

      'Your code goes here'
    End Sub
End Module
```

replace 'Your code goes here' 

with

``` vb
Dim workPart = theSession.Parts.Work

Dim numCurves As Integer = 0
Dim curveLength As Double
For Each cur As curve In workPart.Curves
   numCurves = numCurves + 1
   curveLength = cur.GetLength
   Guide.InfoWriteLine("Curve "& numCurves & " has length " & curveLength)
Next cur
Guide.InfoWriteLine("Work part has " & numCurves & " curves.")
```

|Lines of code|Explanation|
|-------------|-----------|
|Dim workPart = theSession.Parts.Work|Declares a variable "workPart"|
|For Each curve In workPart.Curves||
|||

- 8
  - Example 3: Creating Simple Geometry 创建 简单 几何📐
 
<details>
<summary> 截图 </summary>
  
![4881695030603_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/d07434c5-6835-4d35-81c5-816119b6082f)
</details>

see the following output if you used the curves.prt part file

``` pseudocode
Curve 1 has length 162.999980765796
Curve 2 has length 198.00000586428
Curve 3 has length 198.368182323472
Curve 4 has length 233.301819519901
Curve 5 has length 159.651987547216
Curve 6 has length 109.226575886056
Curve 7 has length 350.572788226968
Curve 8 has length 321.167240792993
Work part has 8 curves
```

- 9
  - Example 4: Reading Attributes 读取 属性

<details>
<summary> 截图 </summary>

![4841695030602_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/e5a377c2-da68-4932-8106-aac0059bcbb4)
</details>

``` vb
Dim workPart = theSession.Parts.Work
Dim vertex As New Point3d(0,0,0)
Dim focus As New Point3d(100,0,0)
Dim axisX As New Vector3d(1,0,0)
Dim axisY As New Vector3d(0,1,0)

Dim focLength = focus.X
Dim h = 100.0

Dim p1, p2 As Point3d

Dim lens = workPart.Curves.CreateParabola(vertex, axisX, axisY, focLength, -h, h)

For y = -h to h Step 10.0
   Dim x = (y*y)/(4.0*focLength)
   p1 = New Point3d(x,y,0)
   p2 = New Point3d(250,y,0)
   workPart.Curves.CreateLine(focus, p1)
   workPart.Curves.CreateLine(p1, p2)
Next y
```

``` vb
Dim theSession = Session.GetSession()

Guide.InfoWriteLine("Outputting list of attributes in each body in the work part:")
Dim bodies = theSession.Parts.Work.Bodies
For Each bod As body in bodies
   Dim attributes = bod.GetUserAttributes()
   For Each attr As NXObject.AttributeInformation in attributes
      Guide.InfoWriteLine(attr.Title & " = " & attr.StringValue)
   Next attr
Next bod
Guide.InfoWriteLine("")
```

- 10

<details>
<summary> 截图 </summary>

![4891695030604_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/31e69ddf-b330-4f18-853f-477ec6a93c65)
</details>

- 11
  - Example 5: WinForms(The Hard Way)

<details>
<summary> 截图 </summary>
  
![4901695030604_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/681f9b30-fc90-4c7a-b637-c3ce54426374)
</details>

- 12

<details>
<summary> 截图 </summary>

![4911695030605_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/f1da57a0-7046-46c7-8abe-7684470b5ea6)
</details>

- 13

<details>
<summary> 截图 </summary>

![5131695714647_ pic_hd](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/2d161aed-841b-4dc4-a48a-d4acfa66a5ea)
</details>

- 14
  - What Next? 下一个

<details>
<summary> 截图 </summary>

![5141695714667_ pic](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/542b0d38-6ded-4721-a4b4-abe43a9edae8)
</details>
