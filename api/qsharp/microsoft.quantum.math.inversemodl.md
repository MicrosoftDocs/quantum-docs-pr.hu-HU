---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723627"
---
# <a name="inversemodl-function"></a>InverseModL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


$B $ értéket ad vissza, amely $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Bevitel

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az invertált szám


### <a name="modulus--bigint"></a>modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az a modulus, amely szerint a számok invertálva vannak



## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Egész $b $, például $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.