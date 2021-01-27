---
title: Fejlesztés Q#-pal és Binderrel
description: Megtudhatja, hogyan hozhat létre Q#-alkalmazást a Binder használatával.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856712"
---
# <a name="develop-with-no-locq-and-binder"></a>Fejlesztés Q#-pal és Binderrel

A Jupyter-notebookok online futtatásához és megosztásához használhatja a Bindert.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>A Binder használata a Microsoft QDK-mintákkal

A Binder konfigurálása a Microsoft QDK-minták automatikus használatához:

1. Nyissa meg a böngészőt, és futtassa a következőt: https://aka.ms/try-qsharp.
1. A **Quantum Development Kit-minták** kezdőlapján kattintson a **Q#-notebookra**, hogy megtudhassa, hogyan írhat saját kvantumalkalmazás-notebookot az IQ# használatával.

![A QDK kezdőlapja](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>A Binder használata saját notebookjaival és adattáraival

Ha már rendelkezik notebookokkal egy GitHub-adattárban, a Bindert saját adattárának használatára is konfigurálhatja:

1. Ellenőrizze, hogy van-e *Dockerfile* nevű fájl az adattár gyökerében. A fájlnak legalább az alábbi sorokat kell tartalmaznia:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > Az IQ# aktuális verzióját a [kibocsátási megjegyzésekben](xref:microsoft.quantum.relnotes) ellenőrizheti.

    A Docker-fájlok létrehozásával kapcsolatos további információért tekintse meg a [Docker-fájlra vonatkozó referenciákat](https://docs.docker.com/engine/reference/builder/).

2. Nyissa meg valamilyen böngészőben a [mybinder.org](https://mybinder.org) webhelyet.
3. Adja meg az adattár nevét a **GitHub URL-címeként** (például *SajátNév/SajátAdattár*), majd kattintson az **Indítás** elemre.

![A MyBinder űrlapja](~/media/mybinder.png)
    
## <a name="next-steps"></a>Következő lépések

Most, hogy beállította a Binder-környezetet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
