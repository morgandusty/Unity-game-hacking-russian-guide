![alt text](https://sun9-39.userapi.com/c858124/v858124980/21a91f/OD1WAGT1LEs.jpg)
Это небольшое руководство по извлечению и изменению ресурсов или кода из игр, созданных с помощью движка Unity. Не стесняйтесь вносить свой вклад.

1. [Структура папок игры Unity](#unity-game-folder-structure)
2. [Извлечение и редактирование кода](#extracting-and-editing-code)
3. [Извлечение активов](#extracting-assets)
4. [Взлом памяти](#hacking-memory)

## Структура папок игры Unity

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

\* : имя было выбрано при компиляциии

File/Directory | Description
--- | ---
*.exe | Исполняемый файл игры
*_Data | Папка с данными, содержащая игровые ресурсы
level0-levelN | Файлы, содержащие данные игровых сцен, каждая сцена имеет свой файл
sharedassets0-sharedassetsN | Ресурсы игры разделены на общие ресурсы и файлы .resS. и это бесит :/
resources.assets | Активы, найденные в папках ресурсов проекта, и их зависимости хранятся в этом файле.
Managed | Папка, содержащая библиотеки DLL Unity
Assembly-CSharp.dll | DLL-файл, содержащий скомпилированные файлы C #
Assembly-UnityScript.dll | DLL-файл, содержащий скомпилированные файлы UnityScript

## Извлечение и редактирование кода

Файлы C # и UnityScript компилируются в библиотеки DLL Assembly-CSharp.dll и Assembly-UnityScript.dll соответственно, которые находятся в папке Managed.

DLL можно декомпилировать с помощью [ILSpy](http://ilspy.net/) или [dnSpy](https://github.com/0xd4d/dnSpy) которые позволяют изменять и перекомпилировать файлы сборки.

Если библиотеки DLL отсутствуют в управляемом каталоге, попробуйте сбросить их с помощью этого инструмента [MegaDumper](https://github.com/CodeCracker-Tools/MegaDumper)

## Извлечение активов

Активы хранятся в файлах .assets и .resS. Содержимое этих файлов можно распаковать одним из следующих инструментов :

Tool | Description
--- | ---
[UtinyRipper](https://github.com/mafaca/UtinyRipper) | uTinyRipper - это инструмент для извлечения ресурсов из сериализованных файлов (CAB- *, * .assets, .sharedAssets и т. д.) и пакетов ресурсов ( .unity3d, * .assetbundle и т. д.) и преобразования их в собственный формат Engine.
[Unity Studio](https://github.com/RaduMC/UnityStudio) | Инструмент для исследования, извлечения и экспорта ресурсов из игр и приложений Unity.
[Unity Assets Bundle Extractor](https://7daystodie.com/forums/showthread.php?22675-Unity-Assets-Bundle-Extractor) | UABE - это инструмент, который позволяет изменять файл ресурсов и извлекать ресурсы в пригодных для использования форматах (png / tga для текстур, obj для сеток).
[Unity Assets Explorer](http://zenhax.com/viewtopic.php?f=9&t=36) | Может извлекать текстуры в формат .DDS, сетки в формат .43.
[QuickBMS](http://aluigi.altervista.org/quickbms.htm) with [this script](http://aluigi.altervista.org/bms/unity.bms) or [this one for webplayer](http://aluigi.org/papers/bms/unity3d_webplayer.bms) |

#### Файлы DDS :

В [DDS](https://en.wikipedia.org/wiki/DirectDraw_Surface) файлы могут быть открыты / перекодировано / отредактирован с этим [gimp plugin](http://registry.gimp.org/node/70) или с этим [photoshop plugin](https://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop).

#### Другой способ извлечения сеток и текстур :

Используйте [3D Ripper DX](http://www.deep-shadows.com/hax/3DRipperDX.htm) (не поддерживает 64-битные двоичные файлы) или [Ninja Ripper](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/).

## Взлом памяти

У cheat-engine есть функция [Dissect mono](https://wiki.cheatengine.org/index.php?title=Mono) которая может помочь взломать память игры. Это видео [video series](https://www.youtube.com/playlist?list=PLNffuWEygffbue0tvx7IusDmfAthqmgS7) об использовании чит-движка действительно полезно.


# [АВТОР ГИТА](https://vk.com/dobrov.sergey)
