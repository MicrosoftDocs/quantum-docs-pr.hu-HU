---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722689"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="3e0c9-102">BlockEncoding-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="3e0c9-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="3e0c9-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3e0c9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3e0c9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e0c9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e0c9-105">Olyan egységes, amelyben a kamatot egy tetszőleges operátor kódolja a bal felső blokkban.</span><span class="sxs-lookup"><span data-stu-id="3e0c9-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="3e0c9-106">Ez az egy `BlockEncoding` egységes $U $ $, ahol a rendszerregisztrációt végző tetszőleges operátor $H $ értékű, a `s` \ket _a $ kiegészítő állapotnak megfelelő bal felső blokkban kódolva {0} .</span><span class="sxs-lookup"><span data-stu-id="3e0c9-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="3e0c9-107">az</span><span class="sxs-lookup"><span data-stu-id="3e0c9-107">That is,</span></span>

<span data-ttu-id="3e0c9-108">$ $ \begin{align} (\bra {0} _a \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="3e0c9-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

