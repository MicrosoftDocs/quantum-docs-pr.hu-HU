---
title: További Q# kódtárak használata
description: Ismerje meg, hogyan adhat hozzá további Q# kódtárakat a kvantum-alkalmazásokhoz.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869579"
---
# <a name="using-additional-no-locq-libraries"></a>További Q# kódtárak használata

A Quantum Development Kit további, tartományra jellemző funkciókat biztosít a projektekhez adható _NuGet-csomagokon_ keresztül Q# .

| Q#Erőforrástár  | NuGet-csomag | Megjegyzések |
|---------|---------|--------|
| [Q#Standard könyvtár](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Alapértelmezés szerint tartalmazza |
| [Kvantumkémiai kódtár](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Kvantumnumerikus kódtár](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. numerikus számok**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Kvantum gépi tanulási kódtár](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Miután telepítette a Quantum Development Kit-t az előnyben részesített környezettel és a gazdagép nyelvével való használatra, a további telepítés nélkül könnyedén hozzáadhat könyvtárakat az egyes Q# projektekhez.

> [!NOTE]
> Egyes Q# könyvtárak jól használhatók olyan további eszközökkel, amelyek a programok mellett működnek Q# , vagy amelyek integrálva vannak a gazdagép alkalmazásaival.
> A [kémia könyvtár telepítési útmutatója](xref:microsoft.quantum.chemistry.concepts.installation) például leírja, hogyan használhatja a [ **Microsoft. Quantum. kémia** csomagot](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) a NWChem számítási kémia platformmal, és hogyan telepítheti a `qdk-chem` parancssori eszközöket a kvantum-kémiai adatmennyiségek használatához.

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[Q#parancssori alkalmazások vagy .NET-együttműködés](#tab/tabid-csproj)

**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal hozzáadhat egy NuGet-csomagot a projekthez.
A [**Microsoft. Quantum. numerikus**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) csomagok hozzáadásához például futtassa a következő parancsot:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Ha a Visual Studio 2019-es vagy újabb verzióját használja, további csomagokat adhat hozzá Q# a NuGet csomagkezelő használatával.
Csomag betöltése: 
1. A Visual Studióban megnyitott projekttel válassza a **NuGet-csomagok kezelése...** lehetőséget a **projekt** menüben.

2. Kattintson a **Tallózás**elemre, válassza az **előzetes kiadás belefoglalása** lehetőséget, és keresse meg a "Microsoft. Quantum. numerikus" nevű csomagot. Ekkor megjelenik a letölthető csomagok listája.

3. Vigye a kurzort a **Microsoft. Quantum.** Numbers elemre, majd kattintson a verziószám jobb oldalán lévő lefelé mutató nyílra a numerikus csomagok telepítéséhez.

További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a numerikus függvénytárat a projekthez a parancssori felületen keresztül.

![A Package Manager konzol használata a parancssorból](~/media/vs2017-nuget-console-menu.png)

A Package Manager konzolon futtassa a következőt:

```
Install-Package Microsoft.Quantum.Numerics
```

További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[Q#Jegyzetfüzetek](#tab/tabid-notebook)

Q#A [ `%package` Magic parancs](xref:microsoft.quantum.iqsharp.magic-ref.package)használatával további csomagokat is használhat az I jegyzetfüzetben.
Ha például a [**Microsoft. Quantum. numerikus**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) csomagokat szeretné felvenni egy I jegyzetfüzetben való használatra Q# , futtassa a következő parancsot egy jegyzetfüzet-cellában:

```
%package Microsoft.Quantum.Numerics
```

Ezt a parancsot követve a csomag a jegyzetfüzetben lévő összes cella számára elérhető.
Ahhoz, hogy a csomag elérhető legyen a Q# jelenlegi munkaterületen található kódból, a csomag hozzáadása után töltse be újra a munkaterületet:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python-együttműködés](#tab/tabid-python)


A metódus használatával további csomagokat is használhat egy Python-gazda programban [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) .
Ha például a [**Microsoft. Quantum. numerikus**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) csomagokat szeretné felvenni egy I jegyzetfüzetben való használatra Q# , futtassa a következő Python-kódot:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

A parancs követése után a csomag elérhetővé válik bármely, a Q# használatával lefordított kód számára `qsharp.compile` .
Ahhoz, hogy a csomag elérhető legyen a Q# jelenlegi munkaterületen található kódból, a csomag hozzáadása után töltse be újra a munkaterületet:

```python
qsharp.reload()
```

***
