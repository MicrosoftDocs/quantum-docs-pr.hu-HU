---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714872"
---
# <a name="hterm-user-defined-type"></a>HTerm-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag [](https://nuget.org/packages/)


A C# és a Q # között átadott adatok formátuma, amely a Hamilton kifejezését jelöli.
A megjelenített adatmennyiség jelentését az azt fogadó algoritmus határozza meg.

```qsharp

newtype HTerm = (Int[], Double[]);
```

