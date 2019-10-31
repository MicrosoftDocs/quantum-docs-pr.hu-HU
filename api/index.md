---
uid: microsoft.quantum.standardlibsintro
title: Szabványos Q#-kódtár a Microsoft Quantumhoz
description: A Microsoft Quantumhoz készült szabványos Q#-kódtár referenciaanyagai
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999085"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="905cb-103">Szabványos Q#-kódtárak</span><span class="sxs-lookup"><span data-stu-id="905cb-103">Q# standard libraries</span></span> #

<span data-ttu-id="905cb-104">A Q#-t számos olyan hasznos művelet, függvény és felhasználó által definiált típus támogatja, amelyek együttesen a Q# *szabványos kódtárát* alkotják.</span><span class="sxs-lookup"><span data-stu-id="905cb-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="905cb-105">A szabványos Q#-kódtár két fő részre oszlik:</span><span class="sxs-lookup"><span data-stu-id="905cb-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="905cb-106">**A bevezetés**: a célszámítógép és a fordító részeként meghatározott műveletek és függvények, jellemzően a klasszikus natív .NET-kódban.</span><span class="sxs-lookup"><span data-stu-id="905cb-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="905cb-107">Általánosságban elmondható, hogy a különböző célszámítógépek a bevezetés különböző implementációit alkalmazzák az egyes rendszereknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="905cb-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="905cb-108">**A kánon**: a Q#-ban definiált műveletek és függvények, amelyek a bevezetésben meghatározott logikára épülnek.</span><span class="sxs-lookup"><span data-stu-id="905cb-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="905cb-109">A kánon implementálása a célszámítógépektől függetlenül mindig ugyanúgy zajlik.</span><span class="sxs-lookup"><span data-stu-id="905cb-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="905cb-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="905cb-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>