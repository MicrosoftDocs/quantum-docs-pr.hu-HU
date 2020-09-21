---
title: Klasszikus adatlemez betöltése
description: Ismerje meg, hogyan tölthető be a saját adatkészlet egy osztályozó modell betanításához a Microsoft Quantum Development Kit (QDK) használatával.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: cd6fdb6bb33a65ee02ac8c43f40df9abeff9c841
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833709"
---
# <a name="load-and-classify-your-own-datasets"></a>Saját adatkészletek betöltése és besorolása

Ebben a rövid oktatóanyagban megtudhatja, hogyan tölthető be a saját adatkészlet egy osztályozó modell betanításához a Quantum Development Kit (QDK) használatával.

Javasoljuk, hogy az adattároláshoz használjon szabványos szerializálási formátumot, például a [JSON-fájlokat](https://en.wikipedia.org/wiki/JSON) .
Az ilyen formátumok nagy kompatibilitást biztosítanak a különböző keretrendszerek, például a Python és a .NET ökoszisztéma tekintetében.
Különösen azt javasoljuk, hogy az adatok betöltéséhez használja a sablont, hogy közvetlenül a mintából másolhatja be a kódot.

## <a name="template-for-loading-your-datasets"></a>Az adatkészletek betöltéséhez használt sablon

Tegyük fel, hogy a (z) $ (x, y) $ $N = $2-es betanítási adatkészlettel rendelkezik, ahol minden példánynak $x _i $ $x $-nak három funkciója van: $x _ {I1} $, $x _ {I2} $ és $x _ {i3} $.
Az érvényesítési adatkészlet ugyanazzal a szerkezettel rendelkezik.
Ezeket a datsets `data.json` az alábbihoz hasonló fájl jelölheti:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Példa a sablon használatával

Tegyük fel, hogy van egy kis adathalmaza, amely a különböző macskák és kutyák magasságával és súlyával rendelkezik. Ez az adatkészlet nagyon kicsi a modell betanításához, de elegendő lesz az adatkészlet betöltési folyamatának megjelenítéséhez.

| Magasság (m) | Súlyozás (kg) | Állat |
|-----------|------------|--------|
| 0,54      | 30         | Figyelve    |
| 0,30      | 8          | Cat    |
| 0,91      | 44         | Figyelve    |
| 0,86      | 31          | Figyelve    |
| 0,32      | 5         | Cat    |
| 0,25      | 4          | Cat    |

A folyamat:

- Először el kell különíteni az adatkészletet a képzésbe és az érvényesítésbe. Ebben az esetben csak az első három mintát vesszük igénybe a képzéshez és a többi minta ellenőrzéshez. Általánosságban azt érdemes megtervezni, hogy véletlenszerűen megkóstolja a betanítási és érvényesítési adatkészletet, hogy elkerülje a betanítási adatokat a nemkívánatos torzulások elkerülése érdekében.
- Másodszor, minden osztályhoz hozzá kell rendelni egy numerikus címkét. Vegye figyelembe, hogy jelenleg a QML-könyvtár csak bináris besorolási problémákat fogad el. Ezért a 0. címkét a osztályhoz rendeljük, `Dog` az 1-es számot pedig az osztályhoz `Cat` .
- Végül kitöltjük a sablont az adatkészlet adatai alapján. Vegye figyelembe, hogy a nagyméretű adatkészletek esetében érdemes létrehozni egy kis parancsfájlt, amely automatikusan létrehozza a sablont az adott adatkészletből. Ez a szkript az adatkészlet eredeti formátumának függvénye lesz.

Az adatkészlet esetében a `data.json` fájl a következő:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Az adatok betöltése

Miután a rendszer JSON-fájlként szerializálta az adatait, betöltheti azt a választott gazdagép nyelvén elérhető JSON-kódtárak használatával.

### <a name="python"></a>[Python](#tab/tabid-python)

A Python a JSON-szerializált adatkezeléshez használható [beépített `json` csomagot](https://docs.python.org/3.7/library/json.html) tartalmazza:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

A .NET Core platform biztosítja a [ `System.Text.Json` csomagot](https://www.nuget.org/packages/System.Text.Json) a JSON-szerializált adatkezeléshez:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Következő lépések

Most már készen áll a saját adatkészletekkel való saját kísérletek futtatására. Próbálja ki a különböző besorolásokat és adatkészleteket, és járuljon hozzá az eredményeket megosztó közösséghez.
