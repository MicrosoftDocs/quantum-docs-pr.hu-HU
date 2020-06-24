---
title: 'Microsoft Q # kémia könyvtár telepítése és érvényesítése'
description: Ismerje meg, hogyan telepítheti a Microsoft Quantum kémia-függvénytárat, és hogyan használhatja a NWChem számítási kémia platformon.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275176"
---
# <a name="chemistry-library-installation-and-validation"></a>Kémiai könyvtárak telepítése és érvényesítése

A Quantum Development Kit támogatást nyújt a Quantum kémia-alkalmazásokhoz a [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet-csomagban.
Ahogy a többi NuGet-csomag esetében is, a kémia könyvtára a projekthez is egyszerűen hozzáadható.

**Visual Studio 2019:** Ha a Visual Studio 2019-at használja, a Quantum kémia-csomagokat a NuGet csomagkezelő használatával adhatja hozzá.
A csomagkezelő megnyitásához kattintson a jobb gombbal arra a projektre, amelyhez hozzá szeretné adni a kémiai könyvtárat, és válassza a "NuGet-csomagok kezelése..." lehetőséget az alábbi képernyőképen.

![A NuGet Package Manager használata a Visual Studio 2019-ben](~/media/vs2017-nuget-manage-packages.png)

A Tallózás lapon keresse meg a "Microsoft. Quantum. kémia" nevű csomagot.

> [!NOTE]
> Győződjön meg arról, hogy az "előzetes kiadás belefoglalása" jelölőnégyzet be van jelölve.

![Előzetes kiadás jelölőnégyzetének belefoglalása](~/media/vs2017-nuget-package-search.png)

Ekkor megjelenik a letölthető csomagok listája.
Kattintson a "Microsoft. Quantum. kémia" elemre a bal oldali ablaktáblán, válassza ki a legújabb előzetes verziót a jobb oldali ablaktáblán, majd kattintson a telepítés gombra:

![A legújabb Microsoft. Quantum. Kémiá csomag telepítése](~/media/vs2017-nuget-select-chem.png)

További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a Quantum kémia függvénytárat a projekthez egy parancssori felülettel.

![A Package Manager konzol használata a parancssorból](~/media/vs2017-nuget-console-menu.png)

A Package Manager konzolon futtassa a következőt:

```
Install-Package Microsoft.Quantum.Chemistry
```

További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal adhat hozzá NuGet-csomagot a projekthez:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>A telepítés ellenőrzése 

A Quantum Development Kit többi részéhez hasonlóan a kvantum-kémia könyvtára számos teljesen dokumentált mintát tartalmaz, amelyek segítségével gyorsan megkezdheti a működést.
Ha tesztelni szeretné a telepítést ezen minták használatával, akkor a [fő minták tárházát](https://github.com/Microsoft/Quantum), majd futtassa az egyik mintát.  A minta futtatásához például [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

A Quantum kémiai könyvtár telepítésének ellenőrzése a Microsoft Visual Studio használatával a tárház klónozása után:
    1. Nyissa meg a ChemistrySamples. SLN megoldást a kémia mappában.  
    2. Válassza a minták/1 elemet. Egyszerű molekulák/MolecularHydrogen indítási projektként.
    3. Nyomja le az F5 billentyűt a molekuláris hidrogén Quantum fázisú becslési bemutató futtatásához.

Az energia szintjeinek becslésével kapcsolatos további információkért lásd: az [energia szintjének becslése](xref:microsoft.quantum.chemistry.examples.energyestimate) .   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>A Quantum Development Kit és a NWChem használata ##

A MolecularHydrogen minta manuálisan konfigurált molekuláris bemeneti adatokat használ.  Habár ez a kis példák esetében is jó, a kvantum-kémia méretének Hamiltonians millió vagy több milliárd kifejezéssel kell rendelkeznie. A skálázható számítási kémia csomagok által generált Hamiltonians túl nagyok a kézzel történő importáláshoz. 

A Quantum Development Kit-hez készült Quantum kémiai könyvtár úgy lett kialakítva, hogy jól használható legyen a számítási kémia csomagjaival, leginkább a [**NWChem**](http://www.nwchem-sw.org/) számítási kémia platformját, amelyet a környezeti molekuláris tudományok laboratóriuma (EMSL) fejlesztett ki a csendes-óceáni országos laboratóriumban.
Különösen a `Microsoft.Quantum.Chemistry` csomag eszközöket biztosít a [Broombridge-sémában](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)képviselt Quantum kémia-szimulációs problémák példányainak betöltéséhez, amelyet a NWChem legújabb verziói is támogatnak.

A NWChem és a Quantum Development Kit együttes használatának megkezdéséhez a következő módszerek egyikét javasoljuk:
- Ismerkedjen meg a [IntegralData/YAML-](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)ben a mintákhoz megadott meglévő Broombridge-fájlok használatával.
- Használja a [EMSL Arrows Builder-t a Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) webalapú NWChem, amely új, Broombridge formátumú molekuláris bemeneti fájlok létrehozását eredményezi.  
- Használja a PNNL által biztosított [Docker-rendszerképet](https://hub.docker.com/r/nwchemorg/nwchem-qc/) a NWChem futtatásához, vagy
- [Fordítsa](http://www.nwchem-sw.org/index.php/Compiling_NWChem) le a NWChem a platformhoz.

Tekintse meg a [NWChem teljes körű](xref:microsoft.quantum.chemistry.examples.endtoend) ismertetését a NWChem és a kémiai modellek használatáról a Quantum fejlesztés Kit kémiai könyvtárának elemzéséhez.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>A mintákhoz megadott Broombridge-fájlok használatának első lépései

A [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) mappa a Quantum Development Kit Samples adattárában a Broombridge-formázott molekula-adatfájlok szerepelnek.  

Egyszerű példaként használja a kémia könyvtár mintát, a [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) a Hamilton betöltéséhez az egyik Broombridge-fájlból, és hajtsa végre a Quantum szimulációs algorigthms a Gate becsléseit:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

A Broombridge-séma által képviselt molekulák beírásával kapcsolatos további információkért lásd: [Hamilton letöltése fájlból](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Az erőforrás-becsléssel kapcsolatos további információkért lásd: [erőforrás-számlálások beszerzése](xref:microsoft.quantum.chemistry.examples.resourcecounts) .  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>A EMSL Arrows Builder használatának első lépései

A EMSL Arrows egy olyan eszköz, amely NWChem és kémiai számítási adatbázisokat használ a molekula-adatforrások létrehozásához.  [A Microsoft Quantum Development Kit EMSL Arrows Builder](https://arrows.emsl.pnnl.gov/api/qsharp_chem) lehetővé teszi a modell megadását több molekuláris modell-építő használatával, és létrehozhatja a Quantum Development Kit által használandó Broombridge-adatfájlt.  

A EMSL lapon kattintson a ["instuctions"] lapra, és kövesse a ["Simple examples"] utasításokat a Broombridge-fájlok létrehozásához.  Ezután próbálja meg futtatni a ["GetGateCount"], hogy megtekintse az adott molekulák kvantum-erőforrásának becsült értékeit.

### <a name="installing-nwchem-from-source"></a>A NWChem telepítése a forrásból

A NWChem a forrásból történő telepítésével kapcsolatos teljes útmutatást a [PNNL biztosít](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Ha a Windows 10 NWChem szeretné használni, a Linux rendszerhez készült Windows alrendszer nagyszerű megoldás.
> Miután telepítette az [Ubuntu 18,04 LTS for Windows rendszert](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), futtassa a `ubuntu18.04` kedvenc terminálját, és kövesse a fenti utasításokat a NWChem forrásról való telepítéséhez.

Miután lefordította a NWChem a forrásból, futtathatja a `yaml_driver` NWChem által biztosított parancsfájlt, hogy gyorsan Broombridge példányokat hozzon létre a NWChem bemeneti fedélzetekről:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Ez a parancs egy új fájlt hoz létre `input.yaml` az aktuális könyvtárban lévő Broombridge formátumban.

### <a name="using-nwchem-with-docker"></a>A NWChem használata a Docker használatával

A NWChem használatához előre elkészített lemezképek a [Docker hub](https://hub.docker.com)-on keresztül érhetők el.
Az első lépésekhez kövesse a Docker telepítési utasításait a platformon:

- [Az Ubuntu Docker telepítése](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [A Docker telepítése macOS rendszerhez](https://docs.docker.com/docker-for-mac/install/)
- [A Windows 10-es Docker telepítése](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Ha a Windowshoz a Docker-t használja, meg kell osztania az ideiglenes könyvtárat tartalmazó meghajtót (ez általában a `C:\` meghajtó) a Docker-démon használatával. További részletekért tekintse meg a [Docker dokumentációját](https://docs.docker.com/docker-for-windows/#shared-drives) .

Miután telepítette a Docker-t, használhatja a Quantum Development Kit-mintákhoz biztosított PowerShell-modult a rendszerkép futtatásához, vagy manuálisan is futtathatja a rendszerképet.
Részletesen ismertetjük a PowerShellt. Ha manuálisan szeretné használni a Docker-rendszerképet, tekintse meg a [képhez mellékelt dokumentációt](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>NWChem futtatása a PowerShell Core használatával

Ha a NWChem Docker-rendszerképet a Quantum Development Kit használatával szeretné használni, egy kis PowerShell-modult biztosítunk, amely a NWChem-ben és a-ban lévő fájlok áthelyezését végzi.
Ha még nem telepítette a PowerShell Core-t, akkor a [githubon lévő PowerShell-tárházból](https://github.com/PowerShell/PowerShell#get-powershell)is letöltheti a platformfüggetlen platformot.

> [!NOTE]
> A PowerShell Core néhány minta esetében is használatos az adatelemzési és üzleti elemzési munkafolyamatokkal való együttműködés bemutatására.

Miután telepítette a PowerShell Core-t, importálja az alkalmazást a `InvokeNWChem.psm1` NWChem parancsok elérhetővé tételéhez az aktuális munkamenetben:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Ezzel `Convert-NWChemToBroombridge` elérhetővé válik a parancs az aktuális PowerShell-munkamenetben.
Ha le szeretné tölteni az összes szükséges rendszerképet a Docker-ből, és használja őket a NWChem bemeneti fedélzetek futtatásához és a kimenet Broombridge való rögzítéséhez, futtassa a következőt:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Ezzel létrehoz egy Broombridge-fájlt a NWChem futtatásával `input.nw` .
Alapértelmezés szerint a Broombridge-kimenet neve és elérési útja megegyezik a bemeneti paklival, és a `.nw` bővítmény a helyére kerül `.yaml` .
Ezt felülbírálhatja a `-DestinationPath` paraméter használatával `Convert-NWChemToBroombridge` .
További információ a PowerShell beépített súgó funkciójának használatával érhető el:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
