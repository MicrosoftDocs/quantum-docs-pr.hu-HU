---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840498"
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

## <a name="example"></a>Példa

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```