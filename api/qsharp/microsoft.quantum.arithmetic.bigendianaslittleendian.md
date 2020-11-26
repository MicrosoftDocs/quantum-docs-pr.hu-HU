---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 5f5d7dc6e08a13fbdc45f9d11c93c29cfcf90bf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223629"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="95509-102">BigEndianAsLittleEndian függvény</span><span class="sxs-lookup"><span data-stu-id="95509-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="95509-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="95509-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="95509-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95509-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95509-105">Egy `BigEndian` qubit-regisztrációt alakít át egy `LittleEndian` qubit-regiszterbe a qubit sorrend megfordításával.</span><span class="sxs-lookup"><span data-stu-id="95509-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="95509-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="95509-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="95509-107">bemenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="95509-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="95509-108">A Qubit-regisztráció `BigEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="95509-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="95509-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="95509-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="95509-110">A Qubit-regisztráció `LittleEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="95509-110">Qubit register in `LittleEndian` format.</span></span>