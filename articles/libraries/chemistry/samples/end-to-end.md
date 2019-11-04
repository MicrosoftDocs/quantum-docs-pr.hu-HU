---
title: Végpontok közötti NWChem | Microsoft Docs
description: Végpontok közötti NWChem docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185817"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="d01a5-103">Végpontok közötti NWChem</span><span class="sxs-lookup"><span data-stu-id="d01a5-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="d01a5-104">Ezen az oldalon egy példát láthatunk a kvantum-kémia szimulációjának lekérésére, amely egy [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) bemeneti pakliból indul.</span><span class="sxs-lookup"><span data-stu-id="d01a5-104">In this page, we will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="d01a5-105">Mielőtt folytatná a példát, ellenőrizze, hogy telepítette-e a Docker-t a [telepítési és érvényesítési útmutatót](xref:microsoft.quantum.chemistry.concepts.installation)követve.</span><span class="sxs-lookup"><span data-stu-id="d01a5-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="d01a5-106">További információ:</span><span class="sxs-lookup"><span data-stu-id="d01a5-106">For more information:</span></span>
- [<span data-ttu-id="d01a5-107">NWChem bemeneti fedélzetek szerkezete</span><span class="sxs-lookup"><span data-stu-id="d01a5-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="d01a5-108">Bemeneti fedélzeti parancsok a Quantum Development Kit használatával</span><span class="sxs-lookup"><span data-stu-id="d01a5-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="d01a5-109">A kémiai könyvtár és a függőségek telepítése</span><span class="sxs-lookup"><span data-stu-id="d01a5-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="d01a5-110">Erőforrások számbavétele</span><span class="sxs-lookup"><span data-stu-id="d01a5-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="d01a5-111">Ehhez a példához a Windows PowerShell Core rendszernek kell futnia.</span><span class="sxs-lookup"><span data-stu-id="d01a5-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="d01a5-112">Töltse le a Windows, macOS vagy Linux rendszerhez készült PowerShell Core-at https://github.com/PowerShell/PowerShell címen.</span><span class="sxs-lookup"><span data-stu-id="d01a5-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="d01a5-113">Szükséges PowerShell-modulok importálása</span><span class="sxs-lookup"><span data-stu-id="d01a5-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="d01a5-114">Ha még nem tette meg, akkor a [Microsoft/Quantum adattár](https://github.com/Microsoft/Quantum)klónozásával, amely mintákat és segédprogramokat tartalmaz a Quantum Development Kit használatával történő használathoz:</span><span class="sxs-lookup"><span data-stu-id="d01a5-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="d01a5-115">Miután klónozott `Microsoft/Quantum`, hajtsa végre `cd` a `utilities/` mappába, és importálja a PowerShell-modult a Docker és a NWChem használatához:</span><span class="sxs-lookup"><span data-stu-id="d01a5-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="d01a5-116">Alapértelmezés szerint a Windows meggátolja a parancsfájlok vagy modulok biztonsági mértékként való végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="d01a5-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="d01a5-117">Ahhoz, hogy a modulok, például a `Invoke-NWChem.psm1` futtathatók legyenek a Windows rendszeren, lehetséges, hogy módosítania kell a végrehajtási házirendet.</span><span class="sxs-lookup"><span data-stu-id="d01a5-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="d01a5-118">Ehhez futtassa a `Set-ExecutionPolicy` parancsot:</span><span class="sxs-lookup"><span data-stu-id="d01a5-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="d01a5-119">Ekkor a rendszer visszaállít egy végrehajtási házirendet, amikor kilép a PowerShellből.</span><span class="sxs-lookup"><span data-stu-id="d01a5-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="d01a5-120">Ha menteni szeretné a végrehajtási szabályzatot, használja a `-Scope`másik értékét:</span><span class="sxs-lookup"><span data-stu-id="d01a5-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="d01a5-121">Most már elérhető a `Convert-NWChemToBroombridge` parancs:</span><span class="sxs-lookup"><span data-stu-id="d01a5-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="d01a5-122">Ezután importáljuk a **GetGateCount** mintával megadott `Get-GateCount` parancsot.</span><span class="sxs-lookup"><span data-stu-id="d01a5-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="d01a5-123">A részletekért tekintse meg a [minta utasításait](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="d01a5-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span></span>
<span data-ttu-id="d01a5-124">Ezután futtassa a következőt, a `<runtime>` az operációs rendszertől függően `win10-x64`, `osx-x64`vagy `linux-x64`.</span><span class="sxs-lookup"><span data-stu-id="d01a5-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="d01a5-125">Most már elérhető a `Get-GateCount` parancs:</span><span class="sxs-lookup"><span data-stu-id="d01a5-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="d01a5-126">Bemeneti paklik</span><span class="sxs-lookup"><span data-stu-id="d01a5-126">Input Decks</span></span> ##

<span data-ttu-id="d01a5-127">A NWChem-csomag egy _bemeneti pakli_ nevű szövegfájlt használ, amely meghatározza a szükséges kvantum-kémia problémát, valamint más paramétereket, például a memória-kiosztási beállításokat.</span><span class="sxs-lookup"><span data-stu-id="d01a5-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="d01a5-128">Ebben a példában a NWChem-hez készült előre elkészített bemeneti lapok egyikét fogjuk használni.</span><span class="sxs-lookup"><span data-stu-id="d01a5-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="d01a5-129">Először a [nwchemgit/nwchem adattár](https://github.com/nwchemgit/nwchem)klónozása:</span><span class="sxs-lookup"><span data-stu-id="d01a5-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="d01a5-130">Mivel ez egy nagyon nagy tárház, a `--depth 1` argumentum használatával egy sekély klónt is megtakaríthat a sávszélesség és a lemezterület megtakarítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="d01a5-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="d01a5-131">Ez azonban nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="d01a5-131">This is optional, however.</span></span>
> <span data-ttu-id="d01a5-132">A klónozás csak `--depth 1`nélkül fog működni.</span><span class="sxs-lookup"><span data-stu-id="d01a5-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="d01a5-133">A `nwchemgit/nwchem` adattár számos különböző bemeneti paklival rendelkezik, amelyek a Quantum Development Kit használatával használhatók, és a [`QA/chem_library_tests` mappában](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)találhatók.</span><span class="sxs-lookup"><span data-stu-id="d01a5-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="d01a5-134">Ebben a példában a `H4` bemeneti paklit használjuk:</span><span class="sxs-lookup"><span data-stu-id="d01a5-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="d01a5-135">A szóban forgó molekula egy 4 hidrogén atomból álló rendszer, amely egy adott geometriában van elrendezve, amely egy adott szögtől függ, a paraméter `alpha` a pakli neve `h4_sto6g_alpha.nw`.</span><span class="sxs-lookup"><span data-stu-id="d01a5-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="d01a5-136">A H4 az 1970-es évek óta ismert [molekuláris teljesítményteszt](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) a számítási kémia számára.</span><span class="sxs-lookup"><span data-stu-id="d01a5-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="d01a5-137">Az `sto6g` paraméter azt jelzi, hogy a pakli egy, a Slater típusú orbitális szolgáltatással kapcsolatos ábrázolást valósít meg, pontosabban egy 6 Gauss-alapú függvényekből álló, Sto-nG-alapú [készletre](https://en.wikipedia.org/wiki/STO-nG_basis_sets) vonatkozó ábrázolást.</span><span class="sxs-lookup"><span data-stu-id="d01a5-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="d01a5-138">Ez a bemeneti fedélzet emellett több, a NWChem-alapú TCE-kezelő motorra () vonatkozó útmutatást is tartalmaz, amely a Quantum Development Kit-vel való együttműködéshez szükséges információk előállításához nyújt közvetlen NWChem:</span><span class="sxs-lookup"><span data-stu-id="d01a5-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="d01a5-139">Broombridge-kimenet létrehozása és elkészítése a NWChem-ből</span><span class="sxs-lookup"><span data-stu-id="d01a5-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="d01a5-140">Most már mindent meg kell Broombridge-dokumentumok létrehozásához és felhasználásához.</span><span class="sxs-lookup"><span data-stu-id="d01a5-140">We now have everything we need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="d01a5-141">A NWChem futtatásához és a `h4_sto6g_0.000.nw` bemeneti paklihoz tartozó Broombridge-dokumentum létrehozásához futtassa a `Convert-NWChemToBroombridge`:</span><span class="sxs-lookup"><span data-stu-id="d01a5-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="d01a5-142">A parancs első futtatásakor a Docker letölti a `nwchemorg/nwchem-qc` rendszerképet.</span><span class="sxs-lookup"><span data-stu-id="d01a5-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="d01a5-143">Ez eltarthat egy kis ideig, a kapcsolódási sebességtől függően, akár egy csésze kávé beszerzésére is lehetőséget biztosít.</span><span class="sxs-lookup"><span data-stu-id="d01a5-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="d01a5-144">Ezzel létrehoz egy `h4_sto6g_0.000.yaml` nevű Broombridge-dokumentumot, amelyet a `Get-GateCount`használatával használhat:</span><span class="sxs-lookup"><span data-stu-id="d01a5-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that we can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="d01a5-145">Ekkor látnia kell a konzol kimenetét, amely erőforrás-becslést tartalmaz, például a T-Count, a Forgások száma, a CNEM száma stb. különböző kvantum-szimulációs módszerekhez:</span><span class="sxs-lookup"><span data-stu-id="d01a5-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="d01a5-146">Itt számos dolgot tehet:</span><span class="sxs-lookup"><span data-stu-id="d01a5-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="d01a5-147">Különböző előre definiált bemeneti paklikat próbálhat ki, például a `h4_sto6g_alpha.nw``alpha` paraméterének megváltoztatásával</span><span class="sxs-lookup"><span data-stu-id="d01a5-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="d01a5-148">A NWChem-paklik közvetlen szerkesztésével próbálja meg módosítani a paklikat, például `STO-nG` modelleket a n, különböző</span><span class="sxs-lookup"><span data-stu-id="d01a5-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="d01a5-149">Próbáljon ki más előre definiált NWChem bemeneti paklikat, amelyek elérhetők a következő helyen: `nwchem/qa/chem_library_tests`,</span><span class="sxs-lookup"><span data-stu-id="d01a5-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="d01a5-150">Próbálja ki a NWChem-ból generált, előre definiált Broombridge YAML-teljesítménymutatókat, amelyek a [Microsoft/Quantum adattár](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)részeként érhetők el.</span><span class="sxs-lookup"><span data-stu-id="d01a5-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="d01a5-151">Ezek a referenciaértékek a következők:</span><span class="sxs-lookup"><span data-stu-id="d01a5-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="d01a5-152">kis molekulák, például molekuláris hidrogén (H2), berillium (be), lítium-hidrid (LiH),</span><span class="sxs-lookup"><span data-stu-id="d01a5-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="d01a5-153">nagyobb molekulák, mint például az ózon (O3), a béta-karotin, a citozin és sok más.</span><span class="sxs-lookup"><span data-stu-id="d01a5-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="d01a5-154">Próbálja ki a grafikus előtér- [EMSL nyilait](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , amelyek egy felületet biztosítanak a Microsoft Quantum Development Kithoz.</span><span class="sxs-lookup"><span data-stu-id="d01a5-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="d01a5-155">Broombridge-kimenet készítése EMSL-nyilakból</span><span class="sxs-lookup"><span data-stu-id="d01a5-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="d01a5-156">A web-alapú előtér-EMSL-nyilak megkezdéséhez navigáljon [ide](https://arrows.emsl.pnnl.gov/api/qsharp_chem)a böngészőben.</span><span class="sxs-lookup"><span data-stu-id="d01a5-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="d01a5-157">A webböngészőben a EMSL-nyilak futtatásához engedélyezni kell a JavaScript használatát.</span><span class="sxs-lookup"><span data-stu-id="d01a5-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="d01a5-158">Tekintse meg ezeket az [utasításokat](https://www.enable-javascript.com/) a JavaScript engedélyezéséhez a böngészőben.</span><span class="sxs-lookup"><span data-stu-id="d01a5-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="d01a5-159">Először adjon meg egy olyan molekulát a lekérdezési mezőben, amely a ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="d01a5-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="d01a5-160">Több molekulát is megadhat a nyelvük neve szerint, például "koffein", "1, 3, 7 – trimethylxanthine" helyett.</span><span class="sxs-lookup"><span data-stu-id="d01a5-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="d01a5-161">Ezután kattintson a ``theory{qsharp_chem}``t tartalmazó gombra.</span><span class="sxs-lookup"><span data-stu-id="d01a5-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="d01a5-162">Ezzel feltölti a lekérdezési mezőt egy olyan utasítással, amely közli a futtatással, hogy a Broombridge YAML formátumban exportálja a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="d01a5-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="d01a5-163">Most ``Run Arrows``óra.</span><span class="sxs-lookup"><span data-stu-id="d01a5-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="d01a5-164">A bemenet méretétől függően ez hosszabb időt is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="d01a5-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="d01a5-165">Vagy ha az adott modellt korábban már kiszámítják, akkor rendkívül gyorsan elvégezhető, mivel csak egy adatbázisban lévő keresésre kerül sor.</span><span class="sxs-lookup"><span data-stu-id="d01a5-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="d01a5-166">Mindkét esetben egy új oldalra kerül sor, amely rengeteg információt tartalmaz az adott NWChem a bemenet által megadott paklival szemben.</span><span class="sxs-lookup"><span data-stu-id="d01a5-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="d01a5-167">Töltse le és mentse a Broombridge YAML fájlt a következő fejléccel kezdődő szakaszból:</span><span class="sxs-lookup"><span data-stu-id="d01a5-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="d01a5-168">Kattintson a ``download``elemre, amely egy egyedi fájlnévvel (például ``qsharp_chem48443.yaml``) menti a helyi másolatot (az adott név az egyes futtatások esetében eltérő lesz).</span><span class="sxs-lookup"><span data-stu-id="d01a5-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="d01a5-169">Ezt a fájlt később is feldolgozhatja, például a következővel:</span><span class="sxs-lookup"><span data-stu-id="d01a5-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="d01a5-170">az erőforrások számának beolvasása.</span><span class="sxs-lookup"><span data-stu-id="d01a5-170">to get resource counts.</span></span> 

<span data-ttu-id="d01a5-171">Használhatja a 3D molekula-szerkesztőt, amely a EMSL nyíl kezdőlapjának ``Arrows Entry - 3D Builder`` lapján érhető el.</span><span class="sxs-lookup"><span data-stu-id="d01a5-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="d01a5-172">A megjelenített molekula [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D képére kattintva lehetővé válik a szerkesztés.</span><span class="sxs-lookup"><span data-stu-id="d01a5-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="d01a5-173">Áthelyezheti az atomok körét, áthúzhatja az atomokat, hogy a molekuláris távolságok változása, az atomok hozzáadása/eltávolítása stb. Mindkét választási lehetőség esetében, miután hozzáadta ``theory{qsharp_chem}`` a lekérdezési mezőben, létrehozhatja a Broombridge YAML sémájának egy példányát, és további vizsgálatokat végezhet a Quantum kémia Library használatával.</span><span class="sxs-lookup"><span data-stu-id="d01a5-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
