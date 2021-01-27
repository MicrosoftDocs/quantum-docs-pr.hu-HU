---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851097"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="07345-102">ApplyDeltaParity művelet</span><span class="sxs-lookup"><span data-stu-id="07345-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="07345-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="07345-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="07345-104">Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="07345-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="07345-105">Kiszámítja az előző PQRS paritásos különbözetét... feltételek és a következő PQRS... távú.</span><span class="sxs-lookup"><span data-stu-id="07345-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="07345-106">Ezt a különbözetet egy kiegészítő qubit számítjuk ki.</span><span class="sxs-lookup"><span data-stu-id="07345-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="07345-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="07345-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="07345-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="07345-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="07345-109">Indexek listája az előző PQRS... feltételek.</span><span class="sxs-lookup"><span data-stu-id="07345-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="07345-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="07345-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="07345-111">Indexek listája a következő PQRS... feltételek.</span><span class="sxs-lookup"><span data-stu-id="07345-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="07345-112">AUX: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07345-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="07345-113">Az a kiegészítő qubit, amelybe a paritásos számítási eredmények tárolódnak.</span><span class="sxs-lookup"><span data-stu-id="07345-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="07345-114">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="07345-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="07345-115">A Qubit az összes PQRS által működött... feltételek.</span><span class="sxs-lookup"><span data-stu-id="07345-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07345-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07345-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07345-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="07345-117">Remarks</span></span>

<span data-ttu-id="07345-118">Ez azt feltételezi, hogy a P < Q < R < S <... mind a prevPQ, mind a nextPQ esetében.</span><span class="sxs-lookup"><span data-stu-id="07345-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>