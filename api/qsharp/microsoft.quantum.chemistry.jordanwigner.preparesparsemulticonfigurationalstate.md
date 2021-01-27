---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: PrepareSparseMultiConfigurationalState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 49b93d0f2447e9eee503bb6ee26aef46c4f5e3f2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98836064"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="a5b1b-102">PrepareSparseMultiConfigurationalState művelet</span><span class="sxs-lookup"><span data-stu-id="a5b1b-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="a5b1b-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a5b1b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a5b1b-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a5b1b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a5b1b-105">Ritka, többkonfigurációs állapot előkészítése próbaverziós állapothoz a kezdeti próbaverziós állapotba való felizgatás hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="a5b1b-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a5b1b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a5b1b-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="a5b1b-107">initialStatePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5b1b-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a5b1b-108">A kezdeti próbaverziós állapot előkészítésének egységesje.</span><span class="sxs-lookup"><span data-stu-id="a5b1b-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="a5b1b-109">izgalom: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="a5b1b-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="a5b1b-110">A gerjesztő a gerjesztés és a qubit indexek által képviselt kezdeti próbaverziós állapot izgatása.</span><span class="sxs-lookup"><span data-stu-id="a5b1b-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a5b1b-111">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5b1b-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5b1b-112">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="a5b1b-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5b1b-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5b1b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

