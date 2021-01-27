---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 2b38be5c196d81635daa8b478f6e727fdf378c62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850240"
---
# <a name="selectz-operation"></a><span data-ttu-id="927eb-102">SelectZ művelet</span><span class="sxs-lookup"><span data-stu-id="927eb-102">SelectZ operation</span></span>

<span data-ttu-id="927eb-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="927eb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="927eb-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="927eb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="927eb-105">Egy egységes $U $, amely a Pauli $Z $ Gate-t alkalmazza egy qubits, $p $ \ket{p} $ index állapotú.</span><span class="sxs-lookup"><span data-stu-id="927eb-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="927eb-106">Ez a $ $ \begin{align} U\ket {p} \ ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="927eb-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="927eb-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="927eb-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="927eb-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="927eb-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="927eb-109">A regisztrációhoz tartozó $ \ket{p} $ érték határozza meg azt a qubit, amelyen a $Z $ értéket alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="927eb-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="927eb-110">targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="927eb-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="927eb-111">Azon qubits regisztrálása, amelyeken a Pauli-operátorok vannak alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="927eb-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="927eb-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="927eb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

