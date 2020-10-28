---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Rx-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723501"
---
# <a name="rx-operation"></a><span data-ttu-id="38b35-102">Rx-művelet</span><span class="sxs-lookup"><span data-stu-id="38b35-102">Rx operation</span></span>

<span data-ttu-id="38b35-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="38b35-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="38b35-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38b35-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38b35-105">A $x $ tengelyre vonatkozó rotációt alkalmaz egy adott szög alapján.</span><span class="sxs-lookup"><span data-stu-id="38b35-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="38b35-106">\begin{align} R_x (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="38b35-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="38b35-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="38b35-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="38b35-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="38b35-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="38b35-109">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38b35-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38b35-110">Az a szög, amely alapján a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="38b35-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="38b35-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="38b35-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="38b35-112">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="38b35-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38b35-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38b35-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="38b35-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="38b35-114">Remarks</span></span>

<span data-ttu-id="38b35-115">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="38b35-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```