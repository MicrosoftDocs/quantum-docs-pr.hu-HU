---
title: A Microsoft Quantum Development Kit (QDK) beállítása
description: Megismerheti a Microsoft Quantum Development Kit különböző környezetekben való beállítását.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228830"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit (QDK) beállítása

Ismerje meg a Microsoft Quantum Development Kit (QDK) saját környezetében történő beállításának módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek. A QDK a következőket tartalmazza:

- A Q# programozási nyelv
- Kódtárak, amelyek a Q# összetett funkcióit kivonatolják
- Pythonhoz és .NET-nyelvekhez (C#, F# és VB.NET) készült API-k a Q#-ban írt kvantumprogramok futtatásához
- A fejlesztést megkönnyítő eszközök

A Q#-programok futhatnak önálló alkalmazásként a Visual Studio Code vagy a Visual Studio használatával, vagy Jupyter-notebookokon keresztül az IQ# Jupyter kernellel, illetve egy Python vagy .NET nyelven írt (C#-, F#-) gazdaprogrammal párban. A Q#-programok az interneten is futtathatók [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) vagy [Docker](#use-the-qdk-with-docker) használatával. 

## <a name="options-for-setting-up-the-qdk"></a>A QDK beállításának lehetőségei

Háromféleképp használhatja a QDK-t:

- [A QDK helyi telepítése](#install-the-qdk-locally)
- [A QDK online használata](#use-the-qdk-online)
- [Egy QDK Docker-rendszerkép használata](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>A QDK helyi telepítése

Kifejleszthet egy Q#-kódot a kedvenc IDE-k többségében, valamint integrálhatja a Q#-t más nyelvekkel, például a Pythonnal és a .NET-tel (C#, F#).

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 vagy újabb)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><b>Visual Studio<br>(2019 vagy újabb)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter-notebookok</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Parancssor</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>Operációsrendszer-támogatás</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Csak Windowson</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>különálló Q#</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Telepítse</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# és Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Telepítse</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# és .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Telepítse</a></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a>A QDK online használata

A következő beállításokkal anélkül fejleszthet Q#-kódot, hogy bármit helyileg telepítene:

|Erőforrás|Előnyök|Korlátozások|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Gazdag online fejlesztési környezet  |Azure-előfizetés és -csomag szükséges hozzá |
|[**Binder**](xref:microsoft.quantum.install.binder) | Ingyenes online jegyzetfüzet-élmény |Nincs perzisztencia |

## <a name="use-the-qdk-with-docker"></a>A QDK használata Dockerrel

A QDK Docker-rendszerképünket használhatja a helyi Docker-telepítésében vagy a felhőben, bármely olyan szolgáltatáson keresztül, amely támogatja a Docker-rendszerképeket, mint például az ACI.

Innen letöltheti az IQ# Docker-rendszerképet: https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

A Dockert egy Visual Studio Code távoli fejlesztési tárolóval is használhatja a fejlesztési környezetek gyors meghatározásához. A VS Code fejlesztési tárolókkal kapcsolatos további tudnivalókért lásd: https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Következő lépések

Az egyes beállításokhoz tartozó munkafolyamatok leírása és összehasonlítása [A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs) című szakaszban olvasható.
