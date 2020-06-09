---
title: A Quantum Development Kit (QDK) frissítése
description: 'Ismerteti, hogyan lehet frissíteni a Q #-projekteket és a Microsoft Quantum Development Kitt a jelenlegi verzióra.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 89db1a671767b0cc083a251918bbeeed2b39b883
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578181"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit frissítése (QDK)

Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.

Ez a cikk azt feltételezi, hogy már telepítette a QDK. Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).

Javasoljuk, hogy naprakészen tartson a legújabb QDK-kiadással. Ezt a frissítési útmutatót követve frissíthet a legújabb QDK-verzióra. A folyamat két részből áll:
1. Meglévő Q # fájlok és projektek frissítése a kód a frissített szintaxissal való igazításához.
2. A kiválasztott fejlesztési környezethez tartozó QDK frissítése.

## <a name="updating-q-projects"></a>Q # projektek frissítése 

Függetlenül attól, hogy C# vagy Python használatával üzemelteti a Q # műveleteit, kövesse ezeket az utasításokat a Q # projektjeinek frissítéséhez.

1. Először is győződjön meg arról, hogy rendelkezik a [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)legújabb verziójával. Futtassa a következő parancsot a parancssorban:

    ```dotnetcli
    dotnet --version
    ```

    Ellenőrizze a kimenetet `3.1.100` vagy a magasabbat. Ha nem, telepítse a [legújabb verziót](https://dotnet.microsoft.com/download) , és ellenőrizze újra. Ezután kövesse az alábbi utasításokat a beállítástól függően (Visual Studio, Visual Studio Code vagy közvetlenül a parancssorból).

### <a name="update-q-projects-in-visual-studio"></a>Q # projektek frissítése a Visual Studióban
 
1. Frissítsen a Visual Studio 2019 legújabb verziójára, [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) talál útmutatást.
2. Nyissa meg a megoldást a Visual Studióban.
3. Válassza a menü **Build**  ->  **tiszta megoldás**létrehozása elemét.
4. Az egyes. csproj-fájlokban frissítse a célként megadott keretrendszert `netcoreapp3.1` (vagy `netstandard2.1` Ha ez egy függvénytár-projekt).
    Az űrlap sorainak szerkesztése:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.

5. Az összes. csproj fájlban állítsa be az SDK-t az `Microsoft.Quantum.Sdk` alábbi sorban látható módon. Figyelje meg, hogy a verziószámnak a legújabb elérhetőnek kell lennie, és megtekintheti a [kibocsátási megjegyzések](https://docs.microsoft.com/quantum/relnotes/)áttekintésével.

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Mentse és zárjunk be minden fájlt a megoldásban.

7. Válassza az **eszközök**  ->  **parancssori**  ->  **fejlesztői parancssor**lehetőséget. Másik lehetőségként használhatja a csomagkezelő konzolt a Visual Studióban is.

8. A megoldás minden egyes projektje esetében futtassa a következő parancsot a csomag **eltávolításához** :

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Ha a projektek más Microsoft. Quantum vagy Microsoft. Azure. Quantum csomagokat használnak (pl. microsoft. Quantum. Numerikusok), futtassa az **Add** parancsot a következőhöz a használt verzió frissítéséhez.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Zárjuk be a parancssort, és válassza a **Build**  ->  **Build Solution** ( *ne* válassza az Újraépítés megoldást) lehetőséget.

Most már kihagyhatja a [Visual Studio QDK bővítmény frissítését](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Q # projektek frissítése a Visual Studio Code-ban

1. A Visual Studio Code-ban nyissa meg a frissíteni kívánt projektet tartalmazó mappát.
2. Válassza a **terminál**  ->  **új terminál**elemet.
3. Kövesse a parancssor használatával történő frissítéshez szükséges utasításokat (közvetlenül alább).

### <a name="update-q-projects-using-the-command-line"></a>Q # projektek frissítése a parancssor használatával

1. Navigáljon a fő projektfájlt tartalmazó mappához.

2. Futtassa az alábbi parancsot:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Határozza meg a QDK aktuális verzióját. A megkereséséhez tekintse át a [kibocsátási megjegyzéseket](https://docs.microsoft.com/quantum/relnotes/). A verzió formátuma a következőhöz hasonló lesz: `0.11.2006.207` .

4. Az egyes `.csproj` fájlokban végezze el a következő lépéseket:

    - Frissítse a célként megadott keretrendszert a `netcoreapp3.1` következőre: (vagy `netstandard2.1` Ha ez egy függvénytár-projekt). Az űrlap sorainak szerkesztése:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        A cél-keretrendszerek meghatározásáról [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)talál további információt.

    - Cserélje le az SDK-ra mutató hivatkozást a projekt definíciójában. Győződjön meg arról, hogy a verziószám a **3. lépésben**meghatározott értéknek felel meg.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Ha van, távolítsa el a csomagra mutató hivatkozást `Microsoft.Quantum.Development.Kit` , amely a következő bejegyzésben lesz meghatározva:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Frissítse az összes Microsoft Quantum-csomag verzióját a QDK legutóbb kiadott verziójára (a **3. lépésben**meghatározva). A csomagok neve a következő mintákkal történik:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        A csomagokra mutató hivatkozások formátuma a következő:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Mentse a módosított fájlt.

    - Állítsa vissza a projekt függőségeit a következő módon:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Váltson vissza a fő projektet tartalmazó mappára, és futtassa a következőt:

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

2. A `iqsharp` verzió ellenőrzése

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A következő kimenetnek kell megjelennie:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne aggódjon, ha a `iqsharp` verzió magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).

3. A `qsharp` csomag frissítése

    ```
    pip install qsharp --upgrade
    ```

4. A `qsharp` verzió ellenőrzése

    ```
    pip show qsharp
    ```

    A következő kimenetnek kell megjelennie:

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Futtassa a következő parancsot a fájlok helyéről `.qs`

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.

### <a name="update-iq-for-jupyter-notebooks"></a>Az IQ # frissítése Jupyter-jegyzetfüzetekhez

1. A `iqsharp` kernel frissítése

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. A `iqsharp` verzió ellenőrzése

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A kimenetnek az alábbihoz hasonlónak kell lennie:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne aggódjon, ha a `iqsharp` verzió magasabb, meg kell egyeznie a [legújabb kiadással](xref:microsoft.quantum.relnotes).

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

   - Ugrás a **View**  ->  **parancs-paletta** megtekintéséhez
   - Válassza a **Q #: Project-sablonok telepítése lehetőséget.**
   - Néhány másodperc elteltével be kell szereznie egy felugró ablakban, hogy a "Project templates telepítése sikeresen megtörtént"

### <a name="c-using-the-dotnet-command-line-tool"></a>C# a `dotnet` parancssori eszköz használatával

1. A .NET-hez készült Quantum Project-sablonok frissítése

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
