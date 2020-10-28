---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712520"
---
# <a name="applybitflipencoder-operation"></a>ApplyBitFlipEncoder művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


A bit flip Encoder és a dekóder megvalósításához használt magánhálózati művelet.

Vegye figyelembe, hogy ez a kódoló a helyi konzisztens helyreállítást is képes használni, ebben az esetben a kezdeti állapotában leírt hibát fogja okozni `auxQubits` .
Különösen, ha `auxQubits` kezdetben a $ \ket $ állapotban vannak {10} , ez $X _1 $ hibát okoz a kódolt qubit.

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="coherentrecovery--bool"></a>coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- Doi: 10.1103/PhysRevA. 85.044302