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
# <a name="quantumrom-function"></a>QuantumROM függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


A Quantum ROM technikát használja egy adott sűrűségű mátrix ábrázolására.

A $N $ együtthatók $ \ alpha_j $ értékének listája esetén ez egy egységes $U $ értéket ad vissza, amely a Quantum-ROM technikát használja a közelítési $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ megtisztítására a sűrűségi mátrix $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $. Ebben a közelítésben a $ \epsilon $ hiba olyan, hogy $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ és $ \| \tilde\rho-\rho \| \Le \epsilon $. Más szóval, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ s {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _j}.
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Bevitel

### <a name="targeterror--double"></a>targetError: [dupla](xref:microsoft.quantum.lang-ref.double)

A célként megadott hiba $ \epsilon $.


### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

$N $ együtthatók tömbje, amely meghatározza az alapul szolgáló állapotok valószínűségét.
A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a>Kimenet: (([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL)

## <a name="first-parameter"></a>Első paraméter

Az a `(x,(y,z))` rekord `x = y + z` , ahol a qubits teljes száma, a `y` qubits száma `LittleEndian` , valamint `z` a szemetet qubits száma.

## <a name="second-parameter"></a>Második paraméter

Az egyszabványú $ \ sum_j | \ alpha_j | $ az együttható tömbből.

## <a name="third-parameter"></a>Harmadik paraméter

Az egységes $U $.

## <a name="references"></a>Referencia

- Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662