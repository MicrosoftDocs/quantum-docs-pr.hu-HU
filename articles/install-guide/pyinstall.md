---
title: 'Fejlesztés Q # és Python nyelven'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: a8c5b9c25c069f98ef8eefd6cfbc36bf3376931c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426367"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="47b31-102">Fejlesztés Q # és Python nyelven</span><span class="sxs-lookup"><span data-stu-id="47b31-102">Develop with Q# and Python</span></span>

<span data-ttu-id="47b31-103">Telepítse a QDK a Python-gazdagépek kifejlesztéséhez a Q # műveleteinek meghívásához.</span><span class="sxs-lookup"><span data-stu-id="47b31-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="47b31-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="47b31-104">Pre-requisites</span></span>

    - <span data-ttu-id="47b31-105">[Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="47b31-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="47b31-106">A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő</span><span class="sxs-lookup"><span data-stu-id="47b31-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="47b31-107">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="47b31-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="47b31-108">Telepítse a `qsharp` csomagot, amely egy Python-csomag, amely lehetővé teszi a Q # és a Python közötti együttműködési lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47b31-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="47b31-109">Telepítse az IQ #, a Jupyter és a Python által használt kernelt, amely a Q # műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.</span><span class="sxs-lookup"><span data-stu-id="47b31-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="47b31-110">Habár a Q #-t bármilyen IDE-ben használhatja a Python használatával, javasoljuk, hogy a Q # + Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t.</span><span class="sxs-lookup"><span data-stu-id="47b31-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="47b31-111">A Visual Studio Code és a QDK Visual Studio Code bővítmény használatával gazdagabb funkciókhoz férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="47b31-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="47b31-112">A [vs Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)</span><span class="sxs-lookup"><span data-stu-id="47b31-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="47b31-113">Telepítse a [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)-hoz készült QDK-bővítményt.</span><span class="sxs-lookup"><span data-stu-id="47b31-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="47b31-114">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="47b31-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="47b31-115">Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="47b31-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="47b31-116">Hozzon létre egy `hello_world.py` nevű Python-programot a Q# `SayHello()` műveletének meghívásához:</span><span class="sxs-lookup"><span data-stu-id="47b31-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="47b31-117">Futtassa a programot:</span><span class="sxs-lookup"><span data-stu-id="47b31-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="47b31-118">Ellenőrizze a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="47b31-118">Verify the output.</span></span> <span data-ttu-id="47b31-119">A program kimenetében a következő soroknak kell szerepelniük:</span><span class="sxs-lookup"><span data-stu-id="47b31-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="47b31-120">A Python Jupyter jegyzetfüzeteket is használhatja a klasszikus Python program írásához és a Q # műveletek a cellákból való meghívásához.</span><span class="sxs-lookup"><span data-stu-id="47b31-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="47b31-121">A Python-kód csak egy normál Python-program.</span><span class="sxs-lookup"><span data-stu-id="47b31-121">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47b31-122">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="47b31-122">Next steps</span></span>

<span data-ttu-id="47b31-123">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="47b31-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
