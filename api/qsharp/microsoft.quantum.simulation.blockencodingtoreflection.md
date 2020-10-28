---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722072"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Az a- `BlockEncoding` t megfelelőre konvertálja `BLockEncodingReflection` .

Ez olyan `BlockEncoding` egységes $U $-t kap, amely egyes operátorok $H $ kamatot kódol, $U "$-re konvertálja `BlockEncodingReflection` , amely ugyanazt a kezelőt kódolja, de a $U" ^ \Dagger = U "$-t is kielégíti.
Ez növeli a $U $ kiegészítő regisztrációjának méretét egy qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Bevitel

### <a name="blockencoding--blockencoding"></a>blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

Egy `BlockEncoding` egységes $U $, amely átalakítható reflexióba.



## <a name="output--blockencodingreflection"></a>Kimenet: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Egy egységes $U ' $, amely közösen működik a regisztereken `a` `s` , és blokkolja a $H $ kódolást, és megfelel a (z) "^ \Dagger = U" $ $U.

## <a name="remarks"></a>Megjegyzések

Ez növeli a $U $ kiegészítő regisztrációjának méretét egy qubit.

## <a name="references"></a>Referencia

- Hamilton szimuláció a Qubitization Guang felfüggeszti Hao Low, Isaac L. a https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. szimulációs. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)