---
title: Fejlesztés Q#-pal és Pythonnal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274084"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="04203-102">Fejlesztés Q#-pal és Pythonnal</span><span class="sxs-lookup"><span data-stu-id="04203-102">Develop with Q# and Python</span></span>

<span data-ttu-id="04203-103">Telepítse a QDK-t a Python-gazdaprogramok fejlesztéséhez Q#-műveletek meghívása céljával.</span><span class="sxs-lookup"><span data-stu-id="04203-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="04203-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="04203-104">Prerequisites</span></span>

    - <span data-ttu-id="04203-105">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="04203-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="04203-106">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="04203-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="04203-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="04203-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="04203-108">Telepítse a `qsharp` Python-csomagot, amely lehetővé teszi a Q# és a Python közötti együttműködést.</span><span class="sxs-lookup"><span data-stu-id="04203-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="04203-109">Telepítse az IQ#-ot, amely a Jupyter és a Python által használt kernel, és a Q#-műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.</span><span class="sxs-lookup"><span data-stu-id="04203-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="04203-110">Ha hibaüzenetet kap a `dotnet iqsharp install` lépés során, nyisson meg egy új terminálablakot, és próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="04203-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="04203-111">Ha ez a lépés továbbra sem sikerül, keresse meg a telepített `dotnet-iqsharp` eszközt (Windows rendszeren: `dotnet-iqsharp.exe`), majd futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="04203-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="04203-112">ahol a `/path/to/dotnet-iqsharp` helyére a fájlrendszerben található `dotnet-iqsharp` eszközre mutató abszolút elérési útvonalat kell beírni.</span><span class="sxs-lookup"><span data-stu-id="04203-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="04203-113">Ez általában a `.dotnet/tools` területen található a felhasználó profil mappájában.</span><span class="sxs-lookup"><span data-stu-id="04203-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="04203-114">Bár a Q#-ot bármilyen IDE-ben használhatja a Pythonnal, határozottan javasoljuk, hogy Q#- és Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t.</span><span class="sxs-lookup"><span data-stu-id="04203-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="04203-115">A Visual Studio Code és a QDK Visual Studio Code-bővítmény használatával további funkciókhoz férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="04203-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="04203-116">A [VS Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)</span><span class="sxs-lookup"><span data-stu-id="04203-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="04203-117">Telepítse a [VS Code-hoz készült QDK-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="04203-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="04203-118">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="04203-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="04203-119">Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="04203-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="04203-120">Hozzon létre egy `hello_world.py` nevű Python-programot a Q# `SayHello()` műveletének meghívásához:</span><span class="sxs-lookup"><span data-stu-id="04203-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="04203-121">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="04203-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="04203-122">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="04203-122">Verify the output.</span></span> <span data-ttu-id="04203-123">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="04203-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="04203-124">Python Jupyter-notebookokat is használhat klasszikus Python programok írásához és Q#-műveletek cellákból való meghívásához.</span><span class="sxs-lookup"><span data-stu-id="04203-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="04203-125">A Python-kód csak egy szokásos Python-program.</span><span class="sxs-lookup"><span data-stu-id="04203-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04203-126">További lépések</span><span class="sxs-lookup"><span data-stu-id="04203-126">Next steps</span></span>

<span data-ttu-id="04203-127">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="04203-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
