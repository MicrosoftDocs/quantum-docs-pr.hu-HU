---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840534"
---
# <a name="embedpauli-function"></a><span data-ttu-id="eeca1-102">EmbedPauli függvény</span><span class="sxs-lookup"><span data-stu-id="eeca1-102">EmbedPauli function</span></span>

<span data-ttu-id="eeca1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eeca1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eeca1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eeca1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eeca1-105">Egy qubit Pauli-operátor és egy qubit indexe miatt egy több qubit Pauli-operátort ad vissza a megadott qubit operátorral az adott indexben és `PauliI` minden más indexben.</span><span class="sxs-lookup"><span data-stu-id="eeca1-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="eeca1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eeca1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="eeca1-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="eeca1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="eeca1-108">Egy qubit Pauli-operátort kell elhelyezni a megadott helyen.</span><span class="sxs-lookup"><span data-stu-id="eeca1-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="eeca1-109">hely: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eeca1-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eeca1-110">Egy index, amely `output[location] == pauli` `output` a függvény kimenetét adja meg.</span><span class="sxs-lookup"><span data-stu-id="eeca1-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="eeca1-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eeca1-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eeca1-112">A visszaadott tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="eeca1-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="eeca1-113">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="eeca1-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="eeca1-114">Példa</span><span class="sxs-lookup"><span data-stu-id="eeca1-114">Example</span></span>

<span data-ttu-id="eeca1-115">A tömb beszerzése `[PauliI, PauliI, PauliX, PauliI]` :</span><span class="sxs-lookup"><span data-stu-id="eeca1-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```