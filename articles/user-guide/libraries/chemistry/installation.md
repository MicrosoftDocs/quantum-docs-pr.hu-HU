---
title: Microsoft Q# kémiai könyvtár telepítése
description: Ismerje meg, hogyan telepítheti a Microsoft Quantum kémia-függvénytárat, és hogyan használhatja a NWChem számítási kémia platformon.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
no-loc:
- Q#
- $$v
ms.openlocfilehash: f1a7d1d041dab73980d8debc179d6c79acac6d33
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759799"
---
# <a name="chemistry-library-installation"></a>Kémiai könyvtár telepítése

A [ **MolecularHydrogen** minta](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) manuálisan konfigurált molekuláris bemeneti adatokat használ.
Habár ez a kis példák esetében is jó, a kvantum-kémia méretének Hamiltonians millió vagy több milliárd kifejezéssel kell rendelkeznie.
A skálázható számítási kémia-csomagok által generált Hamiltonians túl nagyok a kézzel történő importáláshoz.

A Quantum Development Kit-hez készült Quantum kémiai könyvtár úgy lett kialakítva, hogy jól használható legyen a számítási kémia csomagjaival, leginkább a [**NWChem**](http://www.nwchem-sw.org/) számítási kémia platformját, amelyet a környezeti molekuláris tudományok laboratóriuma (EMSL) fejlesztett ki a csendes-óceáni országos laboratóriumban.
A [ **Microsoft. Quantum. kémia** csomag](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) például eszközöket biztosít a [Broombridge-sémában](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)képviselt Quantum kémia-szimulációs problémák példányainak betöltéséhez, amelyet a NWChem legújabb verziói is támogatnak.

A Quantum Development Kit kémia Library egy parancssori eszközt is biztosít, `qdk-chem` amely az örökölt formátumok és a [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)közötti átalakításra szolgál.

Ez a szakasz részletesen ismerteti, hogyan használható a Quantum Development Kit NWChem és Broombridge, illetve örökölt formátumokkal és `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>A Quantum Development Kit és a NWChem használata

A NWChem és a Quantum Development Kit együttes használatának megkezdéséhez használja a következő módszerek egyikét:

- Ismerkedjen meg a [IntegralData/YAML-](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)ben a mintákhoz megadott meglévő Broombridge-fájlok használatával.
- Használja a [EMSL Arrows Builder-t a Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) webalapú NWChem, amely új, Broombridge formátumú molekuláris bemeneti fájlok létrehozását eredményezi.  
- Használja a PNNL által biztosított [Docker-rendszerképet](https://hub.docker.com/r/nwchemorg/nwchem-qc/) a NWChem futtatásához, vagy
- [Fordítsa](http://www.nwchem-sw.org/index.php/Compiling_NWChem) le a NWChem a platformhoz.

Tekintse meg a [NWChem teljes körű](xref:microsoft.quantum.chemistry.examples.endtoend) ismertetését a NWChem és a kémiai modellek használatáról a Quantum fejlesztés Kit kémiai könyvtárának elemzéséhez.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>A mintákhoz megadott Broombridge-fájlok használatának első lépései

A [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML) mappa a Quantum Development Kit Samples adattárában a Broombridge-formázott molekula-adatfájlok szerepelnek.  

Egyszerű példaként használja a kémia könyvtár mintát, a [GetGateCount](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/GetGateCount) a Hamilton betöltéséhez az egyik Broombridge-fájlból, és hajtsa végre a Quantum szimulációs algorigthms a Gate becsléseit:

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

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>A Quantum Development Kit használata a `qdk-chem`

A telepítéséhez használhatja `qdk-chem` a .net Core SDK a parancssorban:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

A telepítése után `qdk-chem` a `--help` lehetőséggel további információkat kaphat az eszköz által kínált funkciókról `qdk-chem` .

A (z) és a (z) Broombridge való konvertáláshoz a következő `qdk-chem convert` parancsot használhatja:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

A `qdk-chem convert` parancs a szabványos bemenetből is elfogadhatja az adatait, és a szabványos kimenetre írhat. Ez különösen hasznos a parancsfájlokban és a régebbi formátumokra exportált eszközök integrálásához.
Például a Bashben:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
