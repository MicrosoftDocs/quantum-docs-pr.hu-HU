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
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863696"
---
# <a name="ino-locq-magic-commands"></a>Q#Magic-parancsok

### <a name="general"></a>Általános kérdések

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Lehetővé teszi a konfigurációs beállítások beállítását vagy lekérdezését.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Egy adott függvény vagy művelet futtatása a ResourcesEstimator célszámítógépen.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Az aktuálisan elérhető Magic-parancsok listáját adja vissza.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): A jelenleg megnyitott névtereket és azok aliasait listázza.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Lehetővé teszi a NuGet-csomagok betöltését.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): A kernel aktuális teljesítmény-metrikáit jelenti.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Lehetővé teszi a projekt-referenciák megtekintését vagy hozzáadását Q# . 
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
