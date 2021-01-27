---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 81abe75e2a315fe9a994147242f3c8c9bde586ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824720"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="656e0-102">SteaneCodeEncoderImpl művelet</span><span class="sxs-lookup"><span data-stu-id="656e0-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="656e0-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="656e0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="656e0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="656e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="656e0-105">A Steane-kód kódolójának és dekóderének megvalósításához használt magánhálózati művelet.</span><span class="sxs-lookup"><span data-stu-id="656e0-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="656e0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="656e0-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="656e0-107">adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="656e0-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="656e0-108">egy 1 qubit tartalmazó tömb, amely a bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="656e0-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="656e0-109">Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="656e0-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="656e0-110">egy 6 qubits rendelkező tömb, amely redundancia hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="656e0-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="656e0-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="656e0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

