---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855374"
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

