---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712185"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="3f3ac-102">SteaneCodeEncoderImpl művelet</span><span class="sxs-lookup"><span data-stu-id="3f3ac-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="3f3ac-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3f3ac-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3f3ac-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f3ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f3ac-105">A Steane-kód kódolójának és dekóderének megvalósításához használt magánhálózati művelet.</span><span class="sxs-lookup"><span data-stu-id="3f3ac-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f3ac-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3f3ac-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="3f3ac-107">adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f3ac-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f3ac-108">egy 1 qubit tartalmazó tömb, amely a bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="3f3ac-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="3f3ac-109">Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f3ac-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f3ac-110">egy 6 qubits rendelkező tömb, amely redundancia hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="3f3ac-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f3ac-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f3ac-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

