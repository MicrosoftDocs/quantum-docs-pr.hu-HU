---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721600"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="25e6d-102">ApplyMajorityInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="25e6d-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="25e6d-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="25e6d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="25e6d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25e6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25e6d-105">A qubit többségi műveletet a következő helyen alkalmazza a qubits-jegyzékben:.</span><span class="sxs-lookup"><span data-stu-id="25e6d-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="25e6d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="25e6d-106">Description</span></span>

<span data-ttu-id="25e6d-107">Ez a művelet kiszámítja a többségi függvényt helyben, 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="25e6d-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="25e6d-108">Ha a kimeneti qubit $z $ és a bemeneti qubits $x $ és $y $ értékre jelöli, a művelet a következő átalakítást hajtja végre: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="25e6d-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="25e6d-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="25e6d-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="25e6d-110">kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="25e6d-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="25e6d-111">Első bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="25e6d-111">First input qubit.</span></span> <span data-ttu-id="25e6d-112">Vegye figyelembe, hogy a kimenet kiszámításának helye és tárolása ebben a qubit történik.</span><span class="sxs-lookup"><span data-stu-id="25e6d-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="25e6d-113">bemenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="25e6d-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="25e6d-114">Második és harmadik bemeneti qubits.</span><span class="sxs-lookup"><span data-stu-id="25e6d-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25e6d-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25e6d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

