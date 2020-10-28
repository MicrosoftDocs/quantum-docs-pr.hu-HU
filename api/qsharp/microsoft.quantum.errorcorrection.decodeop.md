---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712409"
---
# <a name="decodeop-user-defined-type"></a>DecodeOp-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Egy olyan műveletet jelöl, amely kódolja a kódolt regisztrációt egy fizikai regiszterbe, valamint a tünetegyüttes rögzítéséhez használt qubits.

Egy DecodeOp argumentuma megegyezik egy EncodeOp való visszatéréssel, és fordítva.

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

