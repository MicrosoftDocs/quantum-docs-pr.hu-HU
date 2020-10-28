---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713907"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="e9b4a-102">OptimizedBEXY művelet</span><span class="sxs-lookup"><span data-stu-id="e9b4a-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="e9b4a-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e9b4a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e9b4a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9b4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9b4a-105">Egy egységes $U $, amely a Pauli-karakterláncot alkalmazza $ (X ^ {z + 1} \_ c: ^ {z} \_ p) z \_ {p-1}... Z_0 $ on qubits $0.. p $ feltétele egy index $z \in \{ 0, 1 \} $ és $p $.</span><span class="sxs-lookup"><span data-stu-id="e9b4a-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="e9b4a-106">Ez a $ $ \begin{align} U\ket {z} \ ket {p} \ ket {\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} c: # \_ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e9b4a-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e9b4a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e9b4a-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="e9b4a-108">pauliBasis: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e9b4a-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e9b4a-109">Ha ez a qubit a $ \ket $ állapotban van {0} , a rendszer a $X $ értéket alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="e9b4a-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="e9b4a-110">Ha a $ \ket $ állapotú {1} , $Y $ értéket alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e9b4a-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="e9b4a-111">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e9b4a-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e9b4a-112">A regisztrációhoz tartozó $ \ket{p} $ érték határozza meg azt a qubit, amelyen a $X $ vagy $Y $ értéket alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e9b4a-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="e9b4a-113">targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9b4a-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9b4a-114">Azon qubits regisztrálása, amelyeken a Pauli-operátorok vannak alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="e9b4a-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9b4a-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9b4a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e9b4a-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="e9b4a-116">References</span></span>

- <span data-ttu-id="e9b4a-117">Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e9b4a-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>