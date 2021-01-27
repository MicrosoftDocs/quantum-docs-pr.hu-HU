---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846569"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="e43f6-102">LittleEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="e43f6-102">LittleEndian user defined type</span></span>

<span data-ttu-id="e43f6-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e43f6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e43f6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e43f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e43f6-105">Regisztrálja, hogy az előjel nélküli egész számot kódolja kis endian sorrendben.</span><span class="sxs-lookup"><span data-stu-id="e43f6-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="e43f6-106">Az indextel rendelkező qubit `0` egy előjel nélküli egész szám legalacsonyabb részét kódolja.</span><span class="sxs-lookup"><span data-stu-id="e43f6-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="e43f6-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e43f6-107">Remarks</span></span>

<span data-ttu-id="e43f6-108">`LittleEndian` `LE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="e43f6-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>