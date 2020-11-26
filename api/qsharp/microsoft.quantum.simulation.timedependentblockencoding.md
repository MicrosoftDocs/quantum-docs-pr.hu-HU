---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 8fade22dca7af16a567a88f4413c8e9dcc1604b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203501"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="113b3-102">TimeDependentBlockEncoding-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="113b3-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="113b3-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="113b3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="113b3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="113b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="113b3-105">Egy `BlockEncoding` óra-regiszter által vezérelt egy.</span><span class="sxs-lookup"><span data-stu-id="113b3-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="113b3-106">Vagyis a egy olyan `TimeDependentBlockEncoding` egységes $U $, amely a $ \ket{k} _D $ értékű állapotot vezérli úgy, `d` hogy egy tetszőleges operátor $H _K $-t, amely a rendszerregisztrálás során működik, `s` a \ket _a $ kiegészítő állapotnak megfelelő bal felső blokkban kódolva {0} .</span><span class="sxs-lookup"><span data-stu-id="113b3-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="113b3-107">az</span><span class="sxs-lookup"><span data-stu-id="113b3-107">That is,</span></span>

<span data-ttu-id="113b3-108">$ $ \begin{align} (\bra {0} \_ a\otimes I_ {DS}) U (\ket {0} \_ a\otimes I_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="113b3-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="113b3-109">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="113b3-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

