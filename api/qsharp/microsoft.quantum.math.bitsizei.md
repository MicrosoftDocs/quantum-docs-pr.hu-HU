---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195851"
---
# <a name="bitsizei-function"></a>BitSizeI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A nem negatív egész szám esetén `a` a a jelölőhöz szükséges bitek számát adja vissza `a` .

Vagyis a legkisebb $n $ értéket adja vissza, amely $a < 2 ^ n $.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Az egész szám, amelynek a méretét ki kell számítani.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A kis méret `a` .