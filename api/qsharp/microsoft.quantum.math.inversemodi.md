---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723640"
---
# <a name="inversemodi-function"></a>InverseModI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


$B $ értéket ad vissza, amely $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Az invertált szám


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

Az a modulus, amely szerint a számok invertálva vannak



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egész $b $, például $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.