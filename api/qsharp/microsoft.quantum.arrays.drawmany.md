---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209995"
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



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)