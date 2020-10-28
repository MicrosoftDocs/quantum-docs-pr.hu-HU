---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723193"
---
# <a name="bitsizei-function"></a>BitSizeI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


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