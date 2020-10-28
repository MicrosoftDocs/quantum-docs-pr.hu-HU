---
uid: Microsoft.Quantum.Intrinsic.Message
title: Üzenet függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711428"
---
# <a name="message-function"></a><span data-ttu-id="2e86f-102">Üzenet függvény</span><span class="sxs-lookup"><span data-stu-id="2e86f-102">Message function</span></span>

<span data-ttu-id="2e86f-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2e86f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2e86f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e86f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e86f-105">Egy üzenet naplózása.</span><span class="sxs-lookup"><span data-stu-id="2e86f-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2e86f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2e86f-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="2e86f-107">msg: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2e86f-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2e86f-108">A jelentendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="2e86f-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e86f-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e86f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2e86f-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2e86f-110">Remarks</span></span>

<span data-ttu-id="2e86f-111">A függvény konkrét viselkedése a szimulátortól függ, de a legtöbb esetben a rendszer a megadott üzenetet fogja írni a konzolra.</span><span class="sxs-lookup"><span data-stu-id="2e86f-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>