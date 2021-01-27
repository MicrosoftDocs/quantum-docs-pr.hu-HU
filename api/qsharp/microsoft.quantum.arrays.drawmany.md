---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846207"
---
# <a name="drawmany-operation"></a>DrawMany művelet

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Megismétli a műveletet egy adott számú minta esetében, és a kimenetét egy tömbben gyűjti össze.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Bevitel

### <a name="op--tinput--toutput"></a>op: ' TInput => ' TOutput 

A művelet, amelyet többször kell meghívni.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

A gyűjtésre hívott minták száma `op` .


### <a name="input--tinput"></a>bemenet: ' TInput

Az átadandó bemenet `op` .



## <a name="output--toutput"></a>Kimenet: ' TOutput []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="example"></a>Példa

A következő minta egy egész számot adott meg egy olyan műveletből, amely egyszerre egyetlen bitet vesz fel.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)