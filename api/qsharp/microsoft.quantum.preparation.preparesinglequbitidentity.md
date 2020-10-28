---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724886"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


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