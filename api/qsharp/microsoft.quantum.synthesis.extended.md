---
uid: Microsoft.Quantum.Synthesis.Extended
title: Kiterjesztett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855473"
---
# <a name="extended-function"></a>Kiterjesztett függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kibővíti a spektrumot fordított együtthatókkal

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="spectrum--int"></a>spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]

Spektrális együtthatók



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Együtthatók, amelyeket fordított másolat követ

## <a name="example"></a>Példa

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```