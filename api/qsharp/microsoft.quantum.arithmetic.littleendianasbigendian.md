---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843078"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="a5a1b-102">LittleEndianAsBigEndian függvény</span><span class="sxs-lookup"><span data-stu-id="a5a1b-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="a5a1b-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a5a1b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a5a1b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5a1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5a1b-105">Egy `LittleEndian` qubit-regisztrációt alakít át egy `BigEndian` qubit-regiszterbe a qubit sorrend megfordításával.</span><span class="sxs-lookup"><span data-stu-id="a5a1b-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="a5a1b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a5a1b-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="a5a1b-107">bemenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a5a1b-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a5a1b-108">A Qubit-regisztráció `LittleEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="a5a1b-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="a5a1b-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="a5a1b-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="a5a1b-110">A Qubit-regisztráció `BigEndian` formátuma.</span><span class="sxs-lookup"><span data-stu-id="a5a1b-110">Qubit register in `BigEndian` format.</span></span>