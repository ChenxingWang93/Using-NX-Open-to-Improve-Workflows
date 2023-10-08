'D:\Program Files\Siemens\NX 11.0\NXBIN'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/d0a7c4e4-a984-4528-b21f-199a714768f7)


'D:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/0d143e1e-1f3b-4509-b47e-a0a723655377)


copy files 'VB', 'VC', 'VC#' from 'D:\Program Files\Siemens\NX 11.0\UGOPEN\vs_files' 

to 

'D:\Program Files\Microsoft Visual Studio\2022\Community'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/5105e3c0-8bf6-45d7-8f82-c0f460ccc333)


Open

'D:\Program Files\Siemens\NX 11.0\UGOPEN\vs_files\VC#\CSharpProjects' 'NX11_VCS.vsz'

with notebook
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/fa0695e6-3bbc-4fe4-8e51-eb196422a5c1)

![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/eba26231-001e-429f-bb47-a4c1963eb7cf)

![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/e1f52102-5729-4cee-930d-d74c7edcf3dd)

2nd line
'Wizard=VsWizard.VsWizardEngine.11.0' -> 'Wizard=VsWizard.VsWizardEngine.11.0'


Open 'Visual Studio 2022'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/08295532-8a85-457d-baf2-90ad96655b8a)


Create a new proj -> choose 'Class Library(.NET Framework)'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/f652ea96-1476-4ae0-b7a2-596a2cfc8091)


rename proj name 'ClassLib1' to 'NXOPen_Test'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/3930860f-38ad-4c86-a843-338daa1fbd22)


![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/b4013522-d6a2-4f71-8c10-35a4da979563)


mouse right click 'add'->'reference'
select all
☑️'NXOpen.Guide.dll'
☑️'NXOpen.dll'
☑️'NXOpenUI.dll'
☑️'NXOpen.Utilities.dll'
☑️'NXOpenUF.dll'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/6b4c7739-533f-4b01-b9cf-a2b006a4b2bc)


![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/c5fcf063-7dd3-4ae4-94f0-5a36b9d9b7c1)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/ea510597-2884-4528-b205-9ca79e0dfd35)


right click 'properties'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/486b4b4d-7add-45b3-82a7-0df60bf16614)


![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/00877aff-6c1d-4038-abf1-90ae69960977)
'resources'->'resources files'
'browse'
'D:\Program Files\Siemens\NX 11.0\UGOPEN'
'Build Events'
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/764adcb3-d4c4-4554-aa6a-13a001865ce4)
""D:\Program Files\Siemens\NX 11.0\NXBIN" "$(TargetPath)""


addsigningresources
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/365542e7-bdf5-4d03-8c42-a84472195831)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/9ffbebe2-4bb6-44ab-96f9-741101268119)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/ab4eab16-4b1a-4665-a3f0-3c5d83f89d1e)


![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/e15cee79-0270-47bc-b778-856d37974d06)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/cf577554-a00b-4fc6-b50b-4e5ed79704de)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/836eaaa3-64ba-421a-aecd-bed7c68f6be3)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/267dc580-3b3f-4803-8f9f-c6ab04f3fef7)
![image](https://github.com/ChenxingWang93/Using-NX-Open-to-Improve-Workflows/assets/31954987/7d450466-bf03-4e45-a1db-2fea59dd81e8)


## Reference 参考
[](https://blog.csdn.net/Oskar_Lu/article/details/99136423?spm=1001.2014.3001.5502)
