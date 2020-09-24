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
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834482"
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

|&nbsp; | **VS Code<br>(2019 vagy újabb verzió)**| **Visual Studio<br>(2019 vagy újabb verzió)** | **Jupyter-notebookok** | **Parancssor**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**OS** |Windows, macOS, Linux |Csak Windowson |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**különálló Q#** |<br>[Telepítse](xref:microsoft.quantum.install.standalone) |<br> [Telepítse](xref:microsoft.quantum.install.standalone)  |<br> [Telepítse](xref:microsoft.quantum.install.jupyter) |<br>[Telepítse](xref:microsoft.quantum.install.standalone)|
|**Q# és Python** |[Telepítse](xref:microsoft.quantum.install.python) |[Telepítse](xref:microsoft.quantum.install.python) |[Telepítse](xref:microsoft.quantum.install.jupyter) |[Telepítse](xref:microsoft.quantum.install.python) |
|**Q# és .NET (C#, F#)**|[Telepítse](xref:microsoft.quantum.install.cs) |[Telepítse](xref:microsoft.quantum.install.cs)|&#10006; |[Telepítse](xref:microsoft.quantum.install.cs) |

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
