---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845225"
---
# <a name="andladder-operation"></a><span data-ttu-id="39aeb-102">AndLadder művelet</span><span class="sxs-lookup"><span data-stu-id="39aeb-102">AndLadder operation</span></span>

<span data-ttu-id="39aeb-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39aeb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39aeb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39aeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39aeb-105">Felügyelt "és létra" műveletet hajt végre a célként megadott qubits regisztrálásakor.</span><span class="sxs-lookup"><span data-stu-id="39aeb-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="39aeb-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="39aeb-106">Description</span></span>

<span data-ttu-id="39aeb-107">Ez a művelet egy átalakítást alkalmaz, amely a következő hozzárendeléssel van elvégezve: számítási alap, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $, ahol $ \ket{x \_ 1, \dots, x \_ n} $ a számítási állapotára hivatkozik `controls` , és ahol $ \ket{y \_ 1, \dots, y \_ {n-1}} $ a számítási állapotára hivatkozik `targets` .</span><span class="sxs-lookup"><span data-stu-id="39aeb-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="39aeb-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="39aeb-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="39aeb-109">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="39aeb-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="39aeb-110">A CCNOT kapu, amelyet az építkezéshez használni szeretne.</span><span class="sxs-lookup"><span data-stu-id="39aeb-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="39aeb-111">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39aeb-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39aeb-112">A és a létra vezérlőelemként használandó qubits.</span><span class="sxs-lookup"><span data-stu-id="39aeb-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="39aeb-113">Ezzel a művelettel a Invariant állapotú számítási alapú állapotok maradnak `controls` .</span><span class="sxs-lookup"><span data-stu-id="39aeb-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="39aeb-114">A hosszának legalább 2 karakterből kell állnia, és a hosszának meg kell `controls` egyeznie `targets` .</span><span class="sxs-lookup"><span data-stu-id="39aeb-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="39aeb-115">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39aeb-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39aeb-116">A hosszának `targets` legalább 1-nek kell lennie, és meg kell egyeznie a `controls` mínusz egy hosszával.</span><span class="sxs-lookup"><span data-stu-id="39aeb-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39aeb-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39aeb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39aeb-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="39aeb-118">Remarks</span></span>

- <span data-ttu-id="39aeb-119">A és a részeként használatos <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="39aeb-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="39aeb-120">A magyarázathoz és az áramköri diagramhoz lásd a 4,10., 4,3-es szakaszt a Nielsen &.</span><span class="sxs-lookup"><span data-stu-id="39aeb-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="39aeb-121">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="39aeb-121">References</span></span>

- [<span data-ttu-id="39aeb-122">*Michael A. Nielsen, Isaac L.*, a Quantum számítási és a kvantum-információk</span><span class="sxs-lookup"><span data-stu-id="39aeb-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)