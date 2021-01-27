---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Ry művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b50225b67701c6b17475445d5ed54400240e0b69
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818285"
---
# <a name="ry-operation"></a><span data-ttu-id="441a3-102">Ry művelet</span><span class="sxs-lookup"><span data-stu-id="441a3-102">Ry operation</span></span>

<span data-ttu-id="441a3-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="441a3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="441a3-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="441a3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="441a3-105">A $y $ tengelyre vonatkozó rotációt alkalmaz egy adott szög alapján.</span><span class="sxs-lookup"><span data-stu-id="441a3-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="441a3-106">\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="441a3-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="441a3-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="441a3-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="441a3-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="441a3-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="441a3-109">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="441a3-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="441a3-110">Az a szög, amely alapján a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="441a3-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="441a3-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="441a3-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="441a3-112">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="441a3-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="441a3-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="441a3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="441a3-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="441a3-114">Remarks</span></span>

<span data-ttu-id="441a3-115">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="441a3-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```