---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847255"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>Hivatkozások

- Hamilton szimuláció a Qubitization Guang felfüggeszti Hao Low, Isaac L. a https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. szimulációs. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)