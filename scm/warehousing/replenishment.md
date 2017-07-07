---
title: "Feltöltés"
description: "A témakör ismerteti a Raktárkezelési funkciót használó raktárok számára elérhető feltöltési stratégiákat."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: c3bbf35b98416cbc3feca2b0d01015a79cdb2659
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="replenishment"></a>Feltöltés

[!include[banner](../includes/banner.md)]


A témakör ismerteti a Raktárkezelési funkciót használó raktárok számára elérhető feltöltési stratégiákat. Az adatok nem vonatkoznak a raktározási megoldásra, amely a Készletkezelés modulból érhető el. A következő feltöltési stratégiák állnak rendelkezésre:

-   **Hullámigény feltöltés** – Ez a stratégia feltöltési munkát hoz létre kimenő rendelésekhez vagy terhelésekhez, ha a készlet nem érhető el, amikor a munkát létrehozza a hullám. Ha például nem áll rendelkezésre egy értékesítési rendeléshez szükséges mennyiség a hullám feldolgozásakor, feltöltési munka hozható létre.
-   **Minimális vagy maximális feltöltés** – Ez a stratégia minimális és maximális készletezési korlátokat használ a helyek feltöltésének meghatározásához. A cikkek és helyek feltételei meghatározzák a feltöltéshez kiértékelt készletet. A minimális vagy maximális feltöltési sablonok a legfontosabbak megfelelő szintek megtartásához a a kitárolási helyeken. Annak biztosításához, hogy megfelelő mennyiségű kitárolási felület készlet legyen elérhető a hullámigénynek való megfeleléshez, használja kiegészítésként az igényfeltöltést a minimális és maximális feltöltési ciklusok között.
-   **Rakomány igényfeltöltése** – Ez a stratégia többféle rakomány iránti keresletet összegez, és feltöltési munkát hoz létre, mely a megfelelő kitárolási helyek feltöltéséhez szükséges. Ez a stratégia biztosítja, hogy a létrehozott rakományok kitárolhatók legyenek a raktári kibocsátásukat követően.

Mind három stratégia feltöltési sablon alapján hoz létre feltöltési munkát.

## <a name="wave-demand-replenishment"></a>Hullámigény feltöltése

Hullámigény feltöltés feltöltési munkát hoz létre termelési rendelésekhez, kanbanokhoz, kimenő rendelésekhez vagy rakományokhoz igény alapján, ha a készlet nem érhető el, amikor a munkát létrehozza a hullám. A feltöltési sablon a feltételekről, a mértékegységről, az igény növelési egységéről és a helyről tartalmaz adatokat. 

A helyutasítások segítségével meghatározhatja, mely helyeket kell feltölteni. A helyutasításokat hozzákapcsolhatja feltöltési sablonhoz a **Utasításkód** mező használatával. Ha a **Utasításkód** mező nincs beállítva, a lekérdezések segítségével meghatározható, hogy melyik helyutasítást kell használni. Ha az utasításkód nincs meghatározva a feltöltési sablonban és a helyutasításnak van utasításkódja, a helyutasítás figyelmen kívül lesz hagyva, még akkor is, ha a helyutasítás lekérdezése helyes. Kitárolási helyutasítás segítségével meghatározható a feltöltéshez szükséges készlet beszerzési helye. 

Sablon létrehozása mellett meg kell adnia bizonyos feltöltési beállításokat a hullámsablonon. A hullámsablon feltöltési hullámlépést kell tartalmazzon, ami csak akkor fut le, ha a cikkfelosztás nem sikeres. A feltöltési hullámlépés egy hullámlépéskód alapján határozza meg, melyik feltöltési sablont kell használni. Győződjön meg róla, hogy a feltöltés hullámlépése mellett **Feltöltés** van megadva a **Módszerek** szakaszban a hullámsablonon. 

A **Feltöltési sablon** oldal tartalmaz egy **Hullámigény engedélyezése a nem lefoglalt mennyiségek használatához** jelölőnégyzetet. Be kell jelölnie a jelölőnégyzetet, ha engedélyezni kívánja az igényfeltöltéseket a kiválasztott feltöltési sablonokból generált munkákból történő foglalatlan mennyiségek kivonásához. Ezt a jelölőnégyzetet jelölje be minden egyes meglévő feltöltési sablon esetén annak az engedélyezéséhez, hogy az igényfeltöltési sablonok használhassák ezt a logikát. Ha igényfeltöltés jelenik meg a raktárban, az levonja az igényt a foglalatlan mennyiségekkel rendelkező, meglévő feltöltési munkából, ha a munka a **Foglalatlan mennyiség használatához szükséges hullámigények engedélyezése** jelölőnégyzeten bejelölt feltöltési sablonból származik.


