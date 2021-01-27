---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843027"
---
# <a name="multiplyi-operation"></a>MultiplyI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Az egész számot szorozza egész számmal `xs` `ys` , és tárolja az eredményt a értékben `result` , amelyeknek kezdetben nullának kell lennie.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bites multiplicand (LittleEndian)


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

$n $-bit szorzó (LittleEndian)


### <a name="result--littleendian"></a>eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

a $2n $-bit result (LittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A standard eltolási és hozzáadási megközelítést használ a szorzás megvalósításához.
Az ellenőrzött verzió javította $x _i $ másolását egy Ancilla-qubit a vezérlő qubits, majd a Ancilla-qubit hozzáadásának szabályozásával.