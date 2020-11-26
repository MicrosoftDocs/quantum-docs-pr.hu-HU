---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222779"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="80928-102">LittleEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="80928-102">LittleEndian user defined type</span></span>

<span data-ttu-id="80928-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80928-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80928-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80928-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80928-105">Regisztrálja, hogy az előjel nélküli egész számot kódolja kis endian sorrendben.</span><span class="sxs-lookup"><span data-stu-id="80928-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="80928-106">Az indextel rendelkező qubit `0` egy előjel nélküli egész szám legalacsonyabb részét kódolja.</span><span class="sxs-lookup"><span data-stu-id="80928-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="80928-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="80928-107">Remarks</span></span>

<span data-ttu-id="80928-108">`LittleEndian` `LE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="80928-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>