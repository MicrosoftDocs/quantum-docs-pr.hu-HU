---
title: Ismerje meg, hogyan frissítheti a Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036310"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit frissítése (QDK)

Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.

Ez a cikk azt feltételezi, hogy már telepítette a QDK. Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).

Javasoljuk, hogy naprakészen tartson a legújabb QDK-kiadással. Ezt a frissítési útmutatót követve frissíthet a legújabb QDK-verzióra. A folyamat két részből áll:
1. meglévő Q # fájlok és projektek frissítése a kód a frissített szintaxissal való igazításához
2. saját maga frissítése a választott fejlesztési környezet QDK 

## <a name="updating-q-projects"></a>Q # projektek frissítése 

Függetlenül attól, hogy a (z C# ) vagy a Python használatával üzemelteti a q # műveleteit, kövesse ezeket az utasításokat a q # projektjeinek frissítéséhez.

1. Először is győződjön meg arról, hogy rendelkezik a [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)legújabb verziójával. Futtassa a következő parancsot a parancssorban:

    ```dotnetcli
    dotnet --version
    ```

    Ellenőrizze, hogy a kimenet `3.1.100` vagy magasabb-e. Ha nem, telepítse a [legújabb verziót](https://dotnet.microsoft.com/download) , és ellenőrizze újra. Ezután kövesse az alábbi utasításokat a beállítástól függően (Visual Studio, Visual Studio Code vagy közvetlenül a parancssorból).

### <a name="update-q-projects-in-visual-studio"></a>Q # projektek frissítése a Visual Studióban
 
1. A Visual Studio 2019 legújabb verziójának frissítése [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) talál útmutatást.
2. A megoldás megnyitása a Visual Studióban
3. A menüben válassza a **Build** -> **tiszta megoldás** elemet.
4. A. csproj-fájlok mindegyikében frissítse a célként megadott keretrendszert, hogy `netcoreapp3.0` (vagy `netstandard2.1`, ha a könyvtári projekt).
    Az űrlap sorainak szerkesztése:

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.
5. A megoldásban lévő összes fájl mentése és lezárása
6. Válassza az **eszközök** -> **parancssori** -> **fejlesztői parancssor** lehetőséget.
7. A megoldás minden egyes projektje esetében futtassa a következő parancsot:

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Ha a projektek más Microsoft. Quantum csomagokat használnak (például Microsoft. Quantum. Numerikusok), futtassa a parancsot ezekre is.
8. A parancssor bezárásához és a **build** -> **Build megoldás** *kiválasztásához (ne válassza az* Újraépítés megoldás lehetőséget)

Most már kihagyhatja a [Visual Studio QDK bővítmény frissítését](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Q # projektek frissítése a Visual Studio Code-ban

1. A Visual Studio Code-ban nyissa meg a frissíteni kívánt projektet tartalmazó mappát.
2. Válassza ki a **terminal** -> **új terminált**
3. Kövesse a parancssor használatával történő frissítéshez szükséges utasításokat (közvetlenül alább)

### <a name="update-q-projects-using-the-command-line"></a>Q # projektek frissítése a parancssor használatával

1. Navigáljon a projektfájlt tartalmazó mappára.
2. Futtassa az alábbi parancsot:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. A. csproj-fájlok mindegyikében frissítse a célként megadott keretrendszert, hogy `netcoreapp3.0` (vagy `netstandard2.1`, ha a könyvtári projekt).
    Az űrlap sorainak szerkesztése:

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.
4. Futtassa az alábbi parancsot:

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Ha a projekt más Microsoft. Quantum csomagokat (például Microsoft. Quantum. numerikus értékeket) használ, futtassa a parancsot ezekre is.
5. Mentse és zárjunk be minden fájlt.
6. Ismételje meg a 1-4-et minden egyes projekt-függőség esetében, majd térjen vissza a fő projektet tartalmazó mappára, és futtassa a következőt:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Ha már frissítette a Q #-projektjeit, kövesse az alábbi utasításokat a QDK frissítéséhez.

## <a name="updating-the-qdk"></a>A QDK frissítése

A QDK frissítésének folyamata a fejlesztési nyelvtől és környezettől függően változhat.
Válassza ki az alábbi fejlesztési környezetet.

* [Python: az IQ # bővítmény frissítése](#update-iq-for-python)
* [Jupyter jegyzetfüzetek: az IQ # bővítmény frissítése](#update-iq-for-jupyter-notebooks)
* [Visual Studio: a QDK bővítmény frissítése](#update-visual-studio-qdk-extension)
* [VS code: a QDK bővítmény frissítése](#update-vs-code-qdk-extension)
* [Parancssor és C#: Project-sablonok frissítése](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>A Pythonhoz készült IQ # frissítése

1. A `iqsharp` kernel frissítése 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. A `iqsharp` verziójának ellenőrzése

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A következő kimenetnek kell megjelennie:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne aggódjon, ha a `iqsharp` verziója magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).

3. A `qsharp` csomag frissítése

    ```bash
    pip install qsharp --upgrade
    ```

4. A `qsharp` verziójának ellenőrzése

    ```bash
    pip show qsharp
    ```

    A következő kimenetnek kell megjelennie:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Futtassa a következő parancsot a `.qs` fájlok helyéről

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.

### <a name="update-iq-for-jupyter-notebooks"></a>Az IQ # frissítése Jupyter-jegyzetfüzetekhez

1. A `iqsharp` kernel frissítése

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. A `iqsharp` verziójának ellenőrzése

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A kimenetnek az alábbihoz hasonlónak kell lennie:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne aggódjon, ha a `iqsharp` verziója magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).

3. Futtassa a következő parancsot a Jupyter Notebook egyik cellájából:

    ```
    %workspace reload
    ```

4. Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.

### <a name="update-visual-studio-qdk-extension"></a>A Visual Studio QDK bővítmény frissítése

1. A Q # Visual Studio bővítmény frissítése

    - A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit
    - A frissítés elfogadása

    > [!NOTE]
    > A Project-sablonokat a bővítménnyel együtt frissíti a rendszer. A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak. A meglévő projektek kódja nem frissül a bővítmény frissítésekor.

### <a name="update-vs-code-qdk-extension"></a>A VS Code QDK bővítmény frissítése

1. A Quantum VS Code bővítmény frissítése

    - Újraindítás VS Code
    - Navigáljon a **kiterjesztések** lapra
    - Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit
    - A bővítmény újratöltése

2. A Quantum Project-sablonok frissítése:

   - Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
   - Válassza a **Q #: Project-sablonok telepítése lehetőséget.**
   - Néhány másodperc elteltével be kell szereznie egy felugró ablakban, hogy a "Project templates telepítése sikeresen megtörtént"

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, a `dotnet` parancssori eszköz használatával

1. A .NET-hez készült Quantum Project-sablonok frissítése

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>A következő lépések

Most, hogy frissítette a Quantum Development Kit-t az előnyben részesített környezetben, továbbra is fejlesztheti és futtathatja a kvantum-programokat. Ha még nem írt programot, megkezdheti [az első kvantum-program](xref:microsoft.quantum.write-program)megkezdését.
