---
title: Lekéréses kérelmek megnyitása | Microsoft Docs
description: Lekéréses kérelmek megnyitása
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183726"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="6b27e-103">Lekéréses kérelmek megnyitása</span><span class="sxs-lookup"><span data-stu-id="6b27e-103">Opening Pull Requests</span></span> #

<span data-ttu-id="6b27e-104">A Quantum Development Kit dokumentációja a git verziókövetés rendszer használatával felügyelhető a GitHubon tárolt számos tárház használatával.</span><span class="sxs-lookup"><span data-stu-id="6b27e-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="6b27e-105">A git és a GitHub együttes használata megkönnyíti az együttműködését a Quantum Development Kit-ben.</span><span class="sxs-lookup"><span data-stu-id="6b27e-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="6b27e-106">A git-Tárházak például klónozottak vagy összeállíthatók, hogy teljesen független másolatot készítsenek az adott tárházról.</span><span class="sxs-lookup"><span data-stu-id="6b27e-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="6b27e-107">Ez lehetővé teszi az eszközökhöz való hozzájárulást és a kívánt tempóban történő munkát.</span><span class="sxs-lookup"><span data-stu-id="6b27e-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="6b27e-108">Ha elkészült, küldjön nekünk egy kérést, amely tartalmazza a hozzájárulását a repókban a GitHub _pull-kérés_ funkciójának használatával.</span><span class="sxs-lookup"><span data-stu-id="6b27e-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="6b27e-109">Az egyes lekéréses kérelmek lapja tartalmazza a hozzájárulással kapcsolatos összes módosítás részleteit, a hozzájárulással kapcsolatos megjegyzések listáját, valamint azon felülvizsgálati eszközöket, amelyeket a Közösség más tagjai használhatnak a visszajelzés és a tanácsadás megadására.</span><span class="sxs-lookup"><span data-stu-id="6b27e-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="6b27e-110">Habár a git teljes oktatóanyaga az útmutató hatókörén kívül esik, a következő hivatkozásokat ajánljuk további információforrásokra a git learningben:</span><span class="sxs-lookup"><span data-stu-id="6b27e-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="6b27e-111">[Ismerkedjen meg a git](https://www.atlassian.com/git)-val: a Atlassian git-oktatóanyagok készlete.</span><span class="sxs-lookup"><span data-stu-id="6b27e-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="6b27e-112">[Verziókövetés a Visual Studio Code-ban](https://code.visualstudio.com/docs/editor/versioncontrol): útmutató a Visual Studio Code használatához a git felületéhez.</span><span class="sxs-lookup"><span data-stu-id="6b27e-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="6b27e-113">[GitHub learning Lab](https://lab.github.com/): online tanfolyamok a git, a GitHub és a kapcsolódó technológiák használatához.</span><span class="sxs-lookup"><span data-stu-id="6b27e-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="6b27e-114">A [git megjelenítése](https://git-school.github.io/visualizing-git/): interaktív eszköz a git-parancsok egy adattár állapotának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6b27e-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="6b27e-115">[Verziókövetés a git-vel (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A tudományos számítástechnika felé irányuló git-oktatóanyag.</span><span class="sxs-lookup"><span data-stu-id="6b27e-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="6b27e-116">[Ismerkedjen meg a git-elágazással](https://learngitbranching.js.org/): az ágak interaktív készlete és a rejtvények átállítása az új git-funkciók megismeréséhez.</span><span class="sxs-lookup"><span data-stu-id="6b27e-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="6b27e-117">Mi az a lekéréses kérelem?</span><span class="sxs-lookup"><span data-stu-id="6b27e-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="6b27e-118">A fentiek elmondása esetén hasznos lehet néhány percet kipróbálni a **lekéréses kérelmekről**.</span><span class="sxs-lookup"><span data-stu-id="6b27e-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="6b27e-119">A git használatakor a módosítások _véglegesítve_ jelennek meg, amely leírja, hogyan kapcsolódnak ezek a változások a tárház állapotához a módosítások előtt.</span><span class="sxs-lookup"><span data-stu-id="6b27e-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="6b27e-120">Gyakran olyan diagramokat rajzolunk, amelyekben a véglegesíti a korábbi véglegesítés során felnyíló körökkel.</span><span class="sxs-lookup"><span data-stu-id="6b27e-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="6b27e-121">Tegyük fel, hogy egy `feature`nevű _ág_ egy hozzájárulását indította el.</span><span class="sxs-lookup"><span data-stu-id="6b27e-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="6b27e-122">A **Microsoft/Quantum** elágazása a következőhöz hasonló módon jelenhet meg:</span><span class="sxs-lookup"><span data-stu-id="6b27e-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="6b27e-123">Ha a változtatásokat a helyi tárházban végzi el, a változtatásokat egy másik adattárból is lekérheti, hogy felvegyen egy felfelé irányuló _változást._</span><span class="sxs-lookup"><span data-stu-id="6b27e-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="6b27e-124">A lekéréses kérelmek ugyanúgy működnek, de fordított sorrendben: Ha lekéréses kérelmet nyit meg, a felsőbb rétegbeli tárházat kéri a hozzájárulásának lekérésére.</span><span class="sxs-lookup"><span data-stu-id="6b27e-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="6b27e-125">Amikor megnyit egy lekéréses kérelmet a Tárházak egyikére, a GitHub lehetőséget nyújt a Közösség más tagjai számára, hogy megtekintsék a módosítások összegzését, a rájuk vonatkozó észrevételeket, valamint javaslatokat tesznek a még jobb hozzájárulás biztosításához.</span><span class="sxs-lookup"><span data-stu-id="6b27e-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="6b27e-126">Ezzel a folyamattal a GitHub funkcióinak használatával javíthatja a hozzájárulásokat, és kiváló minőségű terméket tarthat fenn a Quantum programozási Közösség számára.</span><span class="sxs-lookup"><span data-stu-id="6b27e-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="6b27e-127">Lekéréses kérelem készítése</span><span class="sxs-lookup"><span data-stu-id="6b27e-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="6b27e-128">A lekéréses kérelmeknek két fő módja van.</span><span class="sxs-lookup"><span data-stu-id="6b27e-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="6b27e-129">Az olyan kisebb módosítások esetén, amelyek csak egyetlen fájlt érintenek, a GitHub webes felülete lekéréses kérelem teljes online elvégzésére használható.</span><span class="sxs-lookup"><span data-stu-id="6b27e-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="6b27e-130">Bonyolultabb hozzájárulások esetén a helyi számítógép általában könnyebben használható a lekéréses kérelmek előkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6b27e-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="6b27e-131">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="6b27e-131">Next steps</span></span> ##

<span data-ttu-id="6b27e-132">Gratulálunk a git használatával, hogy segítse a Quantum Development Kit közösségét!</span><span class="sxs-lookup"><span data-stu-id="6b27e-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="6b27e-133">Ha többet szeretne megtudni a kód beszerzéséről, folytassa az alábbi útmutatóval.</span><span class="sxs-lookup"><span data-stu-id="6b27e-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b27e-134">Ismerje meg, Hogyan járulhat hozzá a kódokhoz</span><span class="sxs-lookup"><span data-stu-id="6b27e-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)