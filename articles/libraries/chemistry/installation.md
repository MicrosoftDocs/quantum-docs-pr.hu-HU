---
title: Kémia könyvtár telepítése és érvényesítése | Microsoft Docs
description: Kémiai könyvtárak telepítése és érvényesítése
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184202"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="2472c-103">Kémiai könyvtárak telepítése és érvényesítése</span><span class="sxs-lookup"><span data-stu-id="2472c-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="2472c-104">A Quantum Development Kit támogatást nyújt a Quantum kémia-alkalmazásokhoz a [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet-csomagon keresztül.</span><span class="sxs-lookup"><span data-stu-id="2472c-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="2472c-105">Ahogy a többi NuGet-csomag esetében is, a kémia könyvtára a projekthez is egyszerűen hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="2472c-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="2472c-106">**Visual Studio 2019:** Ha a Visual Studio 2019-at használja, a Quantum kémia-csomagokat a NuGet csomagkezelő használatával adhatja hozzá.</span><span class="sxs-lookup"><span data-stu-id="2472c-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="2472c-107">A csomagkezelő megnyitásához kattintson a jobb gombbal arra a projektre, amelyhez hozzá szeretné adni a kémiai könyvtárat, és válassza a "NuGet-csomagok kezelése..." lehetőséget az alábbi képernyőképen.</span><span class="sxs-lookup"><span data-stu-id="2472c-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="2472c-108">A Tallózás lapon keresse meg a "Microsoft. Quantum. kémia" nevű csomagot.</span><span class="sxs-lookup"><span data-stu-id="2472c-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="2472c-109">Győződjön meg arról, hogy az "előzetes kiadás belefoglalása" jelölőnégyzet be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="2472c-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="2472c-110">Ekkor megjelenik a letölthető csomagok listája.</span><span class="sxs-lookup"><span data-stu-id="2472c-110">This will list the packages available for download.</span></span>
<span data-ttu-id="2472c-111">Kattintson a "Microsoft. Quantum. kémia" elemre a bal oldali ablaktáblán, válassza ki a legújabb előzetes verziót a jobb oldali ablaktáblán, majd kattintson a telepítés gombra:</span><span class="sxs-lookup"><span data-stu-id="2472c-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="2472c-112">További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="2472c-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="2472c-113">Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a Quantum kémia függvénytárat a projekthez egy parancssori felülettel.</span><span class="sxs-lookup"><span data-stu-id="2472c-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="2472c-114">A Package Manager konzolon futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="2472c-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="2472c-115">További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="2472c-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="2472c-116">**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal adhat hozzá NuGet-csomagot a projekthez:</span><span class="sxs-lookup"><span data-stu-id="2472c-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="2472c-117">A telepítés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="2472c-117">Verifying Your Installation</span></span> 

<span data-ttu-id="2472c-118">A Quantum Development Kit többi részéhez hasonlóan a kvantum-kémia könyvtára számos teljesen dokumentált mintát tartalmaz, amelyek segítségével gyorsan megkezdheti a működést.</span><span class="sxs-lookup"><span data-stu-id="2472c-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="2472c-119">Ha tesztelni szeretné a telepítést ezen minták használatával, akkor a [fő minták tárházát](https://github.com/Microsoft/Quantum), majd futtassa az egyik mintát.</span><span class="sxs-lookup"><span data-stu-id="2472c-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="2472c-120">Például a [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) minta futtatásához:</span><span class="sxs-lookup"><span data-stu-id="2472c-120">For example, to run the [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="2472c-121">A Quantum kémiai könyvtár telepítésének ellenőrzése a Microsoft Visual Studio használatával a tárház klónozása után:</span><span class="sxs-lookup"><span data-stu-id="2472c-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="2472c-122">Nyissa meg a ChemistrySamples. SLN megoldást a kémia mappában.</span><span class="sxs-lookup"><span data-stu-id="2472c-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="2472c-123">Válassza a minták/1 elemet.</span><span class="sxs-lookup"><span data-stu-id="2472c-123">Select Samples/1.</span></span> <span data-ttu-id="2472c-124">Egyszerű molekulák/MolecularHydrogen indítási projektként.</span><span class="sxs-lookup"><span data-stu-id="2472c-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="2472c-125">Nyomja le az F5 billentyűt a molekuláris hidrogén Quantum fázisú becslési bemutató futtatásához.</span><span class="sxs-lookup"><span data-stu-id="2472c-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="2472c-126">Az energia szintjeinek becslésével kapcsolatos további információkért lásd: az [energia szintjének becslése](xref:microsoft.quantum.chemistry.examples.energyestimate) .</span><span class="sxs-lookup"><span data-stu-id="2472c-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="2472c-127">A Quantum Development Kit és a NWChem használata</span><span class="sxs-lookup"><span data-stu-id="2472c-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="2472c-128">A MolecularHydrogen minta manuálisan konfigurált molekuláris bemeneti adatokat használ.</span><span class="sxs-lookup"><span data-stu-id="2472c-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="2472c-129">Habár ez a kis példák esetében is jó, a kvantum-kémia méretének Hamiltonians millió vagy több milliárd kifejezéssel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="2472c-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="2472c-130">A skálázható számítási kémia csomagok által generált Hamiltonians túl nagyok a kézzel történő importáláshoz.</span><span class="sxs-lookup"><span data-stu-id="2472c-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="2472c-131">A Quantum Development Kit-hez készült Quantum kémiai könyvtár úgy lett kialakítva, hogy jól használható legyen a számítási kémia csomagjaival, a legtöbb esetben a környezeti molekuláris tudományok laboratóriuma által fejlesztett [**NWChem**](http://www.nwchem-sw.org/) számítási kémia platform ( EMSL) a Pacific Northwest nemzeti laboratóriumában.</span><span class="sxs-lookup"><span data-stu-id="2472c-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="2472c-132">A `Microsoft.Quantum.Chemistry` csomag különösen a [Broombridge-sémában](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)képviselt Quantum kémia-szimulációs problémák példányainak betöltésére szolgáló eszközöket biztosít, amelyeket a NWChem legújabb verziói is támogatnak.</span><span class="sxs-lookup"><span data-stu-id="2472c-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="2472c-133">A NWChem és a Quantum Development Kit együttes használatának megkezdéséhez a következő módszerek egyikét javasoljuk:</span><span class="sxs-lookup"><span data-stu-id="2472c-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="2472c-134">Ismerkedjen meg a [IntegralData/YAML-](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)ben a mintákhoz megadott meglévő Broombridge-fájlok használatával.</span><span class="sxs-lookup"><span data-stu-id="2472c-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="2472c-135">Használja a [EMSL Arrows Builder-t a Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) webalapú NWChem, amely új, Broombridge formátumú molekuláris bemeneti fájlok létrehozását eredményezi.</span><span class="sxs-lookup"><span data-stu-id="2472c-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="2472c-136">Használja a PNNL által biztosított [Docker-rendszerképet](https://hub.docker.com/r/nwchemorg/nwchem-qc/) a NWChem futtatásához, vagy</span><span class="sxs-lookup"><span data-stu-id="2472c-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="2472c-137">[Fordítsa](http://www.nwchem-sw.org/index.php/Compiling_NWChem) le a NWChem a platformhoz.</span><span class="sxs-lookup"><span data-stu-id="2472c-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="2472c-138">Tekintse meg a [NWChem teljes körű](xref:microsoft.quantum.chemistry.examples.endtoend) ismertetését a NWChem és a kémiai modellek használatáról a Quantum fejlesztés Kit kémiai könyvtárának elemzéséhez.</span><span class="sxs-lookup"><span data-stu-id="2472c-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="2472c-139">A mintákhoz megadott Broombridge-fájlok használatának első lépései</span><span class="sxs-lookup"><span data-stu-id="2472c-139">Getting started using Broombridge files provided with the samples</span></span>
<span data-ttu-id="2472c-140">A [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) mappa a Quantum Development Kit Samples adattárában a Broombridge-formázott molekula-adatfájlok szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="2472c-140">The [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="2472c-141">Egyszerű példaként használja a kémia könyvtár mintát, a [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) a Hamilton betöltéséhez az egyik Broombridge-fájlból, és hajtsa végre a Quantum szimulációs algorigthms a Gate becsléseit:</span><span class="sxs-lookup"><span data-stu-id="2472c-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="2472c-142">A Broombridge-séma által képviselt molekulák beírásával kapcsolatos további információkért lásd: [Hamilton letöltése fájlból](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="2472c-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="2472c-143">Az erőforrás-becsléssel kapcsolatos további információkért lásd: [erőforrás-számlálások beszerzése](xref:microsoft.quantum.chemistry.examples.resourcecounts) .</span><span class="sxs-lookup"><span data-stu-id="2472c-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="2472c-144">A EMSL Arrows Builder használatának első lépései</span><span class="sxs-lookup"><span data-stu-id="2472c-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="2472c-145">A EMSL Arrows egy olyan eszköz, amely NWChem és kémiai számítási adatbázisokat használ a molekula-adatforrások létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2472c-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="2472c-146">[A Microsoft Quantum Development Kit EMSL Arrows Builder](https://arrows.emsl.pnnl.gov/api/qsharp_chem) lehetővé teszi a modell megadását több molekuláris modell-építő használatával, és létrehozhatja a Quantum Development Kit által használandó Broombridge-adatfájlt.</span><span class="sxs-lookup"><span data-stu-id="2472c-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="2472c-147">A EMSL lapon kattintson a ["instuctions"] lapra, és kövesse a ["Simple examples"] utasításokat a Broombridge-fájlok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2472c-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="2472c-148">Ezután próbálja meg futtatni a ["GetGateCount"], hogy megtekintse az adott molekulák kvantum-erőforrásának becsült értékeit.</span><span class="sxs-lookup"><span data-stu-id="2472c-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="2472c-149">A NWChem telepítése a forrásból</span><span class="sxs-lookup"><span data-stu-id="2472c-149">Installing NWChem from Source</span></span>

<span data-ttu-id="2472c-150">A NWChem a forrásból történő telepítésével kapcsolatos teljes útmutatást a [PNNL biztosít](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="2472c-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="2472c-151">Ha a Windows 10 NWChem szeretné használni, a Linux rendszerhez készült Windows alrendszer nagyszerű megoldás.</span><span class="sxs-lookup"><span data-stu-id="2472c-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="2472c-152">Miután telepítette az [Ubuntu 18,04 LTS-et a Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)rendszerre, futtassa `ubuntu18.04` a kedvenc terminálról, és kövesse a fenti utasításokat a NWChem forrásról történő telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="2472c-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="2472c-153">Miután lefordította a NWChem a forrásból, futtathatja a NWChem által biztosított `yaml_driver`-parancsfájlt, hogy gyorsan Broombridge-példányokat hozzon létre a NWChem bemeneti fedélzetekről:</span><span class="sxs-lookup"><span data-stu-id="2472c-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="2472c-154">Ez a parancs egy új `input.yaml` fájlt hoz létre az aktuális könyvtárban lévő Broombridge formátumban.</span><span class="sxs-lookup"><span data-stu-id="2472c-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="2472c-155">A NWChem használata a Docker használatával</span><span class="sxs-lookup"><span data-stu-id="2472c-155">Using NWChem with Docker</span></span>

<span data-ttu-id="2472c-156">A NWChem használatához előre elkészített lemezképek a [Docker hub](https://hub.docker.com)-on keresztül érhetők el.</span><span class="sxs-lookup"><span data-stu-id="2472c-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="2472c-157">Az első lépésekhez kövesse a Docker telepítési utasításait a platformon:</span><span class="sxs-lookup"><span data-stu-id="2472c-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="2472c-158">Az Ubuntu Docker telepítése</span><span class="sxs-lookup"><span data-stu-id="2472c-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="2472c-159">A Docker telepítése macOS rendszerhez</span><span class="sxs-lookup"><span data-stu-id="2472c-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="2472c-160">A Windows 10-es Docker telepítése</span><span class="sxs-lookup"><span data-stu-id="2472c-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="2472c-161">Ha a Windowshoz a Docker-t használja, akkor meg kell osztania az ideiglenes könyvtárat tartalmazó meghajtót (ez általában a `C:\` meghajtó) a Docker-démon használatával.</span><span class="sxs-lookup"><span data-stu-id="2472c-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="2472c-162">További részletekért tekintse meg a [Docker dokumentációját](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="2472c-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="2472c-163">Miután telepítette a Docker-t, használhatja a Quantum Development Kit-mintákhoz biztosított PowerShell-modult a rendszerkép futtatásához, vagy manuálisan is futtathatja a rendszerképet.</span><span class="sxs-lookup"><span data-stu-id="2472c-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="2472c-164">Részletesen ismertetjük a PowerShellt. Ha manuálisan szeretné használni a Docker-rendszerképet, tekintse meg a [képhez mellékelt dokumentációt](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="2472c-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="2472c-165">NWChem futtatása a PowerShell Core használatával</span><span class="sxs-lookup"><span data-stu-id="2472c-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="2472c-166">Ha a NWChem Docker-rendszerképet a Quantum Development Kit használatával szeretné használni, egy kis PowerShell-modult biztosítunk, amely a NWChem-ben és a-ban lévő fájlok áthelyezését végzi.</span><span class="sxs-lookup"><span data-stu-id="2472c-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="2472c-167">Ha még nem telepítette a PowerShell Core-t, akkor a [githubon lévő PowerShell-tárházból](https://github.com/PowerShell/PowerShell#get-powershell)is letöltheti a platformfüggetlen platformot.</span><span class="sxs-lookup"><span data-stu-id="2472c-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="2472c-168">A PowerShell Core néhány minta esetében is használatos az adatelemzési és üzleti elemzési munkafolyamatokkal való együttműködés bemutatására.</span><span class="sxs-lookup"><span data-stu-id="2472c-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="2472c-169">Miután telepítette a PowerShell Core-t, importálja `InvokeNWChem.psm1` a NWChem parancsok elérhetővé tételéhez az aktuális munkamenetben:</span><span class="sxs-lookup"><span data-stu-id="2472c-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="2472c-170">Ezzel elérhetővé teszi a `Convert-NWChemToBroombridge` parancsot az aktuális PowerShell-munkamenetben.</span><span class="sxs-lookup"><span data-stu-id="2472c-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="2472c-171">Ha le szeretné tölteni az összes szükséges rendszerképet a Docker-ből, és használja őket a NWChem bemeneti fedélzetek futtatásához és a kimenet Broombridge való rögzítéséhez, futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="2472c-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="2472c-172">Ezzel létrehoz egy Broombridge-fájlt a NWChem `input.nw`-on való futtatásával.</span><span class="sxs-lookup"><span data-stu-id="2472c-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="2472c-173">Alapértelmezés szerint a Broombridge-kimenet neve és elérési útja megegyezik a bemeneti paklival, és a `.nw` kiterjesztést a `.yaml`váltja fel.</span><span class="sxs-lookup"><span data-stu-id="2472c-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="2472c-174">Ezt felülbírálhatja a `-DestinationPath` paraméter használatával `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="2472c-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="2472c-175">További információ a PowerShell beépített súgó funkciójának használatával érhető el:</span><span class="sxs-lookup"><span data-stu-id="2472c-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

