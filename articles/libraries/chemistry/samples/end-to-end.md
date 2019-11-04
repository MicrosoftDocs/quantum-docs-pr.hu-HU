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
# <a name="end-to-end-with-nwchem"></a>Végpontok közötti NWChem #

Ezen az oldalon egy példát láthatunk a kvantum-kémia szimulációjának lekérésére, amely egy [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) bemeneti pakliból indul.
Mielőtt folytatná a példát, ellenőrizze, hogy telepítette-e a Docker-t a [telepítési és érvényesítési útmutatót](xref:microsoft.quantum.chemistry.concepts.installation)követve.

További információ:
- [NWChem bemeneti fedélzetek szerkezete](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Bemeneti fedélzeti parancsok a Quantum Development Kit használatával](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [A kémiai könyvtár és a függőségek telepítése](xref:microsoft.quantum.chemistry.concepts.installation)
- [Erőforrások számbavétele](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Ehhez a példához a Windows PowerShell Core rendszernek kell futnia.
> Töltse le a Windows, macOS vagy Linux rendszerhez készült PowerShell Core-at https://github.com/PowerShell/PowerShell címen.

## <a name="importing-required-powershell-modules"></a>Szükséges PowerShell-modulok importálása ##

Ha még nem tette meg, akkor a [Microsoft/Quantum adattár](https://github.com/Microsoft/Quantum)klónozásával, amely mintákat és segédprogramokat tartalmaz a Quantum Development Kit használatával történő használathoz:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Miután klónozott `Microsoft/Quantum`, hajtsa végre `cd` a `utilities/` mappába, és importálja a PowerShell-modult a Docker és a NWChem használatához:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Alapértelmezés szerint a Windows meggátolja a parancsfájlok vagy modulok biztonsági mértékként való végrehajtását.
> Ahhoz, hogy a modulok, például a `Invoke-NWChem.psm1` futtathatók legyenek a Windows rendszeren, lehetséges, hogy módosítania kell a végrehajtási házirendet.
> Ehhez futtassa a `Set-ExecutionPolicy` parancsot:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Ekkor a rendszer visszaállít egy végrehajtási házirendet, amikor kilép a PowerShellből.
> Ha menteni szeretné a végrehajtási szabályzatot, használja a `-Scope`másik értékét:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Most már elérhető a `Convert-NWChemToBroombridge` parancs:

```powershell
Get-Command -Module InvokeNWChem
```

Ezután importáljuk a **GetGateCount** mintával megadott `Get-GateCount` parancsot.
A részletekért tekintse meg a [minta utasításait](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).
Ezután futtassa a következőt, a `<runtime>` az operációs rendszertől függően `win10-x64`, `osx-x64`vagy `linux-x64`.

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Most már elérhető a `Get-GateCount` parancs:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Bemeneti paklik ##

A NWChem-csomag egy _bemeneti pakli_ nevű szövegfájlt használ, amely meghatározza a szükséges kvantum-kémia problémát, valamint más paramétereket, például a memória-kiosztási beállításokat.
Ebben a példában a NWChem-hez készült előre elkészített bemeneti lapok egyikét fogjuk használni.
Először a [nwchemgit/nwchem adattár](https://github.com/nwchemgit/nwchem)klónozása:

> [!NOTE]
> Mivel ez egy nagyon nagy tárház, a `--depth 1` argumentum használatával egy sekély klónt is megtakaríthat a sávszélesség és a lemezterület megtakarítása érdekében.
> Ez azonban nem kötelező.
> A klónozás csak `--depth 1`nélkül fog működni.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

A `nwchemgit/nwchem` adattár számos különböző bemeneti paklival rendelkezik, amelyek a Quantum Development Kit használatával használhatók, és a [`QA/chem_library_tests` mappában](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)találhatók.
Ebben a példában a `H4` bemeneti paklit használjuk:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

A szóban forgó molekula egy 4 hidrogén atomból álló rendszer, amely egy adott geometriában van elrendezve, amely egy adott szögtől függ, a paraméter `alpha` a pakli neve `h4_sto6g_alpha.nw`. A H4 az 1970-es évek óta ismert [molekuláris teljesítményteszt](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) a számítási kémia számára. Az `sto6g` paraméter azt jelzi, hogy a pakli egy, a Slater típusú orbitális szolgáltatással kapcsolatos ábrázolást valósít meg, pontosabban egy 6 Gauss-alapú függvényekből álló, Sto-nG-alapú [készletre](https://en.wikipedia.org/wiki/STO-nG_basis_sets) vonatkozó ábrázolást. Ez a bemeneti fedélzet emellett több, a NWChem-alapú TCE-kezelő motorra () vonatkozó útmutatást is tartalmaz, amely a Quantum Development Kit-vel való együttműködéshez szükséges információk előállításához nyújt közvetlen NWChem:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Broombridge-kimenet létrehozása és elkészítése a NWChem-ből ##

Most már mindent meg kell Broombridge-dokumentumok létrehozásához és felhasználásához.
A NWChem futtatásához és a `h4_sto6g_0.000.nw` bemeneti paklihoz tartozó Broombridge-dokumentum létrehozásához futtassa a `Convert-NWChemToBroombridge`:

> [!NOTE]
> A parancs első futtatásakor a Docker letölti a `nwchemorg/nwchem-qc` rendszerképet.
> Ez eltarthat egy kis ideig, a kapcsolódási sebességtől függően, akár egy csésze kávé beszerzésére is lehetőséget biztosít.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Ezzel létrehoz egy `h4_sto6g_0.000.yaml` nevű Broombridge-dokumentumot, amelyet a `Get-GateCount`használatával használhat:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Ekkor látnia kell a konzol kimenetét, amely erőforrás-becslést tartalmaz, például a T-Count, a Forgások száma, a CNEM száma stb. különböző kvantum-szimulációs módszerekhez:

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

Itt számos dolgot tehet: 
- Különböző előre definiált bemeneti paklikat próbálhat ki, például a `h4_sto6g_alpha.nw``alpha` paraméterének megváltoztatásával 
- A NWChem-paklik közvetlen szerkesztésével próbálja meg módosítani a paklikat, például `STO-nG` modelleket a n, különböző 
- Próbáljon ki más előre definiált NWChem bemeneti paklikat, amelyek elérhetők a következő helyen: `nwchem/qa/chem_library_tests`,
- Próbálja ki a NWChem-ból generált, előre definiált Broombridge YAML-teljesítménymutatókat, amelyek a [Microsoft/Quantum adattár](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)részeként érhetők el. Ezek a referenciaértékek a következők: 
    - kis molekulák, például molekuláris hidrogén (H2), berillium (be), lítium-hidrid (LiH),
    - nagyobb molekulák, mint például az ózon (O3), a béta-karotin, a citozin és sok más. 
- Próbálja ki a grafikus előtér- [EMSL nyilait](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , amelyek egy felületet biztosítanak a Microsoft Quantum Development Kithoz. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Broombridge-kimenet készítése EMSL-nyilakból ##

A web-alapú előtér-EMSL-nyilak megkezdéséhez navigáljon [ide](https://arrows.emsl.pnnl.gov/api/qsharp_chem)a böngészőben. 

> [!NOTE]
> A webböngészőben a EMSL-nyilak futtatásához engedélyezni kell a JavaScript használatát. Tekintse meg ezeket az [utasításokat](https://www.enable-javascript.com/) a JavaScript engedélyezéséhez a böngészőben. 

Először adjon meg egy olyan molekulát a lekérdezési mezőben, amely a ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Több molekulát is megadhat a nyelvük neve szerint, például "koffein", "1, 3, 7 – trimethylxanthine" helyett. 

Ezután kattintson a ``theory{qsharp_chem}``t tartalmazó gombra. Ezzel feltölti a lekérdezési mezőt egy olyan utasítással, amely közli a futtatással, hogy a Broombridge YAML formátumban exportálja a kimenetet. 

Most ``Run Arrows``óra. A bemenet méretétől függően ez hosszabb időt is igénybe vehet. Vagy ha az adott modellt korábban már kiszámítják, akkor rendkívül gyorsan elvégezhető, mivel csak egy adatbázisban lévő keresésre kerül sor. Mindkét esetben egy új oldalra kerül sor, amely rengeteg információt tartalmaz az adott NWChem a bemenet által megadott paklival szemben. 

Töltse le és mentse a Broombridge YAML fájlt a következő fejléccel kezdődő szakaszból: 
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

Kattintson a ``download``elemre, amely egy egyedi fájlnévvel (például ``qsharp_chem48443.yaml``) menti a helyi másolatot (az adott név az egyes futtatások esetében eltérő lesz). Ezt a fájlt később is feldolgozhatja, például a következővel: 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
az erőforrások számának beolvasása. 

Használhatja a 3D molekula-szerkesztőt, amely a EMSL nyíl kezdőlapjának ``Arrows Entry - 3D Builder`` lapján érhető el. A megjelenített molekula [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D képére kattintva lehetővé válik a szerkesztés. Áthelyezheti az atomok körét, áthúzhatja az atomokat, hogy a molekuláris távolságok változása, az atomok hozzáadása/eltávolítása stb. Mindkét választási lehetőség esetében, miután hozzáadta ``theory{qsharp_chem}`` a lekérdezési mezőben, létrehozhatja a Broombridge YAML sémájának egy példányát, és további vizsgálatokat végezhet a Quantum kémia Library használatával. 
