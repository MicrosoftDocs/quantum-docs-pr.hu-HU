---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718457"
---
# <a name="applyand-operation"></a>ApplyAnd művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


A megadott qubit csak akkor áll le, ha mindkét vezérlő qubits 1 állapotban van, a adjoint művelet végrehajtásához használja a mérést.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Leírás

`target`A csak akkor áll le, ha mindkét vezérlő 1, de feltételezi, hogy `target` a 0 állapotban van.  A műveletnek T-Count 4, T-depth 2, és nem igényel segítő qubit, és ezért előnyös lehet egy CCNOT művelethez, ha `target` az ismert értéke 0.  A művelet adjoint a mérésen alapul, és nem igényel T-kapukat.

A művelet vezérelt alkalmazásához nem szükséges a segítő qubit, a `2^c` `Rz` Gates és a nem állítható mélységre, ahol `c` a a művelethez tartozó két vezérlőelemet tartalmazó általános qubits száma `ApplyAnd` .  A adjoint által vezérelt alkalmazáshoz `2^c - 1` `Rz` kapuk szükségesek (a nem adjoint művelet méretének kétszerese), a segítő qubit nem, és nincs mélységre optimalizálva.

## <a name="input"></a>Bevitel

### <a name="control1--qubit"></a>control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Első vezérlő qubit


### <a name="control2--qubit"></a>2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Második vezérlő qubit


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Cél kiegészítő qubit; a kötelező állapot 0



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- Cody Jones: "új konstrukciók a hibatűrő Toffoli kapuhoz", leltár. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328
- Craig Gidney: "a kvantum-Hozzáadás díja", Quantum 2, oldal 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) Doi: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "Quantum Oracle-áramkörök és a karácsonyfa mintája", [blog december 19., 2019](https://msoeken.github.io/blog_qac.html) (Megjegyzés: a több vezérelt szerkezet ismertetése)