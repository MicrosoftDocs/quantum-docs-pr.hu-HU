---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203017"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A többszörös vezérlésű, több célt szolgáló Toffoli kaput jelölő típus.

Az első egész szám egy bit-maszk a vezérlők soraihoz.  A beállított bites indexek megfelelnek a vezérlő sorok indexének.

A második egész szám egy bit-maszk a célként megadott sorokhoz.  A beállított, a célként megadott sorok indexeit tartalmazó bites indexek.

Mindkét egész számhoz tartozó bites indexeket különállónak kell lennie.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="controlmask--int"></a>ControlMask: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [int](xref:microsoft.quantum.lang-ref.int)

