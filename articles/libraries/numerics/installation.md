---
title: Numerikus könyvtárak telepítése és érvényesítése | Microsoft Docs
description: Numerikus könyvtárak telepítése és érvényesítése
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184627"
---
# <a name="numerics-library-installation-and-validation"></a>Numerikus könyvtárak telepítése és érvényesítése

A Quantum Development Kit a [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet-csomagon keresztül biztosítja a numerikus funkciók használatát.

**Visual Studio > = 2019:** Ha a Visual Studio 2019-es vagy újabb verzióját használja, a numerikus csomagokat a NuGet csomagkezelő használatával adhatja hozzá.
Ehhez válassza a "NuGet-csomagok kezelése..." lehetőséget. a Visual Studióban a "projekt" menüpontban.

A Tallózás lapon keresse meg a "Microsoft. Quantum. numerikus" nevű csomagot.

> [!NOTE]
> Győződjön meg arról, hogy az "előzetes kiadás belefoglalása" jelölőnégyzet be van jelölve

Ekkor megjelenik a letölthető csomagok listája.
A "Microsoft. Quantum. Numbers" kifejezés fölé helyezve egy lefelé mutató nyíl látható a verziószámtól jobbra.
Kattintson a nyílra a numerikus csomagok telepítéséhez.

További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a numerikus függvénytárat a projekthez a parancssori felületen keresztül.

![](~/media/vs2017-nuget-console-menu.png)

A Package Manager konzolon futtassa a következőt:

```
Install-Package Microsoft.Quantum.Numerics
```

További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal adhat hozzá NuGet-csomagot a projekthez:

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>A telepítés ellenőrzése

A Quantum Development Kit többi részéhez hasonlóan a numerikus könyvtár olyan mintákat tartalmaz, amelyek segítségével a lehető leggyorsabban kezdheti meg a lépéseket.
Ha tesztelni szeretné a telepítést ezeken a mintákon, akkor a [fő minták tárházát](https://github.com/Microsoft/Quantum) , majd futtassa az egyik mintát.

A [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) minta futtatása:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```