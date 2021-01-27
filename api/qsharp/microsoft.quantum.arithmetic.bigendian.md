---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843392"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="3867d-102">BigEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="3867d-102">BigEndian user defined type</span></span>

<span data-ttu-id="3867d-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3867d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3867d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3867d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3867d-105">Regisztrálja, hogy a rendszer egy előjel nélküli egész számot kódol a big-endian sorrendben.</span><span class="sxs-lookup"><span data-stu-id="3867d-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="3867d-106">Az indextel rendelkező qubit `0` a legmagasabb, előjel nélküli egész számot kódolja.</span><span class="sxs-lookup"><span data-stu-id="3867d-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="3867d-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="3867d-107">Remarks</span></span>

<span data-ttu-id="3867d-108">`BigEndian` `BE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="3867d-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>