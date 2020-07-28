---
title: A Quantum Development Kit (QDK) frissítése
description: Ismerteti, hogyan frissítheti Q#-projektjeit és a Microsoft Quantum Development Kitet az aktuális verzióra.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 69b83997773896583258a4996a61b6f334edf407
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871399"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit (QDK) frissítése

Ismerje meg, hogy frissítheti a Microsoft Quantum Development Kitet (QDK) a legújabb verzióra.

A cikk feltételezi, hogy már telepítette a QDK-t. Ha most telepíti először, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).

Azt javasoljuk, hogy mindig a QDK legújabb kiadását használja. A QDK legújabb verziójára való frissítéshez kövesse ezt a frissítési útmutatót. A folyamat két részből áll:
1. A meglévő Q#-fájlok és -projektek frissítéséből, hogy a kód az összes frissített szintaxisnak megfeleljen.
2. A QDK a kiválasztott fejlesztési környezethez történő frissítéséből.

## <a name="updating-q-projects"></a>Q#-projektek frissítése 

Függetlenül attól, hogy a C#-ot vagy Pythont használ a Q#-műveleteihez, kövesse ezeket az utasításokat a Q#-projektek frissítéséhez.

1. Először is ellenőrizze, hogy a [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) legújabb verzióját használja-e. Futtassa az alábbi parancsot a parancssorban:

    ```dotnetcli
    dotnet --version
    ```

    Győződjön meg arról, hogy a kimenet `3.1.100` vagy nagyobb. Ha nem, telepítse a [legújabb verziót](https://dotnet.microsoft.com/download), és ellenőrizze még egyszer. Ezután a környezetétől (Visual Studio, Visual Studio Code vagy közvetlenül a parancssor) függően kövesse az alábbi utasításokat.

### <a name="update-q-projects-in-visual-studio"></a>Q#-projektek frissítése a Visual Studióban
 
1. Frissítés a Visual Studio 2019 legújabb verziójára – a kapcsolódó utasításokat [itt](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) találja.
2. Nyissa meg a megoldást a Visual Studióban.
3. A menüben válassza a **Build (Létrehozás)**  -> **Clean Solution (Megoldás eltávolítása)** elemet.
4. A .csproj-fájlok mindegyikében frissítse a célkeretrendszert a következőre: `netcoreapp3.1` (kódtárprojekt esetén a következőre: `netstandard2.1`).
    Szerkessze az űrlap sorait:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    A célkeretrendszer megadásáról további információt [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) talál.

5. A .csproj-fájlok mindegyikében, az alábbi sorban látható módon állítsa be az SDK-t a következőre: `Microsoft.Quantum.Sdk`. Vegye figyelembe, hogy a verziószámnak a legfrissebb elérhető verziónak kell lennie, amelyet a [kibocsátási megjegyzések](https://docs.microsoft.com/quantum/relnotes/) áttekintésével állapíthat meg.

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. Mentsen, majd zárja be a megoldás összes fájlját.

7. Válassza a **Tools (Eszközök)**  -> **Command Line (Parancssor)**  -> **Developer Command Prompt (Fejlesztői parancssor)** lehetőséget. Használhatja a Visual Studio csomagkezelési konzolját is.

8. A megoldásban található összes projekt esetében az alábbi parancs futtatásával **távolítsa el** ezt a csomagot:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Ha a projektek más Microsoft.Quantum- vagy Microsoft.Azure.Quantum-csomagot is használnak (pl. Microsoft.Quantum.Numerics), futtassa az **add** parancsot az általuk használt verzió frissítéséhez.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Zárja be a parancssort, és válassza a **Build (Létrehozás)**  -> **Build Solution (Megoldás létrehozása)** lehetőséget (*ne* a Rebuild Solution (Megoldás újrafordítása) lehetőséget válassza).

Most már továbbléphet a [Visual Studio QDK-bővítmény frissítéséhez](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Q#-projektek frissítése a Visual Studio Code-ban

1. Nyissa meg a frissíteni kívánt projektet tartalmazó mappát a Visual Studio Code-ban.
2. Válassza a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** lehetőséget.
3. Kövesse a parancssor használatával történő frissítéshez tartozó utasításokat (közvetlenül ez alatt látható).

### <a name="update-q-projects-using-the-command-line"></a>Q#-projektek frissítése a parancssor használatával

1. Nyissa meg a fő projektfájlt tartalmazó mappát.

2. Futtassa az alábbi parancsot:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Állapítsa meg a QDK aktuális verzióját. Ehhez tekintse meg a [kibocsátási megjegyzéseket](https://docs.microsoft.com/quantum/relnotes/). A verzió formátuma a következőhöz hasonló: `0.12.20072031`.

4. Minden `.csproj`-fájl esetében hajtsa végre a következő lépéseket:

    - Frissítse célkeretrendszert a következőre: `netcoreapp3.1` (kódtárprojekt esetén a következőre: `netstandard2.1`). Szerkessze az űrlap sorait:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        A célkeretrendszer megadásáról további információt [itt](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) talál.

    - Cserélje le az SDK hivatkozását a projekt definíciójában. Ellenőrizze, hogy a verziószám megfelel-e a **3. lépésben** megadott értéknek.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - Távolítsa el a `Microsoft.Quantum.Development.Kit` csomagra mutató hivatkozást (ha van ilyen), amely a következő bejegyzésben található:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Frissítse az összes Microsoft Quantum-csomag verzióját a QDK legfrissebb kiadott verziójára (amelyet a **3. lépésben** állapított meg). Ezen csomagok elnevezése a következő mintát követi:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        A csomaghivatkozások formátuma:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - Mentse a módosított fájlt.

    - Az alábbiak elvégzésével állítsa vissza a projekt függőségeit:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Lépjen vissza a fő projektfájlt tartalmazó mappához, majd futtassa a következőt:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

A Q#-projektek frissítése után kövesse az alábbi utasításokat a QDK frissítéséhez.

## <a name="updating-the-qdk"></a>A QDK frissítése

A QDK frissítési folyamata a fejlesztési nyelvtől és a környezettől függ.
A lenti listából válassza ki a fejlesztőkörnyezetet.

* [Python: frissítse a(z) `qsharp` csomagot](#update-the-qsharp-python-package)
* [Jupyter-notebookok: frissítse az IQ#-kernelt](#update-the-iq-jupyter-kernel)
* [Visual Studio: a QDK-bővítmény frissítése](#update-visual-studio-qdk-extension)
* [VS Code: a QDK-bővítmény frissítése](#update-vs-code-qdk-extension)
* [Parancssor és C#: projektsablonok frissítése](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>A(z) `qsharp` Python-csomag frissítése

A frissítési eljárás attól függ, hogy a telepítést eredetileg a Conda vagy a .NET CLI és a pip használatával végezte.

#### <a name="update-using-conda-recommended"></a>[Frissítés a Conda használatával (ajánlott)](#tab/tabid-conda)

1. Aktiválja azt a Conda-környezetet, amelyben a(z) `qsharp` csomagot telepítette, majd futtassa a következő parancsot a frissítéséhez:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Futtassa az alábbi parancsot a(z) `.qs`-fájlok helyéről:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Frissítés a .NET CLI és a pip használatával (haladó)](#tab/tabid-dotnetcli)

1. Frissítse az `iqsharp` kernelt 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ellenőrizze az `iqsharp` verzióját

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A következő kimenetnek kell megjelennie:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Ne aggódjon, ha a(z) `iqsharp` verziószáma nagyobb. Annak meg kell egyeznie a(z) [legújabb kiadással](xref:microsoft.quantum.relnotes).

1. Frissítse a(z) `qsharp` csomagot:

    ```
    pip install qsharp --upgrade
    ```

1. Ellenőrizze a(z) `qsharp` verzióját:

    ```
    pip show qsharp
    ```

    A következő kimenetnek kell megjelennie:

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Futtassa az alábbi parancsot a(z) `.qs`-fájlok helyéről:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

Most már használhatja a frissített `qsharp` Python-csomagot a meglévő kvantumprogramok futtatásához.

### <a name="update-the-iq-jupyter-kernel"></a>Az IQ# Jupyter kernel frissítése

A frissítési eljárás attól függ, hogy a telepítést eredetileg a Conda vagy a .NET CLI és a pip használatával végezte.

#### <a name="update-using-conda-recommended"></a>[Frissítés a Conda használatával (ajánlott)](#tab/tabid-conda)

1. Aktiválja azt a Conda-környezetet, amelyben a(z) `qsharp` csomagot telepítette, majd futtassa a következő parancsot a frissítéséhez:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Futtassa az alábbi parancsot valamennyi meglévő Q# Jupyter-notebook egy-egy cellájából:

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Frissítés a .NET CLI és a pip használatával (haladó)](#tab/tabid-dotnetcli)

1. Frissítse a(z) `Microsoft.Quantum.IQSharp` csomagot:

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ellenőrizze a(z) `iqsharp` verzióját:

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A kimenet az alábbihoz hasonló lesz:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Ne aggódjon, ha a(z) `iqsharp` verziószáma nagyobb. Annak meg kell egyeznie a(z) [legújabb kiadással](xref:microsoft.quantum.relnotes).

1. Futtassa az alábbi parancsot valamennyi meglévő Q# Jupyter-notebook egy-egy cellájából:

    ```
    %workspace reload
    ```

***

Most már használhatja a frissített IQ# kernelt a meglévő Q# Jupyter-notebookok futtatásához.

### <a name="update-visual-studio-qdk-extension"></a>A Visual Studio QDK-bővítmény frissítése

1. Frissítse Q# Visual Studio-bővítményt

    - A Visual Studio arra kéri, hogy fogadja a [Quantum Visual Studio-bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit
    - Fogadja el a frissítést

    > [!NOTE]
    > A rendszer frissíti a projektsablonokat a bővítménnyel. A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak. A meglévő projektek kódja nem frissül a bővítmény frissítésekor.

### <a name="update-vs-code-qdk-extension"></a>A VS Code QDK-bővítmény frissítése

1. Frissítse a Quantum VS Code-bővítményt

    - Indítsa újra a VS Code-ot
    - Lépjen a **Bővítmények** lapra
    - Válassza a **Visual Studio Code-hoz készült Microsoft Quantum Development Kit** bővítményt
    - Töltse be újból a bővítményt

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, a `dotnet` parancssori eszköz használatával

1. Frissítse a .NET-hez tartozó Quantum-projektsablonokat

    A parancssorból:

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   Ha a parancssori sablonokat is használni szeretné, és már telepítve van a VS Code QDK-bővítmény, a projektsablonokat magából a bővítményből is frissítheti:

   - [A QDK-bővítmény frissítése](#update-vs-code-qdk-extension)
   - A VS Code-ban lépjen a **View** -> **Command Palette** (Nézet > Parancskatalógus) lehetőséghez
   - Válassza a **Q#: Install command line project templates** (Q#: Parancssori projektsablonok telepítése)
   - Néhány másodperc elteltével megjelenik a projektsablonok sikeres telepítésének megerősítését tartalmazó felugró ablak
