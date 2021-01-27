---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851054"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A blokk kódolású tükröződést egy Quantum walkre konvertálja.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Leírás

Egy olyan `BlockEncodingReflection` egységes $U $ által képviselt, amely egyes operátorok $H $ kamatot kódol, egy Quantum walk $W $ értéket tartalmaz, amely a $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ spektrumát tartalmazza.

## <a name="input"></a>Bevitel

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Egy `BlockEncodingReflection` egységes $U $ értéket kell átalakítani a Quantum Walking szolgáltatásba.



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egy Quantum Walk $W $, amely a regisztereken közösen működik `a` `s` , és blokkolja a kódolást $H $, és tartalmazza a $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ spektrumát.

## <a name="references"></a>Hivatkozások

- Hamilton szimuláció a Qubitization Guang felfüggeszti Hao Low, Isaac L. a https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. szimulációs. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)