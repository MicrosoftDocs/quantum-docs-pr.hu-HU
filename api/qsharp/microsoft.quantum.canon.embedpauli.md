---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716202"
---
# <a name="embedpauli-function"></a><span data-ttu-id="25dde-102">EmbedPauli függvény</span><span class="sxs-lookup"><span data-stu-id="25dde-102">EmbedPauli function</span></span>

<span data-ttu-id="25dde-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25dde-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25dde-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25dde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25dde-105">Egy qubit Pauli-operátor és egy qubit indexe miatt egy több qubit Pauli-operátort ad vissza a megadott qubit operátorral az adott indexben és `PauliI` minden más indexben.</span><span class="sxs-lookup"><span data-stu-id="25dde-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="25dde-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="25dde-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="25dde-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="25dde-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="25dde-108">Egy qubit Pauli-operátort kell elhelyezni a megadott helyen.</span><span class="sxs-lookup"><span data-stu-id="25dde-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="25dde-109">hely: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25dde-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25dde-110">Egy index, amely `output[location] == pauli` `output` a függvény kimenetét adja meg.</span><span class="sxs-lookup"><span data-stu-id="25dde-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="25dde-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25dde-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25dde-112">A visszaadott tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="25dde-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="25dde-113">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="25dde-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

