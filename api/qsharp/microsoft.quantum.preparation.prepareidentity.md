---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855878"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="70165-102">PrepareIdentity művelet</span><span class="sxs-lookup"><span data-stu-id="70165-102">PrepareIdentity operation</span></span>

<span data-ttu-id="70165-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="70165-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="70165-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70165-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70165-105">A regisztrációt követően a rendszer felkészíti a regisztrációt a maximálisan vegyes állapotba.</span><span class="sxs-lookup"><span data-stu-id="70165-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="70165-106">A regisztráció előkészítése a $ \boldone/2 ^ N $ állapotban történik a teljes depolarizációs csatorna minden qubit való alkalmazásával, ahol a $N $ a regisztráció hossza.</span><span class="sxs-lookup"><span data-stu-id="70165-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="70165-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="70165-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="70165-108">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70165-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70165-109">Olyan regisztráció, amelynek állapotát a fent leírt módon kell leállítani.</span><span class="sxs-lookup"><span data-stu-id="70165-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70165-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70165-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="70165-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="70165-111">See Also</span></span>

- [<span data-ttu-id="70165-112">Microsoft. Quantum. előkészítés. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="70165-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)