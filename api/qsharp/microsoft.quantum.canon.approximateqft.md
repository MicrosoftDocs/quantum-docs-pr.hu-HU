---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850324"
---
# <a name="approximateqft-operation"></a>ApproximateQFT művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Alkalmazza a becsült kvantum Fourier-transzformációt (AQFT) a kvantum-regiszterre.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

a közelítési paraméter, amely meghatározza, hogy az QFT áramkörben lévő vezérelt Z-Forgások milyen szinten vannak metszve.

Az a közelítő paraméter meghatározza a Z-Forgások (∈: {0.. n}) és az összes Z-forgás (2π/2k) metszési szintjét, ahol a k>a QFT-áramkörből el lett távolítva. Ismert, hogy a k >= log ₂ (n) + log ₂ (1/ε) + 3 lehet kötve | | QFT – AQFT | |<ε.


### <a name="qs--bigendian"></a>QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

az n qubits kvantum-regisztrálása, amelyhez a rendszer a megközelítőleges kvantum Fourier-transzformációt alkalmazza.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A AQFT a 2π/2k és a Hadamard Gates formátumú Z-rotációs kapukat igényli.

A bemenet és a kimenet a big endian kódolásban való kódolásra van feltételezve.

## <a name="references"></a>Hivatkozások

- [*M. Roetteler, th. Beth*, kiegyenlített. algebra ENG. communis. Számítógépf. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: Quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)