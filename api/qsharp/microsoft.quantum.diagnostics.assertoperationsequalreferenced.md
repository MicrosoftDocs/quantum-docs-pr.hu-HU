---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712955"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


A két művelet miatt a azt állítja, hogy az összes bemeneti állapot esetében azonos módon működnek.

Ez az állítás a Choi – Jamiołkowski isomorphism használatával valósítható meg, hogy csökkentse az állítást az egyik qubit-állapotra vonatkozóan két kusza regisztrációnál.
Ezért ennek a műveletnek csak egyetlen hívással kell rendelkeznie minden tesztelt művelethez, de kétszer annyi qubits kell lefoglalni.
Ezzel az állítással biztosítható például, hogy egy adott művelet optimalizált verziója azonos módon viselkedik a naiv megvalósításával, vagy egy olyan művelet, amely egy tartományon kívüli adatbevitelt hajt végre, ismert esetekkel egyetért.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes műveleteknek átadandó qubits száma.


### <a name="actual--qubit--unit"></a>tényleges: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

A vizsgálandó művelet.


### <a name="expected--qubit--unit-adj"></a>várt: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

A teszt alatt a művelet várt viselkedését meghatározó művelet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ehhez a művelethez az szükséges, hogy a művelet modellezése a várt viselkedést adjointable, így az inverz csak a cél-regisztráción végezhető el.
Az egyik megadhat egy áttelepítési műveletet, amely ellazítja ezt a követelményt, de az áttelepítési művelet nem általánosan elérhető a tetszőleges kvantum-műveletek esetében, így nem vehető igénybe.