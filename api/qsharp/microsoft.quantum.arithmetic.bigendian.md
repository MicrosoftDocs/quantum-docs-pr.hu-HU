---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223663"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="6b0e4-102">BigEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="6b0e4-102">BigEndian user defined type</span></span>

<span data-ttu-id="6b0e4-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6b0e4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6b0e4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b0e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b0e4-105">Regisztrálja, hogy a rendszer egy előjel nélküli egész számot kódol a big-endian sorrendben.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="6b0e4-106">Az indextel rendelkező qubit `0` a legmagasabb, előjel nélküli egész számot kódolja.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="6b0e4-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6b0e4-107">Remarks</span></span>

<span data-ttu-id="6b0e4-108">`BigEndian` `BE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>