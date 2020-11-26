---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190734"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="09b63-102">ApplyMajorityInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="09b63-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="09b63-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="09b63-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="09b63-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09b63-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09b63-105">A qubit többségi műveletet a következő helyen alkalmazza a qubits-jegyzékben:.</span><span class="sxs-lookup"><span data-stu-id="09b63-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="09b63-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="09b63-106">Description</span></span>

<span data-ttu-id="09b63-107">Ez a művelet kiszámítja a többségi függvényt helyben, 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="09b63-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="09b63-108">Ha a kimeneti qubit $z $ és a bemeneti qubits $x $ és $y $ értékre jelöli, a művelet a következő átalakítást hajtja végre: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="09b63-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="09b63-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="09b63-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="09b63-110">kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="09b63-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="09b63-111">Első bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="09b63-111">First input qubit.</span></span> <span data-ttu-id="09b63-112">Vegye figyelembe, hogy a kimenet kiszámításának helye és tárolása ebben a qubit történik.</span><span class="sxs-lookup"><span data-stu-id="09b63-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="09b63-113">bemenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="09b63-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="09b63-114">Második és harmadik bemeneti qubits.</span><span class="sxs-lookup"><span data-stu-id="09b63-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09b63-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09b63-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

