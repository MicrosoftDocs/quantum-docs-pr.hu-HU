---
title: Q#Magic-parancsok
description: A Q# Jupyter notebookokkal ellátott Magic-parancsok gyors referenciájának lapja Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb7b5543ef9222e6bab2b1cbbc7e3ebb54863438
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867981"
---
# <a name="ino-locq-magic-commands"></a>Q#Magic-parancsok

### <a name="general"></a>Általános kérdések

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Lehetővé teszi a konfigurációs beállítások beállítását vagy lekérdezését.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Egy adott függvény vagy művelet futtatása a ResourcesEstimator célszámítógépen.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Az aktuálisan elérhető Magic-parancsok listáját adja vissza.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Lehetővé teszi a NuGet-csomagok betöltését.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): A kernel aktuális teljesítmény-metrikáit jelenti.
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Egy adott függvény vagy művelet futtatása a QuantumSimulator célszámítógépen.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Egy adott függvény vagy művelet futtatása a ToffoliSimulator célszámítógépen.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Az Q# aktuális munkamenetben elérhető műveletek felsorolása.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Az aktuális munkaterülettel kapcsolatos műveleteket biztosít.

### <a name="azure-quantum-integration"></a>Azure Quantum-integráció

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Csatlakozik egy Azure Quantum-munkaterülethez, vagy megjeleníti a jelenlegi kapcsolati állapotot.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Végrehajt egy feladatot egy Azure Quantum-munkaterületen.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Az aktuális Azure Quantum-munkaterületen található feladatok listáját jeleníti meg.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Az aktuális Azure Quantum-munkaterületen lévő feladatok eredményét jeleníti meg.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Az aktuális Azure Quantum-munkaterületen a feladatok állapotát jeleníti meg.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Elküld egy feladatot egy Azure Quantum-munkaterületre.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Beállítja vagy megjeleníti a Q# feladatok beküldésének aktív végrehajtási célját egy Azure Quantum-munkaterületen.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Kémia (a Microsoft. Quantum. kémia csomagból)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Betölti és visszaadja a Broombridge elektronikus szerkezetének problémás ábrázolását egy adott. YAML fájlból.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Egy Fermion-Hamilton kódol egy formátumba Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Feltételt hoz létre egy Fermion-Hamilton.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Betölti a Fermion Hamilton egy elektronikus szerkezettel kapcsolatos problémára. A probléma betöltése egy fájlból történik, vagy argumentumként van megadva.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Betölti a Broombridge elektronikus szerkezetével kapcsolatos problémát, és visszaadja a kiválasztott bemeneti állapotot.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (a Microsoft. Quantum. katas csomagból)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Egyetlen tesztet hajt végre, és jelentést készít arról, hogy a teszt sikeresen sikeres-e.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Egy Kata-tesztre vonatkozó hivatkozás-implementáció ellenőrzése.
    Pontosabban helyettesíti az egyetlen feladatra vonatkozó hivatkozási implementációt a cellába, és azt jelzi, hogy a teszt sikeresen sikeres volt-e.
