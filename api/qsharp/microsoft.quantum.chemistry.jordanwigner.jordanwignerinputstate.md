---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 81993a7449098c03639cf090fb36ed39c6ba17c0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214687"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A C# és a Q # között átadott adatok formátuma, amely a kezdeti állapot előkészítését jelöli, az azt fogadó algoritmus határozza meg.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

