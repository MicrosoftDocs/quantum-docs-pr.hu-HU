---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842927"
---
# <a name="squaresi-operation"></a>SquareSI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Négyzetes aláírású egész szám `xs` , és a eredményét tárolja `result` , amelynek kezdetben nullának kell lennie.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="xs--signedlittleendian"></a>xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n bites egész szám – négyzet (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>eredmény: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

a 2n-bit result (SignedLittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A megvalósítás a IntegerSquare-ra támaszkodik.