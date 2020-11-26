---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214381"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="b6a1c-102">ExpandedCoefficients függvény</span><span class="sxs-lookup"><span data-stu-id="b6a1c-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="b6a1c-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="b6a1c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="b6a1c-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b6a1c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b6a1c-105">Kibővíti a Jordan-Wigner-együtthatók kompakt megjelenítését, hogy egy-az-egyhez hozzárendelést szerezzen be ezek és a Pauli-kifejezések között.</span><span class="sxs-lookup"><span data-stu-id="b6a1c-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="b6a1c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b6a1c-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="b6a1c-107">coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b6a1c-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b6a1c-108">Együtthatók tömbje, ahogy az Jordan-Wigner Hamilton adatstruktúrából olvasva.</span><span class="sxs-lookup"><span data-stu-id="b6a1c-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="b6a1c-109">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6a1c-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6a1c-110">A Jordan-Wigner kifejezés típusa.</span><span class="sxs-lookup"><span data-stu-id="b6a1c-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="b6a1c-111">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b6a1c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b6a1c-112">Az együtthatók kibontott tömbje, egy Pauli-kifejezéssel.</span><span class="sxs-lookup"><span data-stu-id="b6a1c-112">Expanded arrays of coefficients, one per Pauli term.</span></span>