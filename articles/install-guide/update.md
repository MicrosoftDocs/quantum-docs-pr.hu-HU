---
title: Ismerje meg, hogyan frissítheti a Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185851"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit frissítése (QDK)

Megtudhatja, hogyan frissítheti a Microsoft Quantum Development Kit (QDK) a legújabb verzióra.

Ez a cikk azt feltételezi, hogy már telepítette a QDK. Ha első alkalommal telepíti a rendszert, tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install).

A frissítési lépések a fejlesztési környezettől függenek. A következő fejezetekben válassza ki a környezetét.

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Mostantól a frissített QDK-verziót használhatja a meglévő kvantum-programok futtatásához.

## <a name="jupyter-notebooks"></a>Jupyter-notebookok

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Most már megnyithat egy meglévő Jupyter-jegyzetfüzetet, és futtathatja a frissített QDK.

## <a name="c-on-windows-using-visual-studio"></a>C#Windows rendszeren a Visual Studio használatával

1. A Q # Visual Studio bővítmény frissítése

    - A Visual Studio felszólítja, hogy fogadja el a [Quantum Visual Studio bővítmény](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) frissítéseit
    - A frissítés elfogadása

    > [!NOTE]
    > A Project-sablonokat a bővítménnyel együtt frissíti a rendszer. A frissített sablonok csak az újonnan létrehozott projektekre vonatkoznak. A meglévő projektek kódja nem frissül a bővítmény frissítésekor.

1. QDK-csomagok frissítése

    - Meglévő alkalmazás megnyitása
    - Válassza ki a **függőségeket** a megoldáskezelő
    - Válassza a **NuGet-csomagok kezelése** lehetőséget.
    - A **Microsoft. Quantum** csomagok frissítése a legújabb verzióra

1. Most már futtathatja az alkalmazást a legújabb QDK.

## <a name="c-using-vs-code"></a>C#, a VS Code használatával

1. A Quantum VS Code bővítmény frissítése

    - Újraindítás VS Code
    - Navigáljon a **kiterjesztések** lapra
    - Válassza ki a **Visual Studio Code** -bővítmény Microsoft Quantum Development Kit
    - A bővítmény újratöltése

1. A Quantum Project-sablonok frissítése:

   - Ugrás a -> **parancs-paletta** **megtekintése**
   - Válassza a **Q #: Project-sablonok telepítése lehetőséget.**

1. Meglévő alkalmazás megnyitása a VS Code-ban

   - A. csproj fájl szerkesztése az új csomag verzióinak hozzáadásához

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Ha más `Microsoft.Quantum` csomagokat használ, frissítse ezeket is.

1. Most már futtathatja az alkalmazást a frissített QDK

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, a `dotnet` parancssori eszköz használatával

1. A .NET-hez készült Quantum Project-sablonok frissítése

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Meglévő alkalmazás frissítése és futtatása

    - A QDK-csomag verzióinak frissítése az alkalmazásban

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Ha az alkalmazás más `Microsoft.Quantum` csomagokat használ, frissítse ezeket is.

    - Az alkalmazás futtatása

        ```bash
        dotnet run
        ```

    - Az alkalmazás az új csomag verziójával fog futni

## <a name="whats-next"></a>Vajon mi a következő lépés?

Most, hogy frissítette a Quantum Development Kit-t az előnyben részesített környezetben, továbbra is fejlesztheti és futtathatja a kvantum-programokat. Ha még nem írt programot, megkezdheti [az első kvantum-program](xref:microsoft.quantum.write-program)megkezdését.
