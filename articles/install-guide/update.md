---
title: Ismerje meg, hogyan frissítheti a Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463277"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit frissítése (QDK)

Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.

Ez a cikk azt feltételezi, hogy már telepítette a QDK. Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).


## <a name="updating-q-projects"></a>Q # projektek frissítése 

1. Először telepítse a [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) legújabb verzióját, és futtassa a következő parancsot a parancssorban:
```bash
dotnet --version
```
 Ellenőrizze, hogy a kimenet 3.0.100-e vagy magasabb-e, majd kövesse az alábbi utasításokat a beállítástól függően.

### <a name="in-visual-studio"></a>Visual Studióban
 
 1. A Visual Studio 2019 legújabb verziójának frissítése [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) talál útmutatást.
 2. A megoldás megnyitása a Visual Studióban
 3. A menüben válassza a Build > tiszta megoldás elemet. 
 4. [Frissítse a cél keretrendszert](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) minden. csproj-fájlból a netcoreapp 3.0-ra (vagy netstandard 2.1-re, ha az egy könyvtáros projekt)
 5. A megoldásban lévő összes fájl mentése és lezárása
 6. Válassza az eszközök > parancssori > fejlesztői parancssor lehetőséget.
 7. A megoldás minden egyes projektje esetében futtassa a következő parancsot:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Ha a projektek más Microsoft. Quantum csomagokat használnak, ezeket is futtassa a parancs futtatásával. 
 8. Zárjuk be a parancssort, és válassza a Build > Build megoldás ( *ne válassza a* megoldás újraépítése lehetőséget, mivel az Újraépítés kezdetben sikertelen lesz)

### <a name="in-visual-studio-code"></a>A Visual Studio Code-ban

1. A Visual Studio Code-ban nyissa meg a frissíteni kívánt projektet tartalmazó mappát.
1. Válassza ki a Terminal > új terminált
1. Kövesse a parancssor használatával történő frissítésre vonatkozó utasításokat.

### <a name="using-the-command-line"></a>A parancssor használata

1. Navigáljon a projektfájlt tartalmazó mappára.
2. Futtassa az alábbi parancsot:
```bash
dotnet clean [project_name].csproj
```

3. [Frissítse a cél keretrendszert](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) minden. csproj-fájlból a netcoreapp 3.0-ra (vagy netstandard 2.1-re, ha az egy könyvtáros projekt)
4. Futtassa az alábbi parancsot:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
Ha a projekt más Microsoft. Quantum csomagokat használ, ezeket is futtassa a parancs futtatásával.

5. Az összes fájl mentése és lezárása
6. Ismételje meg a 1-4-et minden egyes projekt-függőség esetében, majd térjen vissza a fő projektet tartalmazó mappára, és futtassa a következőt:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>A Pythonhoz készült IQ # frissítése

1. A `iqsharp` kernel frissítése

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. A `iqsharp` verziójának ellenőrzése

    ```bash
    dotnet iqsharp --version
    ```

    A következő kimenetnek kell megjelennie:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. A `qsharp` csomag frissítése

    ```bash
    pip install qsharp --upgrade
    ```

1. A `qsharp` verziójának ellenőrzése

    ```bash
    pip show qsharp
    ```

    A következő kimenetnek kell megjelennie:

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Futtassa a következő parancsot a `.qs` fájlok helyéről
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.

## <a name="update-iq-for-jupyter-notebooks"></a>Az IQ # frissítése Jupyter-jegyzetfüzetekhez

1. A `iqsharp` kernel frissítése

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. A `iqsharp` verziójának ellenőrzése

    ```bash
    dotnet iqsharp --version
    ```

    A következő kimenetnek kell megjelennie:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Futtassa a következő parancsot a Jupyter Notebook egyik cellájából:
    ```
    %workspace reload
    ```

1. Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.

## <a name="update-visual-studio-qdk-extension"></a>A Visual Studio QDK bővítmény frissítése

1. A Q # Visual Studio bővítmény frissítése

    - A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit
    - A frissítés elfogadása

    > [!NOTE]
    > A Project-sablonokat a bővítménnyel együtt frissíti a rendszer. A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak. A meglévő projektek kódja nem frissül a bővítmény frissítésekor.

## <a name="update-vs-code-qdk-extension"></a>A VS Code QDK bővítmény frissítése

1. A Quantum VS Code bővítmény frissítése

    - Újraindítás VS Code
    - Navigáljon a **kiterjesztések** lapra
    - Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit
    - A bővítmény újratöltése

1. A Quantum Project-sablonok frissítése:

   - Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
   - Válassza a **Q #: Project-sablonok telepítése lehetőséget.**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, a `dotnet` parancssori eszköz használatával

1. A .NET-hez készült Quantum Project-sablonok frissítése

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Vajon mi a következő lépés?

Most, hogy frissítette a Quantum Development Kit-t az előnyben részesített környezetben, továbbra is fejlesztheti és futtathatja a kvantum-programokat. Ha még nem írt programot, megkezdheti [az első kvantum-program](xref:microsoft.quantum.write-program)megkezdését.
