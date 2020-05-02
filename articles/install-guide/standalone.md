---
title: 'Q # programok végrehajtása illesztőprogram és gazdagép nyelve nélkül'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706801"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="c6dd3-102">Q # parancssori alkalmazások</span><span class="sxs-lookup"><span data-stu-id="c6dd3-102">Q# Command Line Applications</span></span>

<span data-ttu-id="c6dd3-103">A Q # programok saját maguk is végrehajthatók a gazdagépen, például C#, F # vagy Python nyelven.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c6dd3-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c6dd3-104">Pre-requisites</span></span>

- [<span data-ttu-id="c6dd3-105">.NET Core SDK 3,1 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="c6dd3-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="c6dd3-106">Telepítés</span><span class="sxs-lookup"><span data-stu-id="c6dd3-106">Installation</span></span>

<span data-ttu-id="c6dd3-107">A Q # parancssori alkalmazásokat bármilyen IDE felépítheti, de a Q # alkalmazásaihoz kifejezetten ajánlott a Visual Studio Code (VS Code) vagy a Visual Studio IDE használata.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="c6dd3-108">A VS Code vagy a Visual Studio és a QDK Visual Studio Code bővítmény használatával gazdagabb funkciókhoz férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="c6dd3-109">A [vs Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)</span><span class="sxs-lookup"><span data-stu-id="c6dd3-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="c6dd3-110">A [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) -hoz készült QDK-bővítmény telepítése</span><span class="sxs-lookup"><span data-stu-id="c6dd3-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="c6dd3-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével</span><span class="sxs-lookup"><span data-stu-id="c6dd3-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="c6dd3-112">Töltse le és telepítse a [Visual Studio bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="c6dd3-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="c6dd3-113">Fejlesztés a Q # segítségével VS Code használatával</span><span class="sxs-lookup"><span data-stu-id="c6dd3-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="c6dd3-114">Telepítse a Quantum-projektsablonokat:</span><span class="sxs-lookup"><span data-stu-id="c6dd3-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="c6dd3-115">Ugrás a **View** -> **parancs-paletta** megtekintéséhez</span><span class="sxs-lookup"><span data-stu-id="c6dd3-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="c6dd3-116">Válassza a **Q #: Project-sablonok telepítése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="c6dd3-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="c6dd3-117">Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="c6dd3-118">Hozzon létre egy új projektet:</span><span class="sxs-lookup"><span data-stu-id="c6dd3-118">Create a new project:</span></span>
  - <span data-ttu-id="c6dd3-119">Ugrás a **View** -> **parancs-paletta** megtekintéséhez</span><span class="sxs-lookup"><span data-stu-id="c6dd3-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="c6dd3-120">Válassza a **Q #: új projekt létrehozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c6dd3-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="c6dd3-121">**Önálló konzolos alkalmazás** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="c6dd3-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="c6dd3-122">Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást</span><span class="sxs-lookup"><span data-stu-id="c6dd3-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="c6dd3-123">A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra</span><span class="sxs-lookup"><span data-stu-id="c6dd3-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="c6dd3-124">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="c6dd3-124">Inspect the project</span></span>
  - <span data-ttu-id="c6dd3-125">Látnia kell, hogy egy `Program.qs` létrehozott fájl egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="c6dd3-126">Futtassa az alkalmazást:</span><span class="sxs-lookup"><span data-stu-id="c6dd3-126">Run the application:</span></span>
  - <span data-ttu-id="c6dd3-127">Ugrás a **terminál** -> **új terminálra**</span><span class="sxs-lookup"><span data-stu-id="c6dd3-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="c6dd3-128">Be`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="c6dd3-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="c6dd3-129">A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c6dd3-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="c6dd3-130">A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="c6dd3-131">Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="c6dd3-132">Fejlesztés a Q # használatával a Visual Studióval</span><span class="sxs-lookup"><span data-stu-id="c6dd3-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="c6dd3-133">Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával</span><span class="sxs-lookup"><span data-stu-id="c6dd3-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="c6dd3-134">Hozzon létre egy új Q#-alkalmazást</span><span class="sxs-lookup"><span data-stu-id="c6dd3-134">Create a new Q# application</span></span>
  - <span data-ttu-id="c6dd3-135">Ugrás a **fájl** -> **új** -> **projektre**</span><span class="sxs-lookup"><span data-stu-id="c6dd3-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="c6dd3-136">A keresőmezőbe írja be a következőt: `Q#`</span><span class="sxs-lookup"><span data-stu-id="c6dd3-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="c6dd3-137">Válassza a **Q#-alkalmazás** elemet</span><span class="sxs-lookup"><span data-stu-id="c6dd3-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="c6dd3-138">Válassza a **tovább** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c6dd3-138">Select **Next**</span></span>
  - <span data-ttu-id="c6dd3-139">Válassza ki az alkalmazás nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="c6dd3-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="c6dd3-140">**Létrehozás** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="c6dd3-140">Select **Create**</span></span>

- <span data-ttu-id="c6dd3-141">Vizsgálja meg a projektet</span><span class="sxs-lookup"><span data-stu-id="c6dd3-141">Inspect the project</span></span>
  - <span data-ttu-id="c6dd3-142">Látnia kell, hogy egy nevű `Program.qs` fájl létre lett hozva, amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="c6dd3-143">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="c6dd3-143">Run the application</span></span>
  - <span data-ttu-id="c6dd3-144">Hibakeresési**kezdés kiválasztása hibakeresés nélkül** **Debug** -> </span><span class="sxs-lookup"><span data-stu-id="c6dd3-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="c6dd3-145">Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="c6dd3-146">Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c6dd3-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="c6dd3-147">A következő lépések</span><span class="sxs-lookup"><span data-stu-id="c6dd3-147">What's next?</span></span>

<span data-ttu-id="c6dd3-148">Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="c6dd3-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