Az igényfeltöltés értékesítési rendelések, átmozgatási rendelések, termelési rendelések és kanbanok esetén támogatott. 

## <a name="minmax-replenishment"></a>Minimális vagy maximális feltöltés
Minimális/maximális feltöltés esetén a készletet úgy töltik fel, hogy a beállított minimális és maximális értékhatárok között legyen. Általában ez a folyamat naponta egyszer fut le, hogy biztosítsa, a kitárolás megkezdése előtt minden kitárolási hely maximálisan fel legyen töltve. 

A minimális és maximális összeg a feltöltési sablonban van meghatározva. A sablon számos egyéb beállítása hasonlít a Hullámigény feltöltése során használt sablonok beállításaira. A sablonnak tartalmaznia kell egy-egy sort minden egyes cikkhez és helyhez. Ha a kötegelt feldolgozással futtatja a feltöltést, a Finance and Operations megvizsgálja, hogy feltöltés szükséges-e abban a sorrendben, amelyben a sorok rendezve vannak. 

Fontos megjegyezni, hogy a minimális/maximális feltöltési stratégia nem tud üres helyet feltölteni, kivéve, ha a hely a cikkhez rögzített helyként van beállítva. Ha a hely, amit fel kell tölteni, nem rögzített hely, nem lehet megállapítani, melyik cikk feltöltése szükséges. Ezért legalább néhány aktuális készlet szükséges a feltöltés bekövetkezte előtt.

## <a name="load-demand-replenishment"></a>Rakomány igényfeltöltése
A Rakomány igényfeltöltése stratégia többféle rakomány iránti keresletet összegez, és feltöltési munkát hoz létre, mely a megfelelő kitárolási helyek feltöltéséhez szükséges. A Rakomány igényfeltöltése sok tekintetben hasonlít a Hullámigény feltöltéséhez. A legnagyobb eltérés a Rakomány igényfeltöltése és a Hullámigény feltöltése között a lefutás módja és ideje között figyelhető meg. Mint a Minimális vagy maximális feltöltés, a Rakomány igényfeltöltése is kötegelt feladat használatával fut. Az elszámolóár beállításához a **Rakomány igényfeltöltése** oldalon válassza ki a használni kívánt feltöltési sablont, állítson be szűrőlekérdezést a rakományigény meghatározásához. A helylekérdezés határozza meg a helyeket, amelyekből bármely rendelkezésre álló mennyiség levonásra kerül a rakományok összesített igényének való megfelelés teljesítéséhez.

## <a name="replenishment-prerequisites"></a>Feltöltés előfeltételei
| Előfeltételek            | Leírás                                                                                                                                                                                                                                        |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cikk                    | A cikknek elérhetőnek kell lennie a raktárkezelő folyamathoz.                                                                                                                                                                                       |
| Raktár               | A raktárnak elérhetőnek kell lennie a raktárkezelő folyamathoz. A raktárt a **Raktárak** oldalon a raktár kiválasztásával, majd a **Raktárkezelési folyamatok alkalmazása** lehetőség kijelölésével tudja a raktárkezelési folyamatokhoz elérhetővé tenni. |
| Feltöltési sablonok | Legalább az egyik feltöltési sablon esetén be kell állítani a Minimális vagy maximális feltöltést, Hullámigény feltöltését vagy a Rakomány igényfeltöltését.                                                                                                             |
| Helyek               | A tárolóhelyeket létre kell hozni és csatlakoztatni kell a helyprofilhoz.                                                                                                                                                                                     |
| Helyprofilok       | Tárolóhelyek létrehozásához helyprofilok meglétére van szükség.                                                                                                                                                                                       |
| Helyutasítások     | Helyutasítások szükségesek a munka olyan helyekre való irányításához, ahol feltöltés szükséges és ahol a készlet forrása van.                                                                                     |
| Munkasablonok          | Munkasablonok szükségesek a **Feltöltés** típusához, feltöltési munka létrehozásához, így a készlet a kívánt helyre mozgatható.                                                                                           |

