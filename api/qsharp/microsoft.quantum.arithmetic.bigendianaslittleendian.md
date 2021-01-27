---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843369"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="f42cc-102">BigEndianAsLittleEndian függvény</span><span class="sxs-lookup"><span data-stu-id="f42cc-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="f42cc-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f42cc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f42cc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f42cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f42cc-105">Egy `BigEndian` qubit-regisztrációt alakít át egy `LittleEndian` qubit-regiszterbe a qubit sorrend megfordításával.</span><span class="sxs-lookup"><span data-stu-id="f42cc-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="f42cc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f42cc-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="f42cc-107">bemenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="f42cc-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="f42cc-108">A Qubit-regisztráció `BigEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="f42cc-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="f42cc-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f42cc-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f42cc-110">A Qubit-regisztráció `LittleEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="f42cc-110">Qubit register in `LittleEndian` format.</span></span>