---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: 7f66af8a1f6f9ab83740fbf5dcfaf55776d74eb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853394"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="d75ac-102">DumpReferenceAndTarget művelet</span><span class="sxs-lookup"><span data-stu-id="d75ac-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="d75ac-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d75ac-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d75ac-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d75ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d75ac-105">A a DumpRegister használatával biztosítja a diagnosztika állapotát a hivatkozás és a cél regisztrálása tekintetében.</span><span class="sxs-lookup"><span data-stu-id="d75ac-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="d75ac-106">Külön műveletként van megjelölve, amely lehetővé teszi a felülbírálást és az értelmezést különálló regiszterként, nem pedig egyetlen kombinált regisztrációként.</span><span class="sxs-lookup"><span data-stu-id="d75ac-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d75ac-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d75ac-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="d75ac-108">hivatkozás: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d75ac-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="d75ac-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d75ac-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="d75ac-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d75ac-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

