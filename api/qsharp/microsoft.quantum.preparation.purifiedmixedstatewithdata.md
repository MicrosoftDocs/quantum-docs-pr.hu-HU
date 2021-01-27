---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854284"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="f63be-102">PurifiedMixedStateWithData függvény</span><span class="sxs-lookup"><span data-stu-id="f63be-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="f63be-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f63be-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f63be-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f63be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f63be-105">Egy olyan műveletet ad vissza, amely egy adott kevert állapot megtisztítását készíti elő, amely egy adott adatgyűjteményt jelképező regiszterrel van összekeverve.</span><span class="sxs-lookup"><span data-stu-id="f63be-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="f63be-106">A "tisztított kevert állapot az adatmennyiséggel" kifejezés az űrlap Σi √ PI | i ⟩ | XI ⟩ | garbagei ⟩, ahol minden XI egy bitstring-kódolással kapcsolatos további, a regisztrációhoz | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="f63be-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="f63be-107">További vitát a következő témakörben talál: https://arxiv.org/pdf/1805.03662.pdf?page=15 .</span><span class="sxs-lookup"><span data-stu-id="f63be-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="f63be-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="f63be-108">Description</span></span>

<span data-ttu-id="f63be-109">A Quantum ROM technikáját használja egy adott sűrűségű mátrix ábrázolására, amely állapot-előkészítési műveletként visszaküldi azt.</span><span class="sxs-lookup"><span data-stu-id="f63be-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="f63be-110">Különösen a $N $ együtthatók $ \ alpha_j $, valamint az _egyes együtthatókkal társított $ \vec{x} j $ bitstring. Ez a függvény egy olyan műveletet ad vissza, amely a Quantum ROM technikát használja a közelítés előkészítéséhez $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ of the Mixed State $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, ahol minden egyes $p _j $ az adott együtthatóra való közelítés $ \ alpha_j $, például $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ minden $j $-hoz.</span><span class="sxs-lookup"><span data-stu-id="f63be-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="f63be-111">Ha átadott egy index-regisztrációt és egy, a szemetet qubits tartalmazó regisztert, amely kezdetben a $ \ket {0} \ket{00\cdots 0} állapotban van, a visszaadott művelet előkészíti mindkét regisztrációt a $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}, \end{align} $ $ értékre, amely a szemét-regisztráció alaphelyzetbe állítása és felszabadítása előtt a kívánt előkészítést a $ \epsilon $ értékre állítja be.</span><span class="sxs-lookup"><span data-stu-id="f63be-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="f63be-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f63be-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="f63be-113">targetError: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f63be-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f63be-114">A célként megadott hiba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="f63be-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="f63be-115">együtthatók: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="f63be-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="f63be-116">$N $ együtthatók tömbje, amely az egyes együtthatókkal társított bitstring $ \vec{x} _j $-t határozza meg.</span><span class="sxs-lookup"><span data-stu-id="f63be-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="f63be-117">A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="f63be-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="f63be-118">Kimenet: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="f63be-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="f63be-119">Egy művelet, amely a $ \tilde \rho $-t előkészíti a közös indexre és a szemét-regisztrációra.</span><span class="sxs-lookup"><span data-stu-id="f63be-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="f63be-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f63be-120">Remarks</span></span>

<span data-ttu-id="f63be-121">Az ehhez a művelethez megadott együtthatók az 1 normát követően normalizálva vannak, így az együtthatók mindig az érvényes kategorikus valószínűségi eloszlás leírásának tekintendők.</span><span class="sxs-lookup"><span data-stu-id="f63be-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="f63be-122">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="f63be-122">References</span></span>

- <span data-ttu-id="f63be-123">Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="f63be-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="f63be-124">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f63be-124">See Also</span></span>

- [<span data-ttu-id="f63be-125">Microsoft. Quantum. előkészítés. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="f63be-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)