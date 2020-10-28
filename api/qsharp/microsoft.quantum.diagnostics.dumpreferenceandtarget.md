---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: f791f6f1e3c1b1da14ac3548a4bd78bb4f24ff83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712856"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="ddbe3-102">DumpReferenceAndTarget művelet</span><span class="sxs-lookup"><span data-stu-id="ddbe3-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="ddbe3-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ddbe3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ddbe3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddbe3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddbe3-105">A a DumpRegister használatával biztosítja a diagnosztika állapotát a hivatkozás és a cél regisztrálása tekintetében.</span><span class="sxs-lookup"><span data-stu-id="ddbe3-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="ddbe3-106">Külön műveletként van megjelölve, amely lehetővé teszi a felülbírálást és az értelmezést különálló regiszterként, nem pedig egyetlen kombinált regisztrációként.</span><span class="sxs-lookup"><span data-stu-id="ddbe3-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ddbe3-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ddbe3-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="ddbe3-108">hivatkozás: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ddbe3-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="ddbe3-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ddbe3-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="ddbe3-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddbe3-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

