---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847350"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="f289f-102">ComplexPolar-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="f289f-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="f289f-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f289f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f289f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f289f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f289f-105">A poláris formában lévő összetett számot jelöli.</span><span class="sxs-lookup"><span data-stu-id="f289f-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="f289f-106">Egy összetett szám poláris ábrázolása $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="f289f-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="f289f-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="f289f-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="f289f-108">Nagyság: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f289f-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f289f-109">Az abszolút érték $r \ge $0 $c $.</span><span class="sxs-lookup"><span data-stu-id="f289f-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="f289f-110">Argumentum: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f289f-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f289f-111">A fázis $t \in \mathbb R $ $c $.</span><span class="sxs-lookup"><span data-stu-id="f289f-111">The phase $t \in \mathbb R$ of $c$.</span></span>