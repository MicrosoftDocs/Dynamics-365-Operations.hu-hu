---
title: "Kiskereskedelmi csatorna kommunikációinak meghatározása (a Commerce Data Exchange)"
description: "Ez a cikk a Commerce Data Exchange-ről és annak összetevőiről nyújt áttekintést. Bemutatja, hogy az egyes összetevők a Microsoft Dynamics 365 for Operations és a kiskereskedelmi csatornák közti adatátvitel mely részében vesznek részt."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Kiskereskedelmi csatorna kommunikációinak meghatározása (a Commerce Data Exchange)

[!include[banner](../includes/banner.md)]


Ez a cikk a Commerce Data Exchange-ről és annak összetevőiről nyújt áttekintést. Bemutatja, hogy az egyes összetevők a Microsoft Dynamics 365 for Operations és a kiskereskedelmi csatornák közti adatátvitel mely részében vesznek részt.

<a name="overview"></a>Áttekintés
--------

A Commerce Data Exchange olyan rendszer, amely átviszi az adatokat a Microsoft Dynamics 365 for Operations és a kiskereskedelmi csatornák között, például online áruházak és a fizikai üzletek között. Az adatbázis, ami a kiskereskedelmi csatorna adatait tárolja más, mint a Microsoft Dynamics 365 for Operations adatbázisa. A csatorna-adatbázis csak kiskereskedelmi tranzakciók esetében szükséges adatokat tartalmazza. Az alapadat a Microsoft Dynamics 365 for Operations programban van beállítva, és innen van kiosztva a csatornák számára. A tranzakciós adatok a pénztári (POS) rendszerben, vagy az online áruházban vannak létrehozva, ezután kerülnek feltöltésre a Dynamics 365 for Operations rendszerbe. Az adatelosztás aszinkron. Ez azt jelenti, hogy a forrásnál az adatok összegyűjtése és csomagolása külön működik a célhelyen történő adatok átvételi és alkalmazási folyamatától. Bizonyos esetekben, mint az ár és készlet keresése, az adatokat valós időben kell beolvasni. Ilyen esetekre a Commerce Data Exchange olyan szolgáltatással rendelkezik, ami lehetővé teszi a valós idejű kommunikációt a Dynamics 365 for Operations és a csatorna között. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async szolgáltatás
A Microsoft SQL Server változáskövetése a Dynamics 365 for Operations adatbázisában meghatározza azokat az adatváltozásokat, amiket el kell küldeni a csatornának. Az elosztási ütemezés alapján a Dynamics 365 for Operations csomagolja azokat az adatokat, és menti központi tárolóba (Azure blob tároló). Egy külön kötegfolyamat használja a Commerce Data Exchange: Async Client rendszer könyvtárát, hogy beszúrja ezt az adatcsomagot a csatorna adatbázisába. 

[![Async szolgáltatás](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Kiskereskedelmi tervezés és ütemezés

Az ütemező feladatok a helyek közti adatelosztás mechanizmusát alkotják. A feladatok alfeladatokból álnak, amik meghatározzák a kiosztásra kerülő adatok tábláit és tábla mezőit. A Dynamics 365 for Operations programban megtalálhatóak az előre meghatározott ütemező feladatok és részfeladatok, amelyek megfelelnek a legtöbb szervezet viszonválasz követelményeinek. Az alábbi típusú meghatározott feladatok vannak létrehozva:

-   **Feladatok letöltése** – Letölti a feladatokat és elküldi a megváltozott adatokat a Dynamics 365 for Operations programból a csatorna adatbázisába. A rekordok módosításai az SQL Server szolgáltatáson keresztül vannak követve.
-   **Feladatok feltöltése (P-feladatok)** – Feltölti a feladatok értékesítési tranzakcióit egy csatornából a Dynamics 365 for Operations adatbázisába. A P-feladatok fokozatosan töltik fel az adatot. A P-feladat futása közben az Async Client tár ellenőrzi a viszonválasz-számlálót azon rekordok esetében, amelyek már korábban is beérkeztek egy megadott helyről. A rekord csak abban az esetben kerül feltöltésre, ha a viszonválasz-számláló értéke nagyobb, mint a legnagyobb talált érték. A P-feladatok nem frissít olyan adatot, ami már korább feltöltésre került.

Az elosztási ütemezés futtatja az adatátvitelt, vagy kézzel, vagy a Microsoft Dynamics 365 for Operations rendszerben beütemezett kötegfeladattal. Az elosztási ütemezés egy vagy több csatorna adatcsoportját, valamint egy vagy több ütemező feladatot tartalmazhat.

## <a name="realtime-service"></a>Real-time Service
Commerce Data Exchange: a Real-time Service egy beépített szolgáltatás, amely valós idejű kommunikációt valósít meg a Dynamics 365 for Operations és a kiskereskedelmi csatornák között. A Real-time Service lehetővé teszi, hogy az egyes POS pénztár számítógépei és az online áruházak meghatározott adatot olvashassanak be valós időben a Dynamics 365 for Operations programból. Annak ellenére, hogy a legtöbb kulcsművelet elvégezhető a helyi csatorna adatbázisában, az alábbi esetek megkövetelik a közvetlen hozzáférést a Dynamics 365 for Operationsben tárolt adatokhoz:

-   Ajándékkártyák kibocsátása és beváltása.
-   Hűségpontok beváltása.
-   Jóváírások kibocsátása és beváltása.
-   Vevőrekordok létrehozása vagy frissítése.
-   Értékesítési rendelések létrehozása, frissítése és befejezése.
-   Készlet átvétele beszerzési rendelés vagy átmozgatási rendelés ellenében.
-   Készletszámolás végrehajtása.
-   Értékesítési tranzakciók beolvasása üzletek között, valamint visszáru-tranzakciókra teljesítése.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Létrejön egy előre meghatározott Real-time Service-profil.




