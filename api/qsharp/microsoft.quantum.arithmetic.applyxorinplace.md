---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721396"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="49ccd-102">ApplyXorInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="49ccd-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="49ccd-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="49ccd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="49ccd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49ccd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49ccd-105">Egy bitenkénti műveletet alkalmaz egy klasszikus egész szám és egy olyan egész szám között, amelyet a qubits regisztere képvisel.</span><span class="sxs-lookup"><span data-stu-id="49ccd-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="49ccd-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="49ccd-106">Description</span></span>

<span data-ttu-id="49ccd-107">A `X` qubits egy kis endian-regisztráción alapuló műveleteket alkalmaz egy egész számban 1 bit alapján.</span><span class="sxs-lookup"><span data-stu-id="49ccd-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="49ccd-108">Tegyük fel `value` , hogy az a és az y legyen előjel nélküli egész szám, amely `target` `InPlaceXorLE` a következő Térkép által megadott műveletet hajtja végre: $ \ket{y}\rightarrow \ket{y\oplus a} $, ahol a $ \oplus $ a bitenkénti kizárólagos vagy operátor.</span><span class="sxs-lookup"><span data-stu-id="49ccd-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="49ccd-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="49ccd-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="49ccd-110">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49ccd-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49ccd-111">Egy egész szám, amelynek feltételezett értéke nem negatív.</span><span class="sxs-lookup"><span data-stu-id="49ccd-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="49ccd-112">cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="49ccd-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="49ccd-113">Olyan kvantum-regiszter, amely `value` kis endian kódolásban való tárolásra szolgál.</span><span class="sxs-lookup"><span data-stu-id="49ccd-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49ccd-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49ccd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

