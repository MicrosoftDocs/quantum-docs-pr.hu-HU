---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841594"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="7d188-102">ApplyPauliFromBitString művelet</span><span class="sxs-lookup"><span data-stu-id="7d188-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="7d188-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d188-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d188-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d188-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d188-105">Egy, a tömb minden qubit alkalmazza a Pauli-operátort, ha a logikai tömb megfelelő bitje egy adott bemenetnek felel meg.</span><span class="sxs-lookup"><span data-stu-id="7d188-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7d188-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7d188-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="7d188-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7d188-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7d188-108">A Pauli-operátor, `qubits[idx]` amelyre alkalmazni kell `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="7d188-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="7d188-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d188-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d188-110">a Pauli alkalmazása, ha a bit értéke ez az érték</span><span class="sxs-lookup"><span data-stu-id="7d188-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="7d188-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7d188-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7d188-112">Logikai regiszter, amely meghatározza, hogy a rendszer mely megfelelő qubit kell `qubits` működtetni</span><span class="sxs-lookup"><span data-stu-id="7d188-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7d188-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d188-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7d188-114">Quantum-regisztráció, amelyen szelektíven alkalmazni kell a megadott Pauli-operátort</span><span class="sxs-lookup"><span data-stu-id="7d188-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d188-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d188-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7d188-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7d188-116">Remarks</span></span>

<span data-ttu-id="7d188-117">A logikai tömbnek és a kvantum-regiszternek egyenlő hosszúságú kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7d188-117">The Boolean array and the quantum register must be of equal length.</span></span>