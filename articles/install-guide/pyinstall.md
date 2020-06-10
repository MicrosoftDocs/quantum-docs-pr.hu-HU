---
title: 'Fejlesztés Q # és Python nyelven'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630288"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="052a3-102">Fejlesztés Q # és Python nyelven</span><span class="sxs-lookup"><span data-stu-id="052a3-102">Develop with Q# and Python</span></span>

<span data-ttu-id="052a3-103">Telepítse a QDK a Python-gazdagépek kifejlesztéséhez a Q # műveleteinek meghívásához.</span><span class="sxs-lookup"><span data-stu-id="052a3-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="052a3-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="052a3-104">Prerequisites</span></span>

    - <span data-ttu-id="052a3-105">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="052a3-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="052a3-106">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="052a3-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="052a3-107">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="052a3-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="052a3-108">Telepítse a `qsharp` csomagot, amely egy Python-csomag, amely lehetővé teszi a Q # és a Python közötti együttműködési lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="052a3-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="052a3-109">Telepítse az IQ #, a Jupyter és a Python által használt kernelt, amely a Q # műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.</span><span class="sxs-lookup"><span data-stu-id="052a3-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="052a3-110">Ha a lépés során hibaüzenet jelenik `dotnet iqsharp install` meg, nyisson meg egy új Terminálablak-ablakot, és próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="052a3-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="052a3-111">Ha ez továbbra sem működik, próbálja meg megkeresni a telepített `dotnet-iqsharp` eszközt (Windows rendszeren `dotnet-iqsharp.exe` ), és futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="052a3-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="052a3-112">ahol a `/path/to/dotnet-iqsharp` fájlrendszerben lévő eszköz abszolút elérési útját kell cserélni `dotnet-iqsharp` .</span><span class="sxs-lookup"><span data-stu-id="052a3-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="052a3-113">Ez általában a `.dotnet/tools` felhasználói profil mappájában történik.</span><span class="sxs-lookup"><span data-stu-id="052a3-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="052a3-114">Habár a Q #-t bármilyen IDE-ben használhatja a Python használatával, javasoljuk, hogy a Q # + Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t.</span><span class="sxs-lookup"><span data-stu-id="052a3-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="052a3-115">A Visual Studio Code és a QDK Visual Studio Code bővítmény használatával gazdagabb funkciókhoz férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="052a3-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="052a3-116">A [vs Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)</span><span class="sxs-lookup"><span data-stu-id="052a3-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="052a3-117">Telepítse a [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)-hoz készült QDK-bővítményt.</span><span class="sxs-lookup"><span data-stu-id="052a3-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="052a3-118">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="052a3-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="052a3-119">Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="052a3-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="052a3-120">Hozzon létre egy `hello_world.py` nevű Python-programot a Q# `SayHello()` műveletének meghívásához:</span><span class="sxs-lookup"><span data-stu-id="052a3-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="052a3-121">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="052a3-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="052a3-122">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="052a3-122">Verify the output.</span></span> <span data-ttu-id="052a3-123">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="052a3-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="052a3-124">A Python Jupyter jegyzetfüzeteket is használhatja a klasszikus Python program írásához és a Q # műveletek a cellákból való meghívásához.</span><span class="sxs-lookup"><span data-stu-id="052a3-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="052a3-125">A Python-kód csak egy normál Python-program.</span><span class="sxs-lookup"><span data-stu-id="052a3-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="052a3-126">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="052a3-126">Next steps</span></span>

<span data-ttu-id="052a3-127">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="052a3-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
