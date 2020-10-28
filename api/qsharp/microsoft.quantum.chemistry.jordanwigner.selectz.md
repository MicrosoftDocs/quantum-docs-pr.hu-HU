---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713794"
---
# <a name="selectz-operation"></a><span data-ttu-id="a5f16-102">SelectZ művelet</span><span class="sxs-lookup"><span data-stu-id="a5f16-102">SelectZ operation</span></span>

<span data-ttu-id="a5f16-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a5f16-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a5f16-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5f16-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5f16-105">Egy egységes $U $, amely a Pauli $Z $ Gate-t alkalmazza egy qubits, $p $ \ket{p} $ index állapotú.</span><span class="sxs-lookup"><span data-stu-id="a5f16-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="a5f16-106">Ez a $ $ \begin{align} U\ket {p} \ ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a5f16-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a5f16-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a5f16-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="a5f16-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a5f16-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a5f16-109">A regisztrációhoz tartozó $ \ket{p} $ érték határozza meg azt a qubit, amelyen a $Z $ értéket alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a5f16-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="a5f16-110">targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5f16-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5f16-111">Azon qubits regisztrálása, amelyeken a Pauli-operátorok vannak alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="a5f16-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5f16-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5f16-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

