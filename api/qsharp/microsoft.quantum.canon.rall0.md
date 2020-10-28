---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715629"
---
# <a name="rall0-operation"></a><span data-ttu-id="a91a6-102">RAll0 művelet</span><span class="sxs-lookup"><span data-stu-id="a91a6-102">RAll0 operation</span></span>

<span data-ttu-id="a91a6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a91a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a91a6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a91a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a91a6-105">Fázis-eltolási műveletet hajt végre.</span><span class="sxs-lookup"><span data-stu-id="a91a6-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="a91a6-106">$R = \boldone-(1-e ^ {i \phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="a91a6-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a91a6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a91a6-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="a91a6-108">fázis: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a91a6-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a91a6-109">A $ \phi $ fázis a $ \ket{0\cdots 0} állapotra vonatkozik, \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="a91a6-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a91a6-110">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a91a6-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a91a6-111">A regisztráció, amelynek állapotát el kell forgatni $R $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="a91a6-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a91a6-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a91a6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a91a6-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a91a6-113">See Also</span></span>

- [<span data-ttu-id="a91a6-114">Microsoft. Quantum. Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="a91a6-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)