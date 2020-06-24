---
title: Példák a Microsoft QDK
description: Ismerje meg, Hogyan járulhat hozzá a mintakód a Microsoft Quantum Development Kithoz (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274805"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Közreműködő minták a Quantum Development Kit-hez

Ha szeretne hozzájárulni a [minták tárházhoz](https://github.com/Microsoft/Quantum)való hozzájáruláshoz, Köszönjük, hogy a kvantum-fejlesztési Közösségnek jobb helyet kíván bevezetni!

## <a name="the-quantum-development-kit-samples-repository"></a>A Quantum Development Kit Samples repository

Annak érdekében, hogy a lehető legnagyobb mértékben segítse elő a hozzájárulását, hasznos lehet gyors áttekintést készíteni a minták tárházának meghatározásáról:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Ez azt eredményezi, hogy a [Microsoft/Quantum adattárban](https://github.com/microsoft/Quantum) lévő mintákat különböző mappákba (például `algorithms/` ,, `arithmetic/` vagy) bontottuk `characterization/` .
Az egyes területekhez tartozó mappában minden minta egy olyan mappából áll, amely összegyűjti a felhasználó által a minta megismeréséhez és használatához szükséges összes adatot.

## <a name="how-samples-are-structured"></a>A minták strukturálva

Tekintse át az egyes mappákat alkotó fájlokat, tekintsük át a [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) mintát.

| Fájl              | Leírás                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q # projekt a minta létrehozásához a .NET Core SDK használatával |
| `Game.qs`         | Q # műveletek és függvények a mintához                 |
| `Host.cs`         | A minta futtatására szolgáló C#-gazda program                     |
| `host.py`         | A minta futtatásához használt Python-gazda program                 |
| `README.md`       | Dokumentáció a minta működéséről és használatáról    |

Nem minden mintának ugyanazokat a fájlokat fogja tartalmazni (például: néhány minta csak C# lehet, másoknak nem lehet Python-gazdagépe, vagy bizonyos példákban segédszolgáltatása adatfájlok is működhetnek).

## <a name="anatomy-of-a-helpful-readme-file"></a>Hasznos információs fájl anatómiája

Az egyik különösen fontos fájl, azonban a `README.md` fájl, ahogy a felhasználóknak meg kell kezdeniük a mintát!

Mindegyiknek olyan `README.md` metaadatokkal kell kezdődnie, amelyek segítenek a docs.microsoft.com/Samples megtalálásában.

> [!div class="nextstepaction"]
> [Nézze meg, hogyan jelenik meg a chsh-játék mintája](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Ez a metaadatok olyan YAML- [fejlécként](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) jelennek meg, amely megadja, hogy a minta milyen nyelvekre terjed ki (ez általában a, a `qsharp` `csharp` és a `python` ), valamint hogy a minta mely termékekre vonatkozik (jellemzően, csak `qdk` ).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> Ahhoz, `page_type: sample` hogy a minta megjelenjen a docs.microsoft.com/Samples, a fejlécben szereplő kulcs megadása kötelező.
> Hasonlóképpen a `product` és a `language` kulcsok kritikus fontosságúak ahhoz, hogy segítséget nyújtson a felhasználóknak a minta megtalálásában és futtatásában.

Ezt követően hasznos lehet egy rövid bevezetőt adni, amely megadja, hogy mit tesz az új minta:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

A minta felhasználói azt is értékelik, hogy mire van szükségük a futtatásához (például: a felhasználók csak saját maga szeretnék kiépíteni a kvantum-fejlesztési csomagot, vagy további szoftverekre van szükségük, például node.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

A következő módon megadhatja, hogy a felhasználók hogyan futtathatják a mintát:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Végezetül pedig hasznos lehet tájékoztatni a felhasználókat arról, hogy a mintában szereplő összes fájl milyen további információkat tartalmaz:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Ügyeljen arra, hogy itt abszolút URL-címeket használjon, mivel a minta egy másik URL-címen fog megjelenni, amikor a docs.microsoft.com/samples-on jelenik meg.
