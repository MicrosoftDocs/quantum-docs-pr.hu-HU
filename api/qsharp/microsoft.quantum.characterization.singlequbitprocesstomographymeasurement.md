---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714928"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="9cb2c-102">SingleQubitProcessTomographyMeasurement művelet</span><span class="sxs-lookup"><span data-stu-id="9cb2c-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="9cb2c-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="9cb2c-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="9cb2c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cb2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cb2c-105">Egy qubit-alapú Process tomográfia-mérést hajt végre Pauli alapon, egy adott érdeklődési csatornán keresztül.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="9cb2c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9cb2c-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="9cb2c-107">előkészítés: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9cb2c-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9cb2c-108">A Pauli-alapú elem $P $, amelyben a qubit elő kell készíteni.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="9cb2c-109">mérés: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9cb2c-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9cb2c-110">A Pauli-alapú elem $Q $, amelyben a qubit mérni kell.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="9cb2c-111">csatorna: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9cb2c-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9cb2c-112">Egyetlen qubit-csatorna $ \Lambda $, amelynek viselkedését a Process tomográfia becsüli.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9cb2c-113">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="9cb2c-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9cb2c-114">Az eredmény a `Zero` következő valószínűséggel: $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="9cb2c-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="9cb2c-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9cb2c-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="9cb2c-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9cb2c-116">Remarks</span></span>

<span data-ttu-id="9cb2c-117">A művelet által visszaadott eredmények eloszlása a qubit állami tomográfia különleges esete.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="9cb2c-118">Engedje, hogy a $ \rho = J (\Lambda)/$2 legyen a Choi – Jamiłkowski ($ \Lambda $) állapot.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="9cb2c-119">Ezután a fenti eloszlás megegyezik a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $, ahol a $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 a $P $ és $Q $ értéknek megfelelő tényleges mérés.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>