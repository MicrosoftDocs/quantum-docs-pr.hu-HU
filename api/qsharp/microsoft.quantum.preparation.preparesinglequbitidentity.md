---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856870"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubit előkészítése a maximálisan kevert állapotban.

Előkészíti a megadott qubit a $ \boldone/$2 állapotban a depolarizációs csatorna $ $ \begin{align} \Omega (\rho) \mathrel{alkalmazásával: =} \frac {1} {4} \ sum_ {\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $, ahol a $ \sigma \_ i $ a $i $ th Pauli operátor, ahol a $ \rho $ egy vegyes állapotot jelölő sűrűségű operátor.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Egy qubit, amelynek állapotát a fent leírt módon kell leállítani.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A vegyes állapotú $ \boldone/$2 azt írja le, hogy a művelet egy adott állapotra való alkalmazásának eredményét implicit módon mutatja-e be a műveletben végrehajtott véletlenszerű választási lehetőség.
Így egyetlen alkalmazás esetében a művelet leképezi a tiszta állapotokat a tiszta állapotokra, de a várt módon működik.
Ez a művelet a Process tomográfia szolgáltatásban használható a csatorna *nem egységes* összetevőinek mérésére.