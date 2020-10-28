---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721024"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="2a5d6-102">LittleEndianAsBigEndian függvény</span><span class="sxs-lookup"><span data-stu-id="2a5d6-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="2a5d6-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2a5d6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2a5d6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a5d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a5d6-105">Egy `LittleEndian` qubit-regisztrációt alakít át egy `BigEndian` qubit-regiszterbe a qubit sorrend megfordításával.</span><span class="sxs-lookup"><span data-stu-id="2a5d6-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="2a5d6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2a5d6-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="2a5d6-107">bemenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2a5d6-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2a5d6-108">A Qubit-regisztráció `LittleEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="2a5d6-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="2a5d6-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="2a5d6-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="2a5d6-110">A Qubit-regisztráció `BigEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="2a5d6-110">Qubit register in `BigEndian` format.</span></span>