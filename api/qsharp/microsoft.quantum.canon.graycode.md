---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716161"
---
# <a name="graycode-function"></a>GrayCode függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Szürke kódú sorozatot hoz létre

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Bevitel

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Bitek száma



## <a name="output--intint"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

A rekordok tömbje. A rekord első értékének értéke a rekordban a GrayCode Sequence második értéke, amely a jelenlegi értékben a következőre változik.