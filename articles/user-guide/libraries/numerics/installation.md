---
title: Microsoft Quantum numerikus könyvtárak – telepítés és érvényesítés
description: Megtudhatja, hogyan adhatja hozzá a Microsoft Quantum numerikus kódtárat a Visual Studio 2019-es vagy újabb verziójának telepítéséhez.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275191"
---
# <a name="numerics-library-installation-and-validation"></a>Numerikus könyvtárak telepítése és érvényesítése

A Quantum Development Kit a NuGet-csomagon keresztül biztosítja a numerikus funkciók használatát [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .

**Visual Studio >= 2019:** Ha a Visual Studio 2019-es vagy újabb verzióját használja, a numerikus csomagokat a NuGet csomagkezelő használatával adhatja hozzá.
Ehhez válassza a "NuGet-csomagok kezelése..." lehetőséget. a Visual Studióban a "projekt" menüpontban.

A Tallózás lapon keresse meg a "Microsoft. Quantum. numerikus" nevű csomagot.

> [!NOTE]
> Győződjön meg arról, hogy az "előzetes kiadás belefoglalása" jelölőnégyzet be van jelölve

Ekkor megjelenik a letölthető csomagok listája.
A "Microsoft. Quantum. Numbers" kifejezés fölé helyezve egy lefelé mutató nyíl látható a verziószámtól jobbra.
Kattintson a nyílra a numerikus csomagok telepítéséhez.

További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a numerikus függvénytárat a projekthez a parancssori felületen keresztül.

![A Package Manager konzol használata a parancssorból](~/media/vs2017-nuget-console-menu.png)

A Package Manager konzolon futtassa a következőt:

```
Install-Package Microsoft.Quantum.Numerics
```

További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal adhat hozzá NuGet-csomagot a projekthez:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>A telepítés ellenőrzése

A Quantum Development Kit többi részéhez hasonlóan a numerikus könyvtár olyan mintákat tartalmaz, amelyek segítségével a lehető leggyorsabban kezdheti meg a lépéseket.
Ha tesztelni szeretné a telepítést ezeken a mintákon, akkor a [fő minták tárházát](https://github.com/Microsoft/Quantum) , majd futtassa az egyik mintát.

A minta futtatása [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
