---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721360"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="c3b8a-102">BigEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="c3b8a-102">BigEndian user defined type</span></span>

<span data-ttu-id="c3b8a-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c3b8a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c3b8a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3b8a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3b8a-105">Regisztrálja, hogy a rendszer egy előjel nélküli egész számot kódol a big-endian sorrendben.</span><span class="sxs-lookup"><span data-stu-id="c3b8a-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="c3b8a-106">Az indextel rendelkező qubit `0` a legmagasabb, előjel nélküli egész számot kódolja.</span><span class="sxs-lookup"><span data-stu-id="c3b8a-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="c3b8a-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c3b8a-107">Remarks</span></span>

<span data-ttu-id="c3b8a-108">`BigEndian` `BE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="c3b8a-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>