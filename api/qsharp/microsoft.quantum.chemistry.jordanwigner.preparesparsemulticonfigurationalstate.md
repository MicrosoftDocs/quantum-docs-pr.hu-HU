---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: PrepareSparseMultiConfigurationalState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713850"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="37e21-102">PrepareSparseMultiConfigurationalState művelet</span><span class="sxs-lookup"><span data-stu-id="37e21-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="37e21-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="37e21-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="37e21-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37e21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37e21-105">Ritka, többkonfigurációs állapot előkészítése próbaverziós állapothoz a kezdeti próbaverziós állapotba való felizgatás hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="37e21-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="37e21-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37e21-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="37e21-107">initialStatePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37e21-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="37e21-108">A kezdeti próbaverziós állapot előkészítésének egységesje.</span><span class="sxs-lookup"><span data-stu-id="37e21-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="37e21-109">izgalom: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="37e21-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="37e21-110">A gerjesztő a gerjesztés és a qubit indexek által képviselt kezdeti próbaverziós állapot izgatása.</span><span class="sxs-lookup"><span data-stu-id="37e21-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="37e21-111">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="37e21-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="37e21-112">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="37e21-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37e21-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37e21-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

