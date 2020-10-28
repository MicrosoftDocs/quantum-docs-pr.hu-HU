---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722072"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="adbee-102">BlockEncodingToReflection függvény</span><span class="sxs-lookup"><span data-stu-id="adbee-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="adbee-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="adbee-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="adbee-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="adbee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="adbee-105">Az a- `BlockEncoding` t megfelelőre konvertálja `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="adbee-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="adbee-106">Ez olyan `BlockEncoding` egységes $U $-t kap, amely egyes operátorok $H $ kamatot kódol, $U "$-re konvertálja `BlockEncodingReflection` , amely ugyanazt a kezelőt kódolja, de a $U" ^ \Dagger = U "$-t is kielégíti.</span><span class="sxs-lookup"><span data-stu-id="adbee-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="adbee-107">Ez növeli a $U $ kiegészítő regisztrációjának méretét egy qubit.</span><span class="sxs-lookup"><span data-stu-id="adbee-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="adbee-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="adbee-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="adbee-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="adbee-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="adbee-110">Egy `BlockEncoding` egységes $U $, amely átalakítható reflexióba.</span><span class="sxs-lookup"><span data-stu-id="adbee-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="adbee-111">Kimenet: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="adbee-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="adbee-112">Egy egységes $U ' $, amely közösen működik a regisztereken `a` `s` , és blokkolja a $H $ kódolást, és megfelel a (z) "^ \Dagger = U" $ $U.</span><span class="sxs-lookup"><span data-stu-id="adbee-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="adbee-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="adbee-113">Remarks</span></span>

<span data-ttu-id="adbee-114">Ez növeli a $U $ kiegészítő regisztrációjának méretét egy qubit.</span><span class="sxs-lookup"><span data-stu-id="adbee-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="adbee-115">Referencia</span><span class="sxs-lookup"><span data-stu-id="adbee-115">References</span></span>

- <span data-ttu-id="adbee-116">Hamilton szimuláció a Qubitization Guang felfüggeszti Hao Low, Isaac L. a https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="adbee-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="adbee-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="adbee-117">See Also</span></span>

- [<span data-ttu-id="adbee-118">Microsoft. Quantum. szimulációs. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="adbee-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="adbee-119">Microsoft. Quantum. szimulációs. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="adbee-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)