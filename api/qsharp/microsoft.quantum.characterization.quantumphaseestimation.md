---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714943"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="0a97f-102">QuantumPhaseEstimation művelet</span><span class="sxs-lookup"><span data-stu-id="0a97f-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="0a97f-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="0a97f-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="0a97f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a97f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a97f-105">Végrehajtja a kvantum fázis becslési algoritmusát egy adott Oracle esetében `U` `targetState` , és beolvassa a fázist egy nagy endian kvantum-regisztrációba.</span><span class="sxs-lookup"><span data-stu-id="0a97f-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="0a97f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0a97f-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="0a97f-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="0a97f-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="0a97f-108">Egy művelet, amely $U ^ m $ értéket valósít meg az adott egész számra (m).</span><span class="sxs-lookup"><span data-stu-id="0a97f-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="0a97f-109">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0a97f-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0a97f-110">A (z) $ \ket{\phi} $ állapotot jelölő Quantum Register $U $.</span><span class="sxs-lookup"><span data-stu-id="0a97f-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="0a97f-111">Ha a $ \ket{\phi} $ $U $ eigenstate, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0, 2 \ PI) $ ismeretlen fázis.</span><span class="sxs-lookup"><span data-stu-id="0a97f-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="0a97f-112">controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="0a97f-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="0a97f-113">Egy big-endian ábrázolási egész számú regiszter, amely a megadott Oracle szabályozására használható, és amely a művelet alkalmazását követően a $ \phi $ ábrázolását fogja tartalmazni.</span><span class="sxs-lookup"><span data-stu-id="0a97f-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="0a97f-114">A controlRegister feltételezi, hogy a kezdeti állapotban $ \ket{00\cdots 0} $, ahol a regisztráció hossza a kívánt pontosságot jelzi.</span><span class="sxs-lookup"><span data-stu-id="0a97f-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a97f-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a97f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

