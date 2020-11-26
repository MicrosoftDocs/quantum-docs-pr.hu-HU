---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216115"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="f61fa-102">MeasureIdentity művelet</span><span class="sxs-lookup"><span data-stu-id="f61fa-102">MeasureIdentity operation</span></span>

<span data-ttu-id="f61fa-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f61fa-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f61fa-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f61fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f61fa-105">Megméri az Identity operátort a qubits-regisztrációban.</span><span class="sxs-lookup"><span data-stu-id="f61fa-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="f61fa-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f61fa-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="f61fa-107">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f61fa-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f61fa-108">A mérendő regisztráció.</span><span class="sxs-lookup"><span data-stu-id="f61fa-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f61fa-109">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="f61fa-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="f61fa-110">Az eredmény értéke `Zero` .</span><span class="sxs-lookup"><span data-stu-id="f61fa-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f61fa-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f61fa-111">Remarks</span></span>

<span data-ttu-id="f61fa-112">Mivel a $ \boldone $ csak a $1 $ sajátérték, és nem rendelkezik negatív sajátérték, ez a művelet mindig visszatér `Zero` , amely a sajátérték $ + 1 = (-1) ^ 0 $ értéknek felel meg, és nem okozza az állapot összeomlását `register` .</span><span class="sxs-lookup"><span data-stu-id="f61fa-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="f61fa-113">Önmagában ez a művelet nem hasznos, de a Process tomográfia környezetében hasznos, mivel információt nyújt a kvantum-folyamat nyomon követésének megőrzéséről.</span><span class="sxs-lookup"><span data-stu-id="f61fa-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="f61fa-114">A veszteséges mérést biztosító célszámítógép például a $ \boldone $ tényleges mérésével helyettesíti ezt a műveletet.</span><span class="sxs-lookup"><span data-stu-id="f61fa-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>