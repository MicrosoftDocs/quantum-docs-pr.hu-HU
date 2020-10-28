---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721048"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="22578-102">LittleEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="22578-102">LittleEndian user defined type</span></span>

<span data-ttu-id="22578-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="22578-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="22578-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22578-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22578-105">Regisztrálja, hogy az előjel nélküli egész számot kódolja kis endian sorrendben.</span><span class="sxs-lookup"><span data-stu-id="22578-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="22578-106">Az indextel rendelkező qubit `0` egy előjel nélküli egész szám legalacsonyabb részét kódolja.</span><span class="sxs-lookup"><span data-stu-id="22578-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="22578-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="22578-107">Remarks</span></span>

<span data-ttu-id="22578-108">`LittleEndian` `LE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="22578-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>