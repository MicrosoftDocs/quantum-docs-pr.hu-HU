---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725502"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="d0cd8-102">MCMTMask-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="d0cd8-102">MCMTMask user defined type</span></span>

<span data-ttu-id="d0cd8-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d0cd8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d0cd8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0cd8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0cd8-105">A többszörös vezérlésű, több célt szolgáló Toffoli kaput jelölő típus.</span><span class="sxs-lookup"><span data-stu-id="d0cd8-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="d0cd8-106">Az első egész szám egy bit-maszk a vezérlők soraihoz.</span><span class="sxs-lookup"><span data-stu-id="d0cd8-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="d0cd8-107">A beállított bites indexek megfelelnek a vezérlő sorok indexének.</span><span class="sxs-lookup"><span data-stu-id="d0cd8-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="d0cd8-108">A második egész szám egy bit-maszk a célként megadott sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="d0cd8-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="d0cd8-109">A beállított, a célként megadott sorok indexeit tartalmazó bites indexek.</span><span class="sxs-lookup"><span data-stu-id="d0cd8-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="d0cd8-110">Mindkét egész számhoz tartozó bites indexeket különállónak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d0cd8-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="d0cd8-111">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="d0cd8-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="d0cd8-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0cd8-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="d0cd8-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0cd8-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

