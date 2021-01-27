---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843472"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="a4b53-102">ApplyXorInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="a4b53-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="a4b53-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a4b53-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a4b53-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4b53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4b53-105">Egy bitenkénti műveletet alkalmaz egy klasszikus egész szám és egy olyan egész szám között, amelyet a qubits regisztere képvisel.</span><span class="sxs-lookup"><span data-stu-id="a4b53-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a4b53-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a4b53-106">Description</span></span>

<span data-ttu-id="a4b53-107">A `X` qubits egy kis endian-regisztráción alapuló műveleteket alkalmaz egy egész számban 1 bit alapján.</span><span class="sxs-lookup"><span data-stu-id="a4b53-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="a4b53-108">Tegyük fel `value` , hogy az a és az y legyen előjel nélküli egész szám, amely `target` `InPlaceXorLE` a következő Térkép által megadott műveletet hajtja végre: $ \ket{y}\rightarrow \ket{y\oplus a} $, ahol a $ \oplus $ a bitenkénti kizárólagos vagy operátor.</span><span class="sxs-lookup"><span data-stu-id="a4b53-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="a4b53-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a4b53-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a4b53-110">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4b53-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a4b53-111">Egy egész szám, amelynek feltételezett értéke nem negatív.</span><span class="sxs-lookup"><span data-stu-id="a4b53-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="a4b53-112">cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a4b53-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a4b53-113">Olyan kvantum-regiszter, amely `value` kis endian kódolásban való tárolásra szolgál.</span><span class="sxs-lookup"><span data-stu-id="a4b53-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4b53-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4b53-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

