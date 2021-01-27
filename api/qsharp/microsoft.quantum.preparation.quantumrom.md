---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856823"
---
# <a name="quantumrom-function"></a><span data-ttu-id="e94f9-102">QuantumROM függvény</span><span class="sxs-lookup"><span data-stu-id="e94f9-102">QuantumROM function</span></span>

<span data-ttu-id="e94f9-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e94f9-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e94f9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e94f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e94f9-105">A QuantumROM elavult.</span><span class="sxs-lookup"><span data-stu-id="e94f9-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="e94f9-106">Használja <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> helyette.</span><span class="sxs-lookup"><span data-stu-id="e94f9-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="e94f9-107">A Quantum ROM technikát használja egy adott sűrűségű mátrix ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="e94f9-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="e94f9-108">A $N $ együtthatók $ \ alpha_j $ értékének listája esetén ez egy egységes $U $ értéket ad vissza, amely a Quantum-ROM technikát használja a közelítési $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ megtisztítására a sűrűségi mátrix $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="e94f9-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="e94f9-109">Ebben a közelítésben a $ \epsilon $ hiba olyan, hogy $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ és $ \| \tilde\rho-\rho \| \Le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e94f9-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="e94f9-110">Más szóval, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ s {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _j}.</span><span class="sxs-lookup"><span data-stu-id="e94f9-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="e94f9-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e94f9-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="e94f9-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e94f9-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e94f9-113">targetError: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e94f9-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e94f9-114">A célként megadott hiba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e94f9-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="e94f9-115">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e94f9-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e94f9-116">$N $ együtthatók tömbje, amely meghatározza az alapul szolgáló állapotok valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="e94f9-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="e94f9-117">A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="e94f9-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="e94f9-118">Kimenet: (([int](xref:microsoft.quantum.lang-ref.int), int[,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="e94f9-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="e94f9-119">Első paraméter</span><span class="sxs-lookup"><span data-stu-id="e94f9-119">First parameter</span></span>

<span data-ttu-id="e94f9-120">Az a `(x,(y,z))` rekord `x = y + z` , ahol a qubits teljes száma, a `y` qubits száma `LittleEndian` , valamint `z` a szemetet qubits száma.</span><span class="sxs-lookup"><span data-stu-id="e94f9-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="e94f9-121">Második paraméter</span><span class="sxs-lookup"><span data-stu-id="e94f9-121">Second parameter</span></span>

<span data-ttu-id="e94f9-122">Az egyszabványú $ \ sum_j | \ alpha_j | $ az együttható tömbből.</span><span class="sxs-lookup"><span data-stu-id="e94f9-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="e94f9-123">Harmadik paraméter</span><span class="sxs-lookup"><span data-stu-id="e94f9-123">Third parameter</span></span>

<span data-ttu-id="e94f9-124">Az egységes $U $.</span><span class="sxs-lookup"><span data-stu-id="e94f9-124">The unitary $U$.</span></span>

## <a name="example"></a><span data-ttu-id="e94f9-125">Példa</span><span class="sxs-lookup"><span data-stu-id="e94f9-125">Example</span></span>

<span data-ttu-id="e94f9-126">A következő kódrészlet felkészíti a $3 $-qubit állapotot $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, ahol a $ \vec\alpha = (1.0, 2.0, 3.0, 4.0, 5.0) $ és a hiba `1e-3` ;</span><span class="sxs-lookup"><span data-stu-id="e94f9-126">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0,2.0,3.0,4.0,5.0)$, and the error is `1e-3`;</span></span>

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a><span data-ttu-id="e94f9-127">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="e94f9-127">References</span></span>

- <span data-ttu-id="e94f9-128">Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e94f9-128">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>