---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715292"
---
# <a name="trotterarbitraryimplca-operation"></a>TrotterArbitraryImplCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


A páros-Order Trotter – Suzuki integrátor rekurzív megvalósítása.

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a>Bevitel

### <a name="order--int"></a>megrendelés: [int](xref:microsoft.quantum.lang-ref.int)

Trotter-Suzuki integrátor sorrendje.


### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

A felbontani kívánt műveletek száma az idő lépésekben.


### <a name="op--intdoublet--unit-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Egy művelet, amely elfogad egy index bemenetet (típus `Int` ) és egy időbemenetet (típus) `Double` és egy kvantum-regisztrációt (típus `'T` ) a dekompozícióhoz.


### <a name="stepsize--double"></a>stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

Szorzó a szimuláció egyes lépéseinek méretéhez.


### <a name="target--t"></a>cél: nem

Az Operations műveletet elvégező kvantum-regisztráció.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a típus, amely az egyes időpontokban cselekszik; általában a `Qubit[]` vagy a `Qubit` .