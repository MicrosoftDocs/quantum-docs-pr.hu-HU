---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Microsoft. Quantum. AmplitudeAmplification névtér
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: 09c29bd9d0648bb8652051ad97ceca6ef6557df3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721848"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Microsoft. Quantum. AmplitudeAmplification névtér

Ez a névtér olyan függvényeket és műveleteket tartalmaz, amelyek amplitúdó-erősítést végeznek.



## <a name="description"></a>Leírás

Az amplitúdó-erősítés a részleges reflexiókkal a legáltalánosabb formája az amplitúdó-erősítésnek itt implementált.

Ezt a művelet AmpAmpObliviousByReflectionPhases hívja meg.

Ez két regisztrációval rendelkezik: `ancillaRegister` és `systemRegister` .

Ez két Oracle-t fogad el ezen olyan típusú reflexiók esetében, `ReflectionOracle` amelyek csak a regisztráláskor lépnek fel `ancillaRegister` .

Ez egy különleges Oracle-t fogad el, amely elfeledkezett a típusú amplitúdó-erősítésről, `ObliviousOracle` amely közösen működik mindkét regisztráláskor.

A bemeneti állapotot `ancillaRegister` feltételezi, hogy az első reflexiós operátor egyedi $-$1 eigenstate van $I – 2 \ ket {s} \ melltartó {s} $.

A cél kvantum állapottal kapcsolatos reflexiók gyakran úgy vannak megvalósítva, hogy hozzáférést biztosítanak egy olyan Oracle-hez, amely felkészíti ezt az állapotot a $ \ket{0\cdots 0} $ számítási alapján.

Ezen Oracle-eszközökre vonatkozó konvenciónk két regisztrációt igényel: egy qubit- `flagQubit` regisztrációt, és minden más, a ancillaRegister-regisztrációhoz tartozó regisztrációt.

Az Oracle of Type `StateOracle` is közösen működik mindkét regiszterben, hogy létrehozza a \ket $ által megjelölt cél állapotot {1} a `flagQubit` regisztrációban egy valós amplitúdóval.

Az `ReflectionOracle` ezzel a jelző állapottal kapcsolatos tükrözést a művelet hozza létre `TargetStateReflectionOracle` .

Az `ReflectionOracle` invertált StateOracle által generált bemeneti állapottal kapcsolatos reflexió, `ancillaRegister` majd a $ \ket{0\cdots 0} $ a ReflectionStart () értékkel való tükrözése.

A Type Oracle a `DeterministicStateOracle` `qubitState` regisztrációk alapján hozza létre a cél állapotot pontosan a nem jelzővel.

`AmpAmpObliviousByOraclePhases` a a feledékenység amplitúdó-erősítésének egy verziója, amely az Oracle `StateOracle` -ket és `ObliviousOracle` a reflexiók helyett a-t fogadja.

Vegye figyelembe, hogy az amplitúdó-erősítés a feledékenység amplitúdó-erősítésének különleges esete, ahol az az `ObliviousOracle` identitás operátora, és nincsenek rendszerszintű qubits, azaz `systemRegister` üresek.

Ezt a rendszer a művelet és a használatával hívja meg `AmpAmByReflectionPhases` `AmpAmpByOraclePhases` .

A részleges tükrözések szakaszait a következő függvény AmpAmpPhasesStandard:.

Például a következő függőségek állnak fenn: AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.