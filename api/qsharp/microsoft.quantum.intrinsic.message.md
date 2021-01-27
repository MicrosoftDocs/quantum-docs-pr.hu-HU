---
uid: Microsoft.Quantum.Intrinsic.Message
title: Üzenet függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849373"
---
# <a name="message-function"></a><span data-ttu-id="cdc29-102">Üzenet függvény</span><span class="sxs-lookup"><span data-stu-id="cdc29-102">Message function</span></span>

<span data-ttu-id="cdc29-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cdc29-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cdc29-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cdc29-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cdc29-105">Egy üzenet naplózása.</span><span class="sxs-lookup"><span data-stu-id="cdc29-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cdc29-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cdc29-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="cdc29-107">msg: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cdc29-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cdc29-108">A jelentendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="cdc29-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdc29-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdc29-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cdc29-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cdc29-110">Remarks</span></span>

<span data-ttu-id="cdc29-111">A függvény konkrét viselkedése a szimulátortól függ, de a legtöbb esetben a rendszer a megadott üzenetet fogja írni a konzolra.</span><span class="sxs-lookup"><span data-stu-id="cdc29-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>