---
title: Lekéréses kérelmek megnyitása
description: Megtudhatja, hogyan küldhet el egy GitHub-lekéréses kérelmet, ha készen áll a kód vagy a dokumentáció Microsoft Quantum Development Kithoz való hozzájárulására.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274845"
---
# <a name="opening-pull-requests"></a>Lekéréses kérelmek megnyitása #

A Quantum Development Kit dokumentációja a git verziókövetés rendszer használatával felügyelhető a GitHubon tárolt számos tárház használatával.
A git és a GitHub együttes használata megkönnyíti az együttműködését a Quantum Development Kit-ben.
A git-Tárházak például klónozottak vagy összeállíthatók, hogy teljesen független másolatot készítsenek az adott tárházról.
Ez lehetővé teszi az eszközökhöz való hozzájárulást és a kívánt tempóban történő munkát.

Ha elkészült, küldjön nekünk egy kérést, amely tartalmazza a hozzájárulását a repókban a GitHub _pull-kérés_ funkciójának használatával.
Az egyes lekéréses kérelmek lapja tartalmazza a hozzájárulással kapcsolatos összes módosítás részleteit, a hozzájárulással kapcsolatos megjegyzések listáját, valamint azon felülvizsgálati eszközöket, amelyeket a Közösség más tagjai használhatnak a visszajelzés és a tanácsadás megadására.

> [!NOTE]
> Habár a git teljes oktatóanyaga az útmutató hatókörén kívül esik, a következő hivatkozásokat ajánljuk további információforrásokra a git learningben:
>
> - [Ismerkedjen meg a git](https://www.atlassian.com/git)-val: a Atlassian git-oktatóanyagok készlete.
> - [Verziókövetés a Visual Studio Code-ban](https://code.visualstudio.com/docs/editor/versioncontrol): útmutató a Visual Studio Code használatához a git felületéhez.
> - [GitHub learning Lab](https://lab.github.com/): online tanfolyamok a git, a GitHub és a kapcsolódó technológiák használatához.
> - A [git megjelenítése](https://git-school.github.io/visualizing-git/): interaktív eszköz a git-parancsok egy adattár állapotának megjelenítéséhez.
> - [Verziókövetés a git-vel (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A tudományos számítástechnika felé irányuló git-oktatóanyag.
> - [Ismerkedjen meg a git-elágazással](https://learngitbranching.js.org/): az ágak interaktív készlete és a rejtvények átállítása az új git-funkciók megismeréséhez.

## <a name="what-is-a-pull-request"></a>Mi az a lekéréses kérelem? ##

A fentiek elmondása esetén hasznos lehet néhány percet kipróbálni a **lekéréses kérelmekről**.
A git használatakor a módosítások _véglegesítve_ jelennek meg, amely leírja, hogyan kapcsolódnak ezek a változások a tárház állapotához a módosítások előtt.
Gyakran olyan diagramokat rajzolunk, amelyekben a véglegesíti a korábbi véglegesítés során felnyíló körökkel.

Tegyük fel, hogy elindított egy hozzájárulást egy nevű _ágban_ `feature` .
A **Microsoft/Quantum** elágazása a következőhöz hasonló módon jelenhet meg:

![Egy működő ág a GitHubban](~/media/git-workflow-step0.png)

Ha a változtatásokat a helyi tárházban végzi el, a változtatásokat egy másik adattárból is lekérheti, hogy felvegyen egy felfelé irányuló _változást._

![A felsőbb rétegbeli tárház változásainak húzása és egyesítése](~/media/git-workflow-step1.png)

A lekéréses kérelmek ugyanúgy működnek, de fordított sorrendben: Ha lekéréses kérelmet nyit meg, a felsőbb rétegbeli tárházat kéri a hozzájárulásának lekérésére.

![A módosítások visszahívásának kérése az eredeti tárházba](~/media/git-workflow-step2.png)

Amikor megnyit egy lekéréses kérelmet a Tárházak egyikére, a GitHub lehetőséget nyújt a Közösség más tagjai számára, hogy megtekintsék a módosítások összegzését, a rájuk vonatkozó észrevételeket, valamint javaslatokat tesznek a még jobb hozzájárulás biztosításához.

![Képernyőkép egy lekéréses kérelemről a GitHubon](~/media/pull-request-header.png)

Ezzel a folyamattal a GitHub funkcióinak használatával javíthatja a hozzájárulásokat, és kiváló minőségű terméket tarthat fenn a Quantum programozási Közösség számára.

## <a name="how-to-make-a-pull-request"></a>Lekéréses kérelem készítése ##

A lekéréses kérelmeknek két fő módja van.  
Az olyan kisebb módosítások esetén, amelyek csak egyetlen fájlt érintenek, a GitHub webes felülete lekéréses kérelem teljes online elvégzésére használható. Egyszerűen navigáljon a szerkeszteni kívánt fájlhoz, és használja a szerkesztési ikont.  
Bonyolultabb hozzájárulások esetén a rendszer leggyakrabban megkönnyíti a tárház klónozását a helyi számítógépre, hogy először előkészítse a lekéréses kérelmeket.

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

## <a name="next-steps"></a>További lépések ##

Gratulálunk a git használatával, hogy segítse a Quantum Development Kit közösségét!
Ha többet szeretne megtudni a kód beszerzéséről, folytassa az alábbi útmutatóval.

> [!div class="nextstepaction"]
> [Ismerje meg, Hogyan járulhat hozzá a kódokhoz](xref:microsoft.quantum.contributing.code)
