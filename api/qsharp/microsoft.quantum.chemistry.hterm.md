---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851792"
---
# <a name="hterm-user-defined-type"></a>HTerm-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A C# és a Q # között átadott adatok formátuma, amely a Hamilton kifejezését jelöli.
A megjelenített adatmennyiség jelentését az azt fogadó algoritmus határozza meg.

```qsharp

newtype HTerm = (Int[], Double[]);
```

