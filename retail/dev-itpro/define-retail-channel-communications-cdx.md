---
title: "Kiskereskedelmi csatorna kommunikációinak meghatározása (a Commerce Data Exchange)"
description: "Ez a cikk a Commerce Data Exchange-ről és annak összetevőiről nyújt áttekintést. Bemutatja, hogy az a része, amely minden egyes összetevő Microsoft Dynamics 365 műveletekhez és kiskereskedelmi csatornák között adatok továbbításának játszik."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
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

Ez a cikk a Commerce Data Exchange-ről és annak összetevőiről nyújt áttekintést. Bemutatja, hogy az a része, amely minden egyes összetevő Microsoft Dynamics 365 műveletekhez és kiskereskedelmi csatornák között adatok továbbításának játszik.

<a name="overview"></a>Áttekintés
--------

Commerce Data Exchange rendszer Dynamics 365 műveletekhez és az online áruházak vagy tégla és habarcs üzletek kiskereskedelmi csatornák közötti adatátvitelt. Az adatbázis, amely tárolja az adatokat a kiskereskedelmi csatorna elkülönül a Dynamics 365 adatbázis műveletek számára. A csatorna-adatbázis csak kiskereskedelmi tranzakciók esetében szükséges adatokat tartalmazza. Törzsadatok Dynamics 365 műveletekhez konfigurált és csatornák számára. Tranzakciós adatok a pont (POS) értékesítési rendszer jön létre, vagy az online tárolja, és ezután feltölthetők a Dynamics 365 műveletekhez. Az adatelosztás aszinkron. Ez azt jelenti, hogy a forrásnál az adatok összegyűjtése és csomagolása külön működik a célhelyen történő adatok átvételi és alkalmazási folyamatától. Bizonyos esetekben, mint az ár és készlet keresése, az adatokat valós időben kell beolvasni. Ezek a forgatókönyvek támogatására, Commerce Data Exchange Dynamics 365 műveletekhez és a csatorna közötti valós idejű kommunikációt lehetővé tevő szolgáltatás is tartalmaz. 

[![frissített kiskereskedelmi-kép](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async szolgáltatás
A Dynamics 365 műveletek adatbázis a Microsoft SQL Server változáskövetés kell küldeni a csatornák adatmódosítások meghatározására szolgál. Elosztási ütemezés alapján, Dynamics 365 műveletek csomagok az adatokat, és központi tárolására (Azure blob-tároló) menti. Egy külön kötegfolyamat használja a Commerce Data Exchange: Async Client rendszer könyvtárát, hogy beszúrja ezt az adatcsomagot a csatorna adatbázisába. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Kiskereskedelmi tervezés és ütemezés

Az ütemező feladatok a helyek közti adatelosztás mechanizmusát alkotják. A feladatok alfeladatokból álnak, amik meghatározzák a kiosztásra kerülő adatok tábláit és tábla mezőit. 365 Dynamics műveletekhez előre definiált ütemezési feladatok és részfeladatok, amelyek megfelelnek a legtöbb szervezet replikációs tartalmazza. Az alábbi típusú meghatározott feladatok vannak létrehozva:

-   **Töltse le a feladatok** – letöltési feladatok megváltozott Dynamics 365 műveletek csatorna adatbázisok adatokat küldik. A rekordok módosításai az SQL Server szolgáltatáson keresztül vannak követve.
-   **Feltöltési feladatot (P-feladatok)** – feltöltési feladatokat húzza a csatorna a Dynamics 365 műveletek adatbázis értékesítési tranzakciók. A P-feladatok fokozatosan töltik fel az adatot. A P-feladat futása közben az Async Client tár ellenőrzi a viszonválasz-számlálót azon rekordok esetében, amelyek már korábban is beérkeztek egy megadott helyről. A rekord csak abban az esetben kerül feltöltésre, ha a viszonválasz-számláló értéke nagyobb, mint a legnagyobb talált érték. A P-feladatok nem frissít olyan adatot, ami már korább feltöltésre került.

Az elosztási ütemezés segítségével futtassa az adatátvitel kézzel vagy egy kötegelt műveletek Dynamics 365 ütemezésével. Az elosztási ütemezés egy vagy több csatorna adatcsoportját, valamint egy vagy több ütemező feladatot tartalmazhat.

## <a name="realtime-service"></a>Valós idejű szolgáltatás
Commerce Data Exchange: Real-time Service egy beépített szolgáltatás, amely Dynamics 365 műveletekhez és kiskereskedelmi csatornák közötti valós idejű kommunikációt biztosít. Valós idejű szolgáltatás lehetővé teszi a számítógépek POS és konkrét adatok lekérése Dynamics 365 műveletek valós idejű online áruházak. Bár a legtöbb kulcsfontosságú művelet végrehajtható a helyi csatorna adatbázisban, a következő esetekben Dynamics 365 műveletek tárolt adatok közvetlen hozzáférést igényelnek a:

-   Ajándékkártyák kibocsátása és beváltása.
-   Hűségpontok beváltása.
-   Jóváírások kibocsátása és beváltása.
-   Vevőrekordok létrehozása vagy frissítése.
-   Értékesítési rendelések létrehozása, frissítése és befejezése.
-   Készlet átvétele beszerzési rendelés vagy átmozgatási rendelés ellenében.
-   Készletszámolás végrehajtása.
-   Értékesítési tranzakciók beolvasása üzletek között, valamint visszáru-tranzakciókra teljesítése.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Egy előre definiált Real-time Service profil jön létre.


