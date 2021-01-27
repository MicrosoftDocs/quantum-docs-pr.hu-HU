---
title: Minta NWChem Quantum program
description: Egy NWChem bemeneti pakli használatával megtudhatja, hogyan számítja ki a kvantum-kémia szimulációjának kapuit.
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: e0ec7dcbdccbab5c81177a4223c71fd3f2ce57d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847774"
---
# <a name="end-to-end-with-nwchem"></a>Végponttól végpontig az NWChem-mel #

Ebből a cikkből megtudhatja, hogyan számítja ki a Quantum kémia szimulációját a [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) bemeneti paklitól kezdődően.
Mielőtt folytatná a példát, ellenőrizze, hogy telepítette-e a Docker-t a [telepítési és érvényesítési útmutatót](xref:microsoft.quantum.chemistry.concepts.installation)követve.

További információk:
- [NWChem bemeneti fedélzetek szerkezete](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Bemeneti fedélzeti parancsok a Quantum Development Kit használatával](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [A kémiai könyvtár és a függőségek telepítése](xref:microsoft.quantum.chemistry.concepts.installation)
- [Erőforrások számbavétele](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Ehhez a példához a Windows PowerShell Core rendszernek kell futnia.
> Töltse le a PowerShell Core for Windows, macOS vagy Linux rendszert a következő címen: https://github.com/PowerShell/PowerShell .

## <a name="importing-required-powershell-modules"></a>Szükséges PowerShell-modulok importálása ##

Ha még nem tette meg, akkor a [Microsoft/Quantum adattár](https://github.com/Microsoft/Quantum)klónozásával, amely mintákat és segédprogramokat tartalmaz a Quantum Development Kit használatával történő használathoz:

```powershell
git clone https://github.com/Microsoft/Quantum
```

A klónozás után `Microsoft/Quantum` végezze el `cd` a mappát, `utilities/` és importálja a PowerShell-modult a Docker és a NWChem használatához:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Alapértelmezés szerint a Windows meggátolja a parancsfájlok vagy modulok futtatását biztonsági mértékként.
> Ha engedélyezni szeretné, hogy a modulok `Invoke-NWChem.psm1` Windows rendszeren is futtathatók legyenek, előfordulhat, hogy módosítania kell a szabályzatot.
> Ehhez futtassa a következő `Set-ExecutionPolicy` parancsot:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> A rendszer a PowerShellből való kilépéskor visszaállít egy házirendet.
> Ha menteni szeretné a szabályzatot, a következőhöz hasonló értéket kell használnia `-Scope` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Ekkor a `Convert-NWChemToBroombridge` parancsnak elérhetőnek kell lennie:

```powershell
Get-Command -Module InvokeNWChem
```

Ezután importáljuk a `Get-GateCount` **GetGateCount** mintával megadott parancsot.
A részletekért tekintse meg a [minta utasításait](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).
Ezután futtassa a következőt, és a (z) vagy a (z), vagy rendszerre való helyettesítését az `<runtime>` `win10-x64` `osx-x64` `linux-x64` operációs rendszertől függően:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Ekkor a `Get-GateCount` parancsnak elérhetőnek kell lennie:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Bemeneti paklik ##

A NWChem-csomag egy _bemeneti pakli_ nevű szövegfájlt használ, amely meghatározza a szükséges kvantum-kémia problémát, valamint más paramétereket, például a memória-kiosztási beállításokat.
Ebben a példában a NWChem-hez készült előre elkészített bemeneti lapok egyikét fogjuk használni.
Először a [nwchemgit/nwchem adattár](https://github.com/nwchemgit/nwchem)klónozása:

> [!NOTE]
> Mivel ez egy nagyon nagy tárház, egy sekély klón segítségével takaríthat meg némi sávszélességet és lemezterületet az `--depth 1` argumentum használatával.
> Ez azonban nem kötelező.
> A klónozás csak hibátlanul fog működni `--depth 1` .

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

A `nwchemgit/nwchem` tárház számos olyan bemeneti paklit tartalmaz, amelyek a Quantum Development Kit használatával használhatók, és a [ `QA/chem_library_tests` mappa](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests)alatt találhatók.
Ebben a példában a `H4` bemeneti paklit fogjuk használni:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

A szóban forgó molekula egy 4 hidrogén atomból álló rendszer, amely egy adott geometriában, a `alpha` pakli nevében jelzett paramétertől függ `h4_sto6g_alpha.nw` . A H4 az 1970-es évek óta ismert [molekuláris teljesítményteszt](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) a számítási kémia számára. A paraméter azt `sto6g` jelzi, hogy a pakli egy, a Slater-típusú orbitális szolgáltatással kapcsolatos ábrázolást valósít meg, pontosabban egy 6 Gauss-alapú függvényekből álló, [Sto](https://en.wikipedia.org/wiki/STO-nG_basis_sets) -alapú, egy-egy példányra vonatkozó ábrázolást. Ez a bemeneti fedélzet emellett több, a NWChem-alapú TCE-kezelő motorra () vonatkozó útmutatást is tartalmaz, amely a Quantum Development Kit-vel való együttműködéshez szükséges információk előállításához nyújt közvetlen NWChem:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Broombridge-kimenet létrehozása és elkészítése a NWChem-ből ##

Most már mindent megtalál, amire szüksége lehet a Broombridge-dokumentumok létrehozásához és felhasználásához.
A NWChem futtatásához és a bemeneti paklihoz tartozó Broombridge-dokumentum létrehozásához futtassa a következőt `h4_sto6g_0.000.nw` `Convert-NWChemToBroombridge` :

> [!NOTE]
> A parancs első futtatásakor a Docker letölti a `nwchemorg/nwchem-qc` rendszerképet.
> Ez eltarthat egy kis ideig, a kapcsolódási sebességtől függően, akár egy csésze kávé beszerzésére is lehetőséget biztosít.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Ezzel létrehoz egy nevű Broombridge-dokumentumot, `h4_sto6g_0.000.yaml` amelyet a következővel használhat `Get-GateCount` :

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
- Próbálja ki a különböző előre megadott bemeneti paklikat, például a paramétert a `alpha` alkalmazásban `h4_sto6g_alpha.nw` , 
- A NWChem-paklik közvetlen szerkesztésével próbálja meg módosítani a paklikat, például az `STO-nG` n, különböző lehetőségeinek modelljeit. 
- Próbáljon ki más előre definiált NWChem bemeneti paklikat, amelyek a következő címen érhetők el: `nwchem/qa/chem_library_tests`
- Próbálja ki a NWChem-ból generált, előre definiált Broombridge YAML-teljesítménymutatókat, amelyek a [Microsoft/Quantum adattár](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)részeként érhetők el. Ezek a referenciaértékek a következők: 
    - kis molekulák, például molekuláris hidrogén (H2), berillium (be), lítium-hidrid (LiH),
    - nagyobb molekulák, mint például az ózon (O3), a béta-karotin, a citozin és sok más. 
- Próbálja ki a grafikus előtér- [EMSL nyilait](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , amelyek egy felületet biztosítanak a Microsoft Quantum Development Kithoz. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Broombridge-kimenet készítése EMSL-nyilakból ##

A web-alapú előtér-EMSL-nyilak megkezdéséhez navigáljon [ide](https://arrows.emsl.pnnl.gov/api/qsharp_chem)a böngészőben. 

> [!NOTE]
> A webböngészőben a EMSL-nyilak futtatásához engedélyezni kell a JavaScript használatát. Tekintse meg ezeket az [utasításokat](https://www.enable-javascript.com/) a JavaScript engedélyezéséhez a böngészőben. 

Először adjon meg egy molekulát a lekérdezési mezőben, amely azt írja: ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Több molekulát is megadhat a nyelvük neve szerint, például "koffein", "1, 3, 7 – trimethylxanthine" helyett. 

Ezután kattintson a következő gombra: ``theory{qsharp_chem}`` . Ezzel feltölti a lekérdezési mezőt egy olyan utasítással, amely közli a futtatással, hogy a Broombridge YAML formátumban exportálja a kimenetet. 

Most pedig az óra bekapcsolva ``Run Arrows`` . A bemenet méretétől függően ez hosszabb időt is igénybe vehet. Vagy ha az adott modellt korábban már kiszámítják, akkor rendkívül gyorsan elvégezhető, mivel csak egy adatbázisban lévő keresésre kerül sor. Mindkét esetben egy új oldalra kerül sor, amely rengeteg információt tartalmaz az adott NWChem a bemenet által megadott paklival szemben. 

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

Kattintson a ``download`` (z) elemre, amely egy olyan helyi másolatot ment egy egyedi fájlnévvel, mint például ``qsharp_chem48443.yaml`` (az egyes futtatások esetében az adott név eltérő lesz). Ezt a fájlt később is feldolgozhatja, például a következővel: 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
az erőforrások számának beolvasása. 

Használhatja a 3D-s molekula-szerkesztőt, amely elérhető a EMSL nyíl kezdőlapján található ``Arrows Entry - 3D Builder`` lapról. A megjelenített molekula [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D képére kattintva lehetővé válik a szerkesztés. Áthelyezheti az atomok körét, áthúzhatja az atomokat, hogy a molekuláris távolságok változása, az atomok hozzáadása/eltávolítása stb. A lekérdezési mezőbe való felvételük után a ``theory{qsharp_chem}`` BROOMBRIDGE YAML sémájának egy példányát létrehozhatja, és a kvantum-kémia könyvtár használatával tovább is vizsgálhatja. 
