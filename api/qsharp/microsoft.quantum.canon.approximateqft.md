---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850324"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="00e35-102">ApproximateQFT művelet</span><span class="sxs-lookup"><span data-stu-id="00e35-102">ApproximateQFT operation</span></span>

<span data-ttu-id="00e35-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00e35-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00e35-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00e35-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00e35-105">Alkalmazza a becsült kvantum Fourier-transzformációt (AQFT) a kvantum-regiszterre.</span><span class="sxs-lookup"><span data-stu-id="00e35-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="00e35-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="00e35-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="00e35-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00e35-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00e35-108">a közelítési paraméter, amely meghatározza, hogy az QFT áramkörben lévő vezérelt Z-Forgások milyen szinten vannak metszve.</span><span class="sxs-lookup"><span data-stu-id="00e35-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="00e35-109">Az a közelítő paraméter meghatározza a Z-Forgások (∈: {0.. n}) és az összes Z-forgás (2π/2k) metszési szintjét, ahol a k>a QFT-áramkörből el lett távolítva.</span><span class="sxs-lookup"><span data-stu-id="00e35-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="00e35-110">Ismert, hogy a k >= log ₂ (n) + log ₂ (1/ε) + 3 lehet kötve | | QFT – AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="00e35-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="00e35-111">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="00e35-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="00e35-112">az n qubits kvantum-regisztrálása, amelyhez a rendszer a megközelítőleges kvantum Fourier-transzformációt alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="00e35-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00e35-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00e35-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="00e35-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="00e35-114">Remarks</span></span>

<span data-ttu-id="00e35-115">A AQFT a 2π/2k és a Hadamard Gates formátumú Z-rotációs kapukat igényli.</span><span class="sxs-lookup"><span data-stu-id="00e35-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="00e35-116">A bemenet és a kimenet a big endian kódolásban való kódolásra van feltételezve.</span><span class="sxs-lookup"><span data-stu-id="00e35-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="00e35-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="00e35-117">References</span></span>

- [<span data-ttu-id="00e35-118">*M. Roetteler, th. Beth*, kiegyenlített. algebra ENG. communis. Számítógépf. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="00e35-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="00e35-119">*D. Coppersmith* arXiv: Quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="00e35-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)