---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216030"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="3ab81-102">HTermToGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="3ab81-102">HTermToGenIdx function</span></span>

<span data-ttu-id="3ab81-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3ab81-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="3ab81-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3ab81-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3ab81-105">Hamilton-kifejezést alakít át `HTerm` adatformátumba egy GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="3ab81-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="3ab81-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3ab81-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="3ab81-107">kifejezés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="3ab81-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="3ab81-108">Bemeneti adatok `HTerm` formátumban.</span><span class="sxs-lookup"><span data-stu-id="3ab81-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="3ab81-109">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3ab81-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3ab81-110">További információ a GeneratorIndex-hez.</span><span class="sxs-lookup"><span data-stu-id="3ab81-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="3ab81-111">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3ab81-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3ab81-112">A által reprezentált Hamilton kifejezést képviselő GeneratorIndex `term` , a által hozzáadott további információkkal együtt `termType` .</span><span class="sxs-lookup"><span data-stu-id="3ab81-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>