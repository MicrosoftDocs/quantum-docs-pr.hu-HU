---
title: Quantum Machine learning-könyvtár
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
ms.openlocfilehash: f9b33a607a892179795d0700ba3080f9a24ab94a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909772"
---
# <a name="quantum-machine-learning-glossary"></a>Quantum Machine Learning Szószedet

Az áramkör-központú kvantummechanika betanítása olyan folyamat, amely számos mozgó részből áll (vagy valamivel nagyobb), mint a hagyományos osztályozók betanítása. Itt definiáljuk a betanítási folyamat fő fogalmait és összetevőit.

## <a name="trainingtesting-schedules"></a>Képzés/tesztelési ütemtervek

Az osztályozó képzés kontextusában az *ütemterv* az adatminták egy részhalmazát írja le egy átfogó képzésben vagy tesztelési készletben. Az ütemtervek meghatározása általában minta-indexek gyűjteménye.

## <a name="parameterbias-scores"></a>Paraméterek/torzítások pontszámai

A jelölt paraméterek és az osztályozó torzítások miatt a rendszer az *ellenőrzési pontszámot* a kiválasztott ellenőrzési ütemtervhez viszonyítva méri, és számos, az ütemtervben szereplő összes minta alapján megszámolt téves besorolással rendelkezik.

## <a name="hyperparameters"></a>Hiperparaméterek beállítása

A modell betanítási folyamatát bizonyos előre beállított, *hiperparaméterek beállítása*nevű értékek szabályozzák:

### <a name="learning-rate"></a>Tanulási arány

Ez a legfontosabb hiperparaméterek beállítása egyike. Meghatározza, hogy a sztochasztikus gradiens aktuális becsült értéke milyen mértékben befolyásolja a paraméter frissítését. A paraméter-frissítési különbözet mérete arányos a képzési aránysal. A kisebb tanulási arány a lassabb paraméterek alakulását és a lassabb konvergenciát eredményezi, de az LR túlságosan nagy értékei megszüntetik a konvergenciát egészen addig, amíg a színátmenet kivezetése soha nem véglegesíti az adott helyi minimális értéket. Míg a képzési algoritmus adaptív bizonyos mértékig korrigálva van, a megfelelő kezdeti érték kiválasztása fontos. A tanulási sebesség szokásos alapértelmezett kezdeti értéke 0,1. A tanulási sebesség legjobb értékének kiválasztása egy képzőművészet (lásd például a Goodfellow et al., "Deep learning", "do Press", 2017) 4,3 című szakaszt.

### <a name="minibatch-size"></a>Minibatch mérete

Meghatározza, hogy hány adatminta van használatban a sztochasztikus gradiens egyetlen becsléséhez. A minibatch méretének nagyobb értéke általában robusztusabb és több monoton konvergenciát eredményez, de a betanítási folyamat lelassulhat, mivel a minimatch méretével arányos egy átmenetes becslés díja. A minibatch szokásos alapértelmezett értéke 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Képzési korszakok, tolerancia, gridlocks

Az "EPOCH" kifejezés azt jelenti, hogy az ütemezett betanítási adatszolgáltatások egyike teljes.
A betanítási szálon (lásd alább) lévő időpontok maximális számát meg kell szabni. A betanítási szál a leálláshoz van definiálva (a legismertebb jelölt paraméterekkel), amikor a rendszer elvégezte az időpontok maximális számát. Az ilyen képzések azonban korábban megszűnnek, ha az érvényesítési ütemterv nem a kiválasztott tűréshatár alá esik. Tegyük fel például, hogy a téves besorolási tűréshatár 0,01 (1%); Ha az 2000-minták érvényesítési készletében kevesebb, mint 20 téves besorolás látható, akkor a rendszer elérte a tűréshatár szintjét. Egy betanítási szál idő előtt leáll, ha a pályázó modell ellenőrzési pontszáma nem mutatott javulást több egymást követő korszakban (egy körbetartozás). A körbetartozás-megszakítás logikája jelenleg hardcoded.

### <a name="measurements-count"></a>Mérések száma

A betanítási/érvényesítési pontszámok, valamint a sztochasztikus gradiensnek a kvantum-eszközön lévő összetevőinek becslése a kvantum-állapot átfedésének megbecsléséhez, amely a megfelelő observables több mérését igényli. A mérések számát $O (1/\ epszilon ^ 2) $ értékre kell méretezni, ahol a $ \epsilon $ a kívánt becslési hiba.
A szabály a kezdeti mérések száma körülbelül $1/\ mbox {tolerancia} ^ 2 $ lehet (lásd a tolerancia definícióját az előző bekezdésben). Az egyiknek újra kell változtatnia a mérések darabszámát, ha úgy tűnik, hogy a gradiens túlságosan kiszámíthatatlan, és a konvergencia túl nehezen elérhető.

### <a name="training-threads"></a>Betanítási szálak

A valószínűségi függvény, amely az osztályozó betanítási segédprogramja, nagyon ritkán domború, ami azt jelenti, hogy általában számos helyi Optima szerepel a paraméterben, amely jelentősen különbözhet a minőségtől. Mivel az SGD-folyamat csak egy adott optimális értékre konvergál, fontos felderíteni több kezdő paraméteres vektort is. A gépi tanulás gyakori gyakorlata, hogy az ilyen kezdő vektorokat véletlenszerűen inicializálja. A Q # betanítási API tetszőleges tömböt fogad az ilyen kezdő vektorokból, de az alapul szolgáló kód szekvenciálisan tárja fel őket. A többtényezős számítógépeken vagy a párhuzamos számítástechnikai architektúrák esetében ajánlott több hívást végrehajtani a Q # betanítási API-val párhuzamosan a hívások különböző paramétereinek inicializálásával.

#### <a name="how-to-modify-the-hyperparameters"></a>A hiperparaméterek beállítása módosítása

A QML-könyvtárban a legjobb módszer a hiperparaméterek beállítása módosítására, ha felülbírálja a UDT alapértelmezett értékeit [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions). Ehhez hívja meg a függvényt [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) és alkalmazza a kezelőt `w/` az alapértelmezett értékek felülbírálásához. Például az 100 000 mérések és a 0,01-es tanulási arány használatához:
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```