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
# <a name="optimizedbexy-operation"></a>OptimizedBEXY művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag [](https://nuget.org/packages/)


Egy egységes $U $, amely a Pauli-karakterláncot alkalmazza $ (X ^ {z + 1} \_ c: ^ {z} \_ p) z \_ {p-1}... Z_0 $ on qubits $0.. p $ feltétele egy index $z \in \{ 0, 1 \} $ és $p $. Ez a $ $ \begin{align} U\ket {z} \ ket {p} \ ket {\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} c: # \_ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="paulibasis--qubit"></a>pauliBasis: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Ha ez a qubit a $ \ket $ állapotban van {0} , a rendszer a $X $ értéket alkalmazza. Ha a $ \ket $ állapotú {1} , $Y $ értéket alkalmazza a rendszer.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A regisztrációhoz tartozó $ \ket{p} $ érték határozza meg azt a qubit, amelyen a $X $ vagy $Y $ értéket alkalmazza a rendszer.


### <a name="targetregister--qubit"></a>targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Azon qubits regisztrálása, amelyeken a Pauli-operátorok vannak alkalmazva.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662