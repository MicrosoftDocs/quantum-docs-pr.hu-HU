---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841485"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="7acdc-102">ApplyToEachCA művelet</span><span class="sxs-lookup"><span data-stu-id="7acdc-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="7acdc-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7acdc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7acdc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7acdc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7acdc-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="7acdc-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="7acdc-106">A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="7acdc-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7acdc-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7acdc-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="7acdc-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="7acdc-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7acdc-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="7acdc-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7acdc-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="7acdc-110">register : 'T[]</span></span>

<span data-ttu-id="7acdc-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="7acdc-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7acdc-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7acdc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7acdc-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7acdc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7acdc-114">Nem</span><span class="sxs-lookup"><span data-stu-id="7acdc-114">'T</span></span>

<span data-ttu-id="7acdc-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="7acdc-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="7acdc-116">Példa</span><span class="sxs-lookup"><span data-stu-id="7acdc-116">Example</span></span>

<span data-ttu-id="7acdc-117">Készítse elő a három qubit $ \ket{+} $ állapotot:</span><span class="sxs-lookup"><span data-stu-id="7acdc-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="7acdc-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7acdc-118">See Also</span></span>

- [<span data-ttu-id="7acdc-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="7acdc-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)