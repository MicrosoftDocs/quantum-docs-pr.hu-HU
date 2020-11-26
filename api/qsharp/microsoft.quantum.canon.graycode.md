---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206884"
---
# <a name="graycode-function"></a>GrayCode függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Szürke kódú sorozatot hoz létre

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Bevitel

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Bitek száma



## <a name="output--intint"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

A rekordok tömbje. A rekord első értékének értéke a rekordban a GrayCode Sequence második értéke, amely a jelenlegi értékben a következőre változik.