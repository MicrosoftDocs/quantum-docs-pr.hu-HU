---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721013"
---
# <a name="maj-operation"></a><span data-ttu-id="6df28-102">MAJ-művelet</span><span class="sxs-lookup"><span data-stu-id="6df28-102">MAJ operation</span></span>

<span data-ttu-id="6df28-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6df28-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6df28-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6df28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6df28-105">Ez a helyi többségi műveletet 3 qubits alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="6df28-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="6df28-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6df28-106">Description</span></span>

<span data-ttu-id="6df28-107">Ha a célként megadott qubit állapotát a $ \ket{z} $ értékre, a bemeneti qubits pedig $ \ket{x} $ és $ \ket{y} $ értékre állítja be, akkor ez a művelet a következő átalakítást hajtja végre: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="6df28-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6df28-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6df28-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="6df28-109">input0: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6df28-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6df28-110">Az első bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="6df28-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="6df28-111">input1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6df28-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6df28-112">A második bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="6df28-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6df28-113">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6df28-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6df28-114">A qubit, amelyre a rendszer alkalmazza a többségi függvényt.</span><span class="sxs-lookup"><span data-stu-id="6df28-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6df28-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6df28-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

