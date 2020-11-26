---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202209"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="1d048-102">AssertQubitIsInStateWithinTolerance művelet</span><span class="sxs-lookup"><span data-stu-id="1d048-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="1d048-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1d048-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1d048-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1d048-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1d048-105">Azt állítja be, hogy a qubit a várt állapotú.</span><span class="sxs-lookup"><span data-stu-id="1d048-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="1d048-106">`expected` összetett vektort jelöl: $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="1d048-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="1d048-107">A $a $, $b $ értéket képviselő rekordok első eleme a komplex szám valódi része, míg a második a képzeletbeli rész.</span><span class="sxs-lookup"><span data-stu-id="1d048-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="1d048-108">Az utolsó argumentum meghatározza azt a tűréshatárt, amellyel az érvényesítés történik.</span><span class="sxs-lookup"><span data-stu-id="1d048-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="1d048-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1d048-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="1d048-110">várt: ([összetett](xref:Microsoft.Quantum.Math.Complex),[összetett](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="1d048-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="1d048-111">A várt összetett amplitúdók a $ \ket {0} $ és a $ \ket $ értéknél {1} .</span><span class="sxs-lookup"><span data-stu-id="1d048-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1d048-112">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1d048-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1d048-113">Az a Qubit, amelynek az állapotát érvényesíteni kell.</span><span class="sxs-lookup"><span data-stu-id="1d048-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="1d048-114">Vegye figyelembe, hogy ez a qubit feltételezhető, hogy elkülöníthető a többi lefoglalt qubits, és nincs összekeverve.</span><span class="sxs-lookup"><span data-stu-id="1d048-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1d048-115">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1d048-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1d048-116">Az adalékanyag tűréshatára, amellyel a tényleges amplitúdók eltérhetnek a várttól.</span><span class="sxs-lookup"><span data-stu-id="1d048-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="1d048-117">Részletekért lásd az alábbi megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="1d048-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d048-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d048-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1d048-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1d048-119">Remarks</span></span>

<span data-ttu-id="1d048-120">A következő Mathematica-kód segítségével ellenőrizheti a mi, MX, My, MZ kifejezéseket:</span><span class="sxs-lookup"><span data-stu-id="1d048-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="1d048-121">A tolerancia a $L \_ {\infty} $ távolság a 3 dimenziós valós vektor között (x ₂, x ₃, x ₄) a $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ és a Real Vector (y ₂, y ₃, y ₄) által meghatározott ρ = Y ₁ I + y ₂ x + y ₃ Y + y ₄ Z, ahol a ρ a regiszter állapotának megfelelő sűrűségi mátrix.</span><span class="sxs-lookup"><span data-stu-id="1d048-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="1d048-122">Ez csak abban az esetben igaz, ha a TR (ρ) és a TR (| ψ ⟩ ⟨ ψ |) mindkettő 1 (például x ₁ = 1/2, y ₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="1d048-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="1d048-123">Ha ez nem így van, a függvény azt állítja be, hogy az l ∞ távolság (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) és (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) értéke kisebb, mint a tolerancia paraméter.</span><span class="sxs-lookup"><span data-stu-id="1d048-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>