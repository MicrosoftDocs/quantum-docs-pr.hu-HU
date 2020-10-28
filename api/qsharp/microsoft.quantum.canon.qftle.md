---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715642"
---
# <a name="qftle-operation"></a><span data-ttu-id="647de-102">QFTLE művelet</span><span class="sxs-lookup"><span data-stu-id="647de-102">QFTLE operation</span></span>

<span data-ttu-id="647de-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="647de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="647de-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="647de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="647de-105">Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a kis endian ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="647de-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="647de-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="647de-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="647de-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="647de-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="647de-108">A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik</span><span class="sxs-lookup"><span data-stu-id="647de-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="647de-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="647de-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="647de-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="647de-110">Remarks</span></span>

<span data-ttu-id="647de-111">A bemenet és a kimenet kis endian-kódolásban van feltételezve.</span><span class="sxs-lookup"><span data-stu-id="647de-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="647de-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="647de-112">See Also</span></span>

- [<span data-ttu-id="647de-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="647de-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)