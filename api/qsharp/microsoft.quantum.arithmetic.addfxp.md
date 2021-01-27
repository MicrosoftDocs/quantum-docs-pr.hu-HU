---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843857"
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