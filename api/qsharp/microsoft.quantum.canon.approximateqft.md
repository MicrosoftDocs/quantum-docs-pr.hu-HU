---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716776"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="c49af-102">ApproximateQFT művelet</span><span class="sxs-lookup"><span data-stu-id="c49af-102">ApproximateQFT operation</span></span>

<span data-ttu-id="c49af-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c49af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c49af-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c49af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c49af-105">Alkalmazza a becsült kvantum Fourier-transzformációt (AQFT) a kvantum-regiszterre.</span><span class="sxs-lookup"><span data-stu-id="c49af-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c49af-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c49af-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c49af-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c49af-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c49af-108">a közelítési paraméter, amely meghatározza, hogy az QFT áramkörben lévő vezérelt Z-Forgások milyen szinten vannak metszve.</span><span class="sxs-lookup"><span data-stu-id="c49af-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="c49af-109">Az a közelítő paraméter meghatározza a Z-Forgások (∈: {0.. n}) és az összes Z-forgás (2π/2k) metszési szintjét, ahol a k>a QFT-áramkörből el lett távolítva.</span><span class="sxs-lookup"><span data-stu-id="c49af-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="c49af-110">Ismert, hogy a k >= log ₂ (n) + log ₂ (1/ε) + 3 lehet kötve | | QFT – AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="c49af-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="c49af-111">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="c49af-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="c49af-112">az n qubits kvantum-regisztrálása, amelyhez a rendszer a megközelítőleges kvantum Fourier-transzformációt alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="c49af-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c49af-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c49af-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c49af-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c49af-114">Remarks</span></span>

<span data-ttu-id="c49af-115">A AQFT a 2π/2k és a Hadamard Gates formátumú Z-rotációs kapukat igényli.</span><span class="sxs-lookup"><span data-stu-id="c49af-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="c49af-116">A bemenet és a kimenet a big endian kódolásban való kódolásra van feltételezve.</span><span class="sxs-lookup"><span data-stu-id="c49af-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="c49af-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="c49af-117">References</span></span>

- [<span data-ttu-id="c49af-118">*M. Roetteler, th. Beth* , kiegyenlített. algebra ENG. communis. Számítógépf. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="c49af-118"> *M. Roetteler, Th. Beth* , Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="c49af-119">*D. Coppersmith* arXiv: Quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="c49af-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)