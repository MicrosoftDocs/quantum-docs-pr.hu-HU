---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852277"
---
# <a name="qftle-operation"></a><span data-ttu-id="c7a9a-102">QFTLE művelet</span><span class="sxs-lookup"><span data-stu-id="c7a9a-102">QFTLE operation</span></span>

<span data-ttu-id="c7a9a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7a9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7a9a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7a9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7a9a-105">Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a kis endian ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="c7a9a-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c7a9a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c7a9a-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="c7a9a-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7a9a-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c7a9a-108">A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik</span><span class="sxs-lookup"><span data-stu-id="c7a9a-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7a9a-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7a9a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c7a9a-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c7a9a-110">Remarks</span></span>

<span data-ttu-id="c7a9a-111">A bemenet és a kimenet kis endian-kódolásban van feltételezve.</span><span class="sxs-lookup"><span data-stu-id="c7a9a-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7a9a-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c7a9a-112">See Also</span></span>

- [<span data-ttu-id="c7a9a-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="c7a9a-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)