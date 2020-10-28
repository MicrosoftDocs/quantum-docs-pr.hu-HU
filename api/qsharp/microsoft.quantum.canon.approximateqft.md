---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716776"
---
# <a name="approximateqft-operation"></a>ApproximateQFT művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Alkalmazza a becsült kvantum Fourier-transzformációt (AQFT) a kvantum-regiszterre.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
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

## <a name="references"></a>Referencia

- [*M. Roetteler, th. Beth* , kiegyenlített. algebra ENG. communis. Számítógépf. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: Quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)