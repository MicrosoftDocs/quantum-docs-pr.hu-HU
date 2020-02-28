---
title: 'Típus konverziók a Q # standard könyvtárakban'
description: 'Az általános és a felhasználó által definiált típusú átalakítási függvények ismertetése a Q # standard kódtárakban.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907800"
---
# <a name="type-conversions"></a><span data-ttu-id="30e5f-103">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="30e5f-103">Type Conversions</span></span> #

<span data-ttu-id="30e5f-104">A Q # egy **határozottan gépelt** nyelv.</span><span class="sxs-lookup"><span data-stu-id="30e5f-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="30e5f-105">Különösen a Q # nem végez implicit módon különböző típusok között.</span><span class="sxs-lookup"><span data-stu-id="30e5f-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="30e5f-106">Például `1 + 2.0` nem érvényes Q # kifejezés.</span><span class="sxs-lookup"><span data-stu-id="30e5f-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="30e5f-107">A Q # Ehelyett számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="30e5f-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="30e5f-108">Például <xref:microsoft.quantum.core.length> `Int`kimeneti típusa van, ezért a kimenetét először egy `Double`ra kell konvertálni, mielőtt egy lebegőpontos kifejezés részeként lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="30e5f-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="30e5f-109">Ezt a <xref:microsoft.quantum.convert.intasdouble> függvény használatával teheti meg:</span><span class="sxs-lookup"><span data-stu-id="30e5f-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="30e5f-110">A <xref:microsoft.quantum.convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például `Int`, `Double`, `BigInt`, `Result`és `Bool`) használatához:</span><span class="sxs-lookup"><span data-stu-id="30e5f-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="30e5f-111">A <xref:microsoft.quantum.convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation`, amely a függvényeket `'T -> 'U` új műveleti `'T => 'U`alakítja át.</span><span class="sxs-lookup"><span data-stu-id="30e5f-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="30e5f-112">Végül a Q # standard Library számos felhasználó által definiált típust tartalmaz, például <xref:microsoft.quantum.math.complex> és <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="30e5f-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="30e5f-113">Ezen típusok mellett a szabványos függvénytár olyan funkciókat is biztosít, mint például a <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="30e5f-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
