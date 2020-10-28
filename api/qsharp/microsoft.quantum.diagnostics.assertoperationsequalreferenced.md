---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712955"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="2eb60-102">AssertOperationsEqualReferenced művelet</span><span class="sxs-lookup"><span data-stu-id="2eb60-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="2eb60-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2eb60-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2eb60-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2eb60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2eb60-105">A két művelet miatt a azt állítja, hogy az összes bemeneti állapot esetében azonos módon működnek.</span><span class="sxs-lookup"><span data-stu-id="2eb60-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="2eb60-106">Ez az állítás a Choi – Jamiołkowski isomorphism használatával valósítható meg, hogy csökkentse az állítást az egyik qubit-állapotra vonatkozóan két kusza regisztrációnál.</span><span class="sxs-lookup"><span data-stu-id="2eb60-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="2eb60-107">Ezért ennek a műveletnek csak egyetlen hívással kell rendelkeznie minden tesztelt művelethez, de kétszer annyi qubits kell lefoglalni.</span><span class="sxs-lookup"><span data-stu-id="2eb60-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="2eb60-108">Ezzel az állítással biztosítható például, hogy egy adott művelet optimalizált verziója azonos módon viselkedik a naiv megvalósításával, vagy egy olyan művelet, amely egy tartományon kívüli adatbevitelt hajt végre, ismert esetekkel egyetért.</span><span class="sxs-lookup"><span data-stu-id="2eb60-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="2eb60-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2eb60-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2eb60-110">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2eb60-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2eb60-111">Az egyes műveleteknek átadandó qubits száma.</span><span class="sxs-lookup"><span data-stu-id="2eb60-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="2eb60-112">tényleges: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2eb60-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2eb60-113">A vizsgálandó művelet.</span><span class="sxs-lookup"><span data-stu-id="2eb60-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="2eb60-114">várt: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="2eb60-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2eb60-115">A teszt alatt a művelet várt viselkedését meghatározó művelet.</span><span class="sxs-lookup"><span data-stu-id="2eb60-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2eb60-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2eb60-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2eb60-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2eb60-117">Remarks</span></span>

<span data-ttu-id="2eb60-118">Ehhez a művelethez az szükséges, hogy a művelet modellezése a várt viselkedést adjointable, így az inverz csak a cél-regisztráción végezhető el.</span><span class="sxs-lookup"><span data-stu-id="2eb60-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="2eb60-119">Az egyik megadhat egy áttelepítési műveletet, amely ellazítja ezt a követelményt, de az áttelepítési művelet nem általánosan elérhető a tetszőleges kvantum-műveletek esetében, így nem vehető igénybe.</span><span class="sxs-lookup"><span data-stu-id="2eb60-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>