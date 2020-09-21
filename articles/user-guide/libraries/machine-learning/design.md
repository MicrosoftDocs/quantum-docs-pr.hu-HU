---
title: Saját osztályozó kialakítása a QDK
description: Megtudhatja, hogyan tervezhet áramköri modelleket a Quantum Circuit központú osztályozó számára.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3515279dd4d03b2a512035af0b13e084dd91f9dc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835706"
---
# <a name="design-your-own-classifier"></a>Saját osztályozó tervezése

Ebben az útmutatóban megismerheti a Quantum Circuit központú osztályozó áramköri modelljeinek kialakításához szükséges alapvető fogalmakat.

A klasszikus mély tanuláshoz hasonlóan nincs általános szabály egy adott architektúra kiválasztásához. A probléma függvényében egyes architektúrák jobban teljesítenek, mint mások. Vannak azonban olyan fogalmak is, amelyek hasznosak lehetnek az áramkör tervezésekor:

- A nagy számú paraméter egy rugalmasabb modellt tesz szükségessé, amely alkalmas lehet a bonyolult besorolási határok rajzolására, de az is elképzelhető, hogy a túlilleszkedés is érzékenyebb.

- A qubits közötti összekapcsolási kapuk elengedhetetlenek a kvantum-funkciók közötti korrelációk rögzítéséhez.

## <a name="how-to-build-a-classifier-with-q"></a>Osztályozó létrehozása a Q használatával\#

Az osztályozó kiépítéséhez a parametrized-vezérelt rotációkat fogjuk összefűzni az áramköri modellben. Ehhez a [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) Quantum Machine learning könyvtárban definiált típust használhatjuk. Ez a típus négy argumentumot fogad el: a cél qubit indexét, a vezérlőelem qubits indexét, a forgatás tengelyét, valamint a társított paraméter indexét a modellt meghatározó paraméterek tömbben.

Lássunk egy példát a besorolásra. A [Half-Moons mintában](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)a következő, a fájlban definiált osztályozó található `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

Az itt definiált függvények az elemek tömbjét visszaadó függvény `ControlledRotation` , amely a paraméterek tömbjét és a torzítást is meghatározza [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) . Ez a típus alapvető fontosságú a Quantum Machine Learning könyvtárban, és meghatározza az osztályozó értéket. A fenti függvényben meghatározott kör egy olyan osztályozó része, amelyben az adatkészlet mindegyik mintája két funkciót tartalmaz. Ezért csak két qubits van szükség. Az áramkör grafikus ábrázolása:

 ![Példa áramköri modellre](~/media/circuit_model_1.PNG)

Vegye figyelembe, hogy alapértelmezés szerint a Quantum Machine Learning Library műveletei a regisztráció utolsó qubit mérik a besorolási valószínűségek becslése érdekében. Ezt a tényt érdemes figyelembe vennie az áramkör tervezésekor.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>A könyvtár függvények használata a Gates rétegeinek írásához

Tegyük fel, hogy egy 784-es funkciókkal rendelkező adatkészletet használunk, például: 28 × 28 képpont, például a MNIST adathalmaz. Ebben az esetben az áramkör szélessége elég nagy lesz, így az egyes kapuk általi írás is lehetséges, de nem praktikus feladat lesz. Ezért a Quantum Machine Learning Library olyan eszközöket biztosít, amelyekkel automatikusan hozhat létre parametrized-rotációs rétegeket. A függvény például [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) visszaadja a nem vezérelt qubit-rotációk tömbjét egy adott tengelyen, egy rotációs értékkel a regiszter minden egyes qubit, az egyes parametrized egy másik modell-paraméterrel. Például `LocalRotationsLayer(4, X)` a következő Gates-készletet adja vissza:

 ![Helyi elforgatások réteg](~/media/local_rotations_layer.PNG)

Javasoljuk, hogy ismerkedjen meg a [Quantum Machine learning Library API-referenciával](xref:microsoft.quantum.machinelearning) , és fedezze fel az áramköri terv egyszerűsítéséhez rendelkezésre álló összes eszközt.

## <a name="next-steps"></a>Következő lépések

 Próbálkozzon különböző struktúrákkal a minták által megadott példákban. Megjelenik a modell teljesítményében bekövetkezett változás? A következő oktatóanyagban [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) megtudhatja, hogyan tölthet be adatkészleteket az osztályozók új architektúráinak kipróbálásához és megismeréséhez.
