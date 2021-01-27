---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ-művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846546"
---
# <a name="maj-operation"></a><span data-ttu-id="82555-102">MAJ-művelet</span><span class="sxs-lookup"><span data-stu-id="82555-102">MAJ operation</span></span>

<span data-ttu-id="82555-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="82555-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="82555-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82555-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82555-105">Ez a helyi többségi műveletet 3 qubits alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="82555-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="82555-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="82555-106">Description</span></span>

<span data-ttu-id="82555-107">Ha a célként megadott qubit állapotát a $ \ket{z} $ értékre, a bemeneti qubits pedig $ \ket{x} $ és $ \ket{y} $ értékre állítja be, akkor ez a művelet a következő átalakítást hajtja végre: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="82555-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="82555-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="82555-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="82555-109">input0: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="82555-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="82555-110">Az első bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="82555-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="82555-111">input1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="82555-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="82555-112">A második bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="82555-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="82555-113">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="82555-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="82555-114">A qubit, amelyre a rendszer alkalmazza a többségi függvényt.</span><span class="sxs-lookup"><span data-stu-id="82555-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82555-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82555-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

