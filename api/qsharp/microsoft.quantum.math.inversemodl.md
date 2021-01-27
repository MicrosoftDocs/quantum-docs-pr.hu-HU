---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851389"
---
# <a name="inversemodl-function"></a>InverseModL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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