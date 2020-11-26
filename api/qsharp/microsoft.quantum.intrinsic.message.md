---
uid: Microsoft.Quantum.Intrinsic.Message
title: Üzenet függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199012"
---
# <a name="message-function"></a><span data-ttu-id="a25f8-102">Üzenet függvény</span><span class="sxs-lookup"><span data-stu-id="a25f8-102">Message function</span></span>

<span data-ttu-id="a25f8-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a25f8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a25f8-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a25f8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a25f8-105">Egy üzenet naplózása.</span><span class="sxs-lookup"><span data-stu-id="a25f8-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a25f8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a25f8-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="a25f8-107">msg: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a25f8-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a25f8-108">A jelentendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="a25f8-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a25f8-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a25f8-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a25f8-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a25f8-110">Remarks</span></span>

<span data-ttu-id="a25f8-111">A függvény konkrét viselkedése a szimulátortól függ, de a legtöbb esetben a rendszer a megadott üzenetet fogja írni a konzolra.</span><span class="sxs-lookup"><span data-stu-id="a25f8-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>