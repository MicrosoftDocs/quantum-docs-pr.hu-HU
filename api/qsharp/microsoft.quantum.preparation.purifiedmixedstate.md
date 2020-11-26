---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230021"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="fbf59-102">PurifiedMixedState függvény</span><span class="sxs-lookup"><span data-stu-id="fbf59-102">PurifiedMixedState function</span></span>

<span data-ttu-id="fbf59-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="fbf59-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="fbf59-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbf59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbf59-105">Egy olyan műveletet ad vissza, amely egy adott kevert állapot tisztítását készíti elő.</span><span class="sxs-lookup"><span data-stu-id="fbf59-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="fbf59-106">A "tisztított kevert állapot" kifejezés a következő űrlap állapotára hivatkozik: | ψ ⟩ = Σi √ PI | i ⟩ | garbagei ⟩ által meghatározott együtthatók vektora {PI}.</span><span class="sxs-lookup"><span data-stu-id="fbf59-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="fbf59-107">Az űrlap állapotait vegyes állapotokra lehet csökkenteni, ρ ≔ PI | i ⟩ ⟨ i | a "Garbage" regiszter (azaz a számítási alapon átlós, kevert állapot) alapján történő nyomkövetéssel.</span><span class="sxs-lookup"><span data-stu-id="fbf59-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="fbf59-108">További vitát a következő témakörben talál: https://arxiv.org/pdf/1805.03662.pdf?page=15 .</span><span class="sxs-lookup"><span data-stu-id="fbf59-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="fbf59-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="fbf59-109">Description</span></span>

<span data-ttu-id="fbf59-110">A Quantum ROM technikáját használja egy adott sűrűségű mátrix ábrázolására, amely állapot-előkészítési műveletként visszaküldi azt.</span><span class="sxs-lookup"><span data-stu-id="fbf59-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="fbf59-111">Különösen, ha a $N $ együtthatós $ \ alpha_j $ értéket adta meg, ez a függvény egy olyan műveletet ad vissza, amely a Quantum ROM-technikát használja a közelítés előkészítéséhez $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ vegyes állapotú $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, ahol minden egyes $p _j $ az adott együtthatóra való közelítés $ \ alpha_j $, például $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ minden $j $-hoz.</span><span class="sxs-lookup"><span data-stu-id="fbf59-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="fbf59-112">Ha átadott egy index-regisztrációt és egy, a szemetet qubits tartalmazó regisztert, amely kezdetben a $ \ket {0} \ket{00\cdots 0} állapotban van, a visszaadott művelet előkészíti mindkét regisztrációt a $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $ értékre, amely a szemét-regisztráció alaphelyzetbe állítása és felszabadítása előtt a kívánt előkészítést a \epsilon $ értékre állítja be.</span><span class="sxs-lookup"><span data-stu-id="fbf59-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="fbf59-113">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fbf59-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="fbf59-114">targetError: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fbf59-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fbf59-115">A célként megadott hiba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="fbf59-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="fbf59-116">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fbf59-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fbf59-117">$N $ együtthatók tömbje, amely meghatározza az alapul szolgáló állapotok valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="fbf59-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="fbf59-118">A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="fbf59-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="fbf59-119">Kimenet: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="fbf59-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="fbf59-120">Egy művelet, amely a $ \tilde \rho $-t előkészíti a közös indexre és a szemét-regisztrációra.</span><span class="sxs-lookup"><span data-stu-id="fbf59-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="fbf59-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fbf59-121">Remarks</span></span>

<span data-ttu-id="fbf59-122">Az ehhez a művelethez megadott együtthatók az 1 normát követően normalizálva vannak, így az együtthatók mindig az érvényes kategorikus valószínűségi eloszlás leírásának tekintendők.</span><span class="sxs-lookup"><span data-stu-id="fbf59-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="fbf59-123">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fbf59-123">References</span></span>

- <span data-ttu-id="fbf59-124">Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="fbf59-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf59-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fbf59-125">See Also</span></span>

- [<span data-ttu-id="fbf59-126">Microsoft. Quantum. előkészítés. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="fbf59-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)