Это небольшое руководство по извлечению и изменению ресурсов или кода из игр, созданных с помощью движка Unity. Не стесняйтесь вносить свой вклад.

# Структура папок игры Unity
____
```
│   *.exe
└───*_Data
    │   globalgamemanagers
    │   globalgamemanagers.assets
    │   level0
    │   level0.resS
        ...
    |   levelN
    |   levelN.resS
    │   sharedassets0.assets
    │   sharedassets0.assets.resS
        ...
    |   sharedassetsN.assets
    |   sharedassetsN.assets.resS
    |   resources.assets
    ├───Managed
    │       Assembly-CSharp.dll
    │       Assembly-UnityScript.dll
    │       Mono.Security.dll
    │       mscorlib.dll
    │       System.Core.dll
    │       System.dll
    │       UnityEngine.dll
    │       UnityEngine.dll.mdb
    │       UnityEngine.Networking.dll
    │       UnityEngine.UI.dll
    ├───Mono
    │   │   mono.dll
    │   └───etc
    │       └───mono
    │           │   browscap.ini
    │           │   config
    │           ├───1.0
    │           │       DefaultWsdlHelpGenerator.aspx
    │           │       machine.config
    │           ├───2.0
    │           │   │   DefaultWsdlHelpGenerator.aspx
    │           │   │   machine.config
    │           │   │   settings.map
    │           │   │   web.config
    │           │   └───Browsers
    │           │           Compat.browser
    │           └───mconfig
    │                   config.xml
    └───Resources
            unity default resources
            unity_builtin_extra
            ```
            *: Имя выбрано при компиляции
            | Файл / каталог | Описание |
|----------------|:---------:|----------------:|
| *.Exe | Исполняемый файл игры |
| *_Data | Папка с данными, содержащая игровые ресурсы |
| level0-levelN | Файлы, содержащие данные игровых сцен, каждая сцена имеет свой файл |
| sharedassets0-sharedassetsN | 	Ресурсы игры разделены на общие ресурсы и файлы .resS. |
| resources.assets | Активы, найденные в папках ресурсов проекта, и их зависимости хранятся в этом файле. |
| Managed | 	Папка, содержащая библиотеки DLL Unity |
| Assembly-CSharp.dll | DLL-файл, содержащий скомпилированные файлы C # |
| Assembly-UnityScript.dll | DLL-файл, содержащий скомпилированные файлы UnityScript |

# Извлечение и редактирование кода
____
Файлы C # и UnityScript компилируются в библиотеки DLL Assembly-CSharp.dll и Assembly-UnityScript.dll соответственно, которые находятся в папке Managed.

[Библиотеки](http://ilspy.net/) DLL можно декомпилировать с помощью [ILSpy](http://ilspy.net/) или [dnSpy](https://github.com/0xd4d/dnSpy), которые позволяют изменять и перекомпилировать файлы сборки.

Если библиотеки DLL отсутствуют в управляемом каталоге, попробуйте сбросить их с помощью этого инструмента [MegaDumper.](https://github.com/CodeCracker-Tools/MegaDumper).

# Извлечение активов
____
Активы хранятся в файлах .assets и .resS. Содержимое этих файлов можно распаковать одним из следующих инструментов:
            | Инструмент | Описание |
|----------------|:---------:|----------------:|
| [UtinyRipper](https://github.com/mafaca/UtinyRipper) | uTinyRipper - это инструмент для извлечения ресурсов из сериализованных файлов (CAB- *, * .assets, .sharedAssets и т. д.) и пакетов ресурсов ( .unity3d, * .assetbundle и т. д.) и преобразования их в собственный формат Engine. |
| *_Data | Папка с данными, содержащая игровые ресурсы |
| level0-levelN | Файлы, содержащие данные игровых сцен, каждая сцена имеет свой файл |
| sharedassets0-sharedassetsN | 	Ресурсы игры разделены на общие ресурсы и файлы .resS. |
| resources.assets | Активы, найденные в папках ресурсов проекта, и их зависимости хранятся в этом файле. |
| Managed | 	Папка, содержащая библиотеки DLL Unity |
| Assembly-CSharp.dll | DLL-файл, содержащий скомпилированные файлы C # |
| Assembly-UnityScript.dll | DLL-файл, содержащий скомпилированные файлы UnityScript |
