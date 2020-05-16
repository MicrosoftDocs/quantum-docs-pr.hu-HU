---
title: IQ# Magic parancsok
description: 'Gyors hivatkozási oldal az IQ # Magic parancsaihoz Q # Jupyter notebookokkal'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431019"
---
# <a name="iq-magic-commands"></a>IQ# Magic parancsok

### <a name="general"></a>Általános kérdések

- `%config`: Beállítja vagy lekéri a konfigurációs beállításokat.
- `%estimate`: Egy adott függvény vagy művelet futtatása a QuantumSimulator célszámítógépen.
- `%lsmagic`: Az aktuálisan elérhető Magic-parancsok listáját adja vissza.
- `%package`: Lehetővé teszi a Nuget-csomagok betöltését.
- `%performance`: A kernel aktuális teljesítmény-metrikáit jelenti.
- `%simulate`: Egy adott függvény vagy művelet futtatása a QuantumSimulator célszámítógépen.
- `%toffoli`: Egy adott függvény vagy művelet futtatása a ToffoliSimulator Simulator célszámítógépen.
- `%who`: Az aktuális munkaterülettel kapcsolatos műveleteket biztosít.
- `%workspace`: Az aktuális munkamenetben definiált összes művelet és függvény listáját adja vissza, akár interaktív módon, akár az aktuális munkaterületről betöltve.

### <a name="chemistry"></a>Vegyi összetétel

- `%chemistry.broombridge`: Betölti és visszaadja a Broombridge elektronikus szerkezetének problémás ábrázolását egy adott. YAML fájlból.
- `%chemistry.encode`: Egy Fermion Hamilton kódol a Q # használatával.
- `%chemistry.fh.add_terms`: Feltételt hoz létre egy Fermion-Hamilton.
- `%chemistry.fh.load`: Betölti a Fermion Hamilton egy elektronikus szerkezettel kapcsolatos problémára. A probléma betöltése egy fájlból történik, vagy argumentumként van megadva.
- `%chemistry.inputstate.load`: Betölti a Broombridge elektronikus szerkezetével kapcsolatos problémát, és visszaadja a kiválasztott bemeneti állapotot.

### <a name="from-microsoftquantumkatas-package"></a>A Microsoft. Quantum. katas csomagból

- `%kata`: Egyetlen tesztet hajt végre, és jelentést készít arról, hogy a teszt sikeresen sikeres-e.
- `%check_kata`: Egy Kata-tesztre vonatkozó hivatkozás-implementáció ellenőrzése.
    Pontosabban helyettesíti az egyetlen feladatra vonatkozó hivatkozási implementációt a cellába, és azt jelzi, hogy a teszt sikeresen sikeres volt-e.
