---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846486"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="a3d1d-102">ReversedOpBE függvény</span><span class="sxs-lookup"><span data-stu-id="a3d1d-102">ReversedOpBE function</span></span>

<span data-ttu-id="a3d1d-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3d1d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3d1d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3d1d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3d1d-105">Olyan művelet miatt, amely nagy endian adatbevitelt igényel, egy új műveletet ad vissza, amely egy kis endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="a3d1d-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="a3d1d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a3d1d-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="a3d1d-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3d1d-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a3d1d-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="a3d1d-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="a3d1d-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3d1d-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a3d1d-110">Új művelet, amely kis endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="a3d1d-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3d1d-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a3d1d-111">See Also</span></span>

- [<span data-ttu-id="a3d1d-112">Microsoft. Quantum. aritmetika. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="a3d1d-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="a3d1d-113">Microsoft. Quantum. aritmetika. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="a3d1d-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="a3d1d-114">Microsoft. Quantum. aritmetika. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="a3d1d-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="a3d1d-115">Microsoft. Quantum. aritmetika. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="a3d1d-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)