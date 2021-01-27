---
uid: Microsoft.Quantum.ErrorCorrection.Syndrome
title: A szindrómát felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Syndrome
qsharp.summary: Type for measurement results `Result[]` that specify an error syndrome of a quantum code.
ms.openlocfilehash: fa73da3190946af7784f3bd80cee6cbf6e8e8462
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824688"
---
# <a name="syndrome-user-defined-type"></a>A szindrómát felhasználó által definiált típus

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Olyan mérési eredmények típusának `Result[]` megadása, amelyek kvantum-kód hibát okozó szindrómát határoznak meg.

```qsharp

newtype Syndrome = (Result[]);
```

