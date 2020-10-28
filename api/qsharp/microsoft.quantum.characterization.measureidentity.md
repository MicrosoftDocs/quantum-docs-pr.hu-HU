---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714970"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="4e805-102">MeasureIdentity művelet</span><span class="sxs-lookup"><span data-stu-id="4e805-102">MeasureIdentity operation</span></span>

<span data-ttu-id="4e805-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4e805-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="4e805-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e805-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e805-105">Megméri az Identity operátort a qubits-regisztrációban.</span><span class="sxs-lookup"><span data-stu-id="4e805-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="4e805-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4e805-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="4e805-107">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4e805-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4e805-108">A mérendő regisztráció.</span><span class="sxs-lookup"><span data-stu-id="4e805-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4e805-109">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="4e805-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="4e805-110">Az eredmény értéke `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4e805-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e805-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4e805-111">Remarks</span></span>

<span data-ttu-id="4e805-112">Mivel a $ \boldone $ csak a $1 $ sajátérték, és nem rendelkezik negatív sajátérték, ez a művelet mindig visszatér `Zero` , amely a sajátérték $ + 1 = (-1) ^ 0 $ értéknek felel meg, és nem okozza az állapot összeomlását `register` .</span><span class="sxs-lookup"><span data-stu-id="4e805-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="4e805-113">Önmagában ez a művelet nem hasznos, de a Process tomográfia környezetében hasznos, mivel információt nyújt a kvantum-folyamat nyomon követésének megőrzéséről.</span><span class="sxs-lookup"><span data-stu-id="4e805-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="4e805-114">A veszteséges mérést biztosító célszámítógép például a $ \boldone $ tényleges mérésével helyettesíti ezt a műveletet.</span><span class="sxs-lookup"><span data-stu-id="4e805-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>