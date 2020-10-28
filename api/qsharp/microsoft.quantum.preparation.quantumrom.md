---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722955"
---
# <a name="quantumrom-function"></a><span data-ttu-id="72915-102">QuantumROM függvény</span><span class="sxs-lookup"><span data-stu-id="72915-102">QuantumROM function</span></span>

<span data-ttu-id="72915-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="72915-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="72915-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72915-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72915-105">A Quantum ROM technikát használja egy adott sűrűségű mátrix ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="72915-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="72915-106">A $N $ együtthatók $ \ alpha_j $ értékének listája esetén ez egy egységes $U $ értéket ad vissza, amely a Quantum-ROM technikát használja a közelítési $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ megtisztítására a sűrűségi mátrix $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="72915-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="72915-107">Ebben a közelítésben a $ \epsilon $ hiba olyan, hogy $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ és $ \| \tilde\rho-\rho \| \Le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="72915-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="72915-108">Más szóval, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ s {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _j}.</span><span class="sxs-lookup"><span data-stu-id="72915-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="72915-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="72915-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="72915-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="72915-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="72915-111">targetError: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72915-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72915-112">A célként megadott hiba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="72915-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="72915-113">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="72915-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="72915-114">$N $ együtthatók tömbje, amely meghatározza az alapul szolgáló állapotok valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="72915-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="72915-115">A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="72915-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="72915-116">Kimenet: (([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="72915-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="72915-117">Első paraméter</span><span class="sxs-lookup"><span data-stu-id="72915-117">First parameter</span></span>

<span data-ttu-id="72915-118">Az a `(x,(y,z))` rekord `x = y + z` , ahol a qubits teljes száma, a `y` qubits száma `LittleEndian` , valamint `z` a szemetet qubits száma.</span><span class="sxs-lookup"><span data-stu-id="72915-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="72915-119">Második paraméter</span><span class="sxs-lookup"><span data-stu-id="72915-119">Second parameter</span></span>

<span data-ttu-id="72915-120">Az egyszabványú $ \ sum_j | \ alpha_j | $ az együttható tömbből.</span><span class="sxs-lookup"><span data-stu-id="72915-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="72915-121">Harmadik paraméter</span><span class="sxs-lookup"><span data-stu-id="72915-121">Third parameter</span></span>

<span data-ttu-id="72915-122">Az egységes $U $.</span><span class="sxs-lookup"><span data-stu-id="72915-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="72915-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="72915-123">References</span></span>

- <span data-ttu-id="72915-124">Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="72915-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>