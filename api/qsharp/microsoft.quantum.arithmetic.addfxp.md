---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191040"
---
# <a name="addfxp-operation"></a>AddFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Két, a kvantum-regiszterekben tárolt, rögzített ponttal rendelkező számot adja meg.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

A $ \ket{f_1} $ és a $ \ket{f_2} $ értékben megadott két rögzített pontos regiszter esetében a $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $ műveletet hajtja végre.

## <a name="input"></a>Bevitel

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Első rögzített pont száma


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

A rendszer frissíti a második rögzített pont számát, hogy tartalmazza a két bemenet összegét.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A jelenlegi megvalósításhoz a két rögzített pontból származó számnak azonos ponttal kell rendelkeznie, mint a legkevésbé jelentős, azaz $n _i $ és a $p _i $ értéknek egyenlőnek kell lennie.