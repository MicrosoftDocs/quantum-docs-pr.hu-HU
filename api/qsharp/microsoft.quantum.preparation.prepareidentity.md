---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210437"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="2f45f-102">PrepareIdentity művelet</span><span class="sxs-lookup"><span data-stu-id="2f45f-102">PrepareIdentity operation</span></span>

<span data-ttu-id="2f45f-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2f45f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2f45f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f45f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f45f-105">A regisztrációt követően a rendszer felkészíti a regisztrációt a maximálisan vegyes állapotba.</span><span class="sxs-lookup"><span data-stu-id="2f45f-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="2f45f-106">A regisztráció előkészítése a $ \boldone/2 ^ N $ állapotban történik a teljes depolarizációs csatorna minden qubit való alkalmazásával, ahol a $N $ a regisztráció hossza.</span><span class="sxs-lookup"><span data-stu-id="2f45f-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2f45f-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2f45f-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="2f45f-108">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2f45f-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2f45f-109">Olyan regisztráció, amelynek állapotát a fent leírt módon kell leállítani.</span><span class="sxs-lookup"><span data-stu-id="2f45f-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f45f-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f45f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2f45f-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2f45f-111">See Also</span></span>

- [<span data-ttu-id="2f45f-112">Microsoft. Quantum. előkészítés. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="2f45f-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)