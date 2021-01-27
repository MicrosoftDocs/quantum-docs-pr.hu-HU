---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845053"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="20584-102">ApplyFermionicSWAP művelet</span><span class="sxs-lookup"><span data-stu-id="20584-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="20584-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20584-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20584-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20584-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20584-105">A Fermionic-csere alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="20584-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="20584-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="20584-106">Description</span></span>

<span data-ttu-id="20584-107">Ez lényegében felcseréli a qubits, miközben a-1 globális fázist alkalmazza, ha mindkettő qubits: 1s.</span><span class="sxs-lookup"><span data-stu-id="20584-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="20584-108">Megőrzi a symmetrization.</span><span class="sxs-lookup"><span data-stu-id="20584-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="20584-109">További információ: .</span><span class="sxs-lookup"><span data-stu-id="20584-109">See  for more information.</span></span>

<span data-ttu-id="20584-110">Ezt a műveletet az egységes operátor \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="20584-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="20584-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="20584-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="20584-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="20584-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="20584-113">qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="20584-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="20584-114">Az első felcserélni kívánt qubit.</span><span class="sxs-lookup"><span data-stu-id="20584-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="20584-115">qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="20584-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="20584-116">A második qubit kell felcserélni.</span><span class="sxs-lookup"><span data-stu-id="20584-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20584-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20584-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="20584-118">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="20584-118">References</span></span>

- [<span data-ttu-id="20584-119">*Ryan Babbush, Nathan Wiebe, Fahamvas McClean, James McClain, Hartmut neven, gránát Kin-Lic Chan*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="20584-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="20584-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="20584-120">See Also</span></span>

- [<span data-ttu-id="20584-121">Microsoft. Quantum. belső. SWAP</span><span class="sxs-lookup"><span data-stu-id="20584-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)