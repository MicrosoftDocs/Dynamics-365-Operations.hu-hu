---
title: "A Munkaerő-kezelés áttekintése"
description: "Ez a témakör leírja, hogyan használhatja a munkaerő kezelése (WFM) szolgáltatást az ismerős pénztári (POS) ügyfelek, a modern pénztár és a felhőpénztár előnyeinek kihasználására úgy, hogy az üzletvezetők egyszerűen kezelhessék a munkaerőt."
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="workforce-management-overview"></a>A Munkaerő-kezelés áttekintése

[!include[banner](includes/banner.md)]
    
A munkaerő kezelése (WFM) szolgáltatást az ismerős pénztári (POS) ügyfelek, a modern pénztár és a felhőpénztár előnyeinek kihasználásával lehetővé teszi, hogy az üzletvezetők egyszerűen kezelhessék a munkaerőt. A WFM szolgáltatás a kiterjesztési keretrendszer használatával tölti le a megfelelő csomagokat a pénztárra. A csomagok letöltése akkor történik meg, amikor a pénztárt lezárják és újra megnyitják. Ezért amikor a Microsoft új funkciókat tesz közzé a WFM-hez, a pénztár alkalmazást be kell zárni és újra megnyitni.

A szolgáltatás segítségével az üzletvezetők könnyen létrehozhatják és közzétehetik az üzletek heti munkaütemezését. Az üzlet dolgozói ezután gyorsan megjeleníthetik saját munkarendjüket és a munkatársaik munkarendjét. Ezzel a módszerrel megtudhatják, kivel fognak együtt dolgozni a nekik kijelölt műszakban. Az üzletben dolgozók létrehozhatnak kéréseket távollétre, műszakcserére és műszakajánlatokra. Ezen kérések mind megadott munkafolyamatot indítanak el.

A műszak alatt az üzletben dolgozók használhatják az érkezéskori és távozáskori blokkolás szolgáltatást, amely be van építve a pénztári kliensbe. Az adatokat a rendszer beküldi a központba (HQ) bérlista-feldolgozásra. Az érkezéskori és távozáskori blokkolás szolgáltatás a pénztár meglévő képessége. A beállítással és a támogatott forgatókönyvekkel kapcsolatos további tudnivalókat lásd: [Érkezéskori és távozáskori blokkolás](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Támogatott esetek
Ez a szakasz további információkat tartalmaz a támogatott helyzetekről.

- **Ütemezések készítése és közzététele** – a WFM szolgáltatás a pénztári engedélyeket használja, amelyek a központban vannak meghatározva, annak eldöntéséhez, hogy a dolgozó rendelkezik-e üzletvezetői jogosultságokkal. Csak az üzletvezetők hozhatnak létre és tehetnek közzé ütemezéseket az Ütemezéskezelés művelettel. Gyorsan létrehozhatnak egy ütemezést úgy, ha egy dolgozó meglévő műszakát átmásolják és beillesztik egy másik dolgozóhoz. Ütemezést létrehozhatnak úgy is, hogy bármely előző hét ütemezését importálják az aktuális héthez.

    Ha egy ütemezés nincs közzétéve, akkor „vázlat” állapotban van, és másképp néz ki, mint a közzétett ütemezések. Az üzletvezetők ütemezést a **Közzététel** gombra kattintva tehetnek közzé bármely hétre vonatkozóan. Az ütemezés adott hétre történt közzététele után a rendszer automatikusan közzéteszi a módosításokat. Módosítások lehetnek például műszakok vagy távollétek hozzáadása vagy törlése, illetve és műszakok vagy távollétek módosítása. Az üzletben dolgozók csak a különböző hetekre közzétett ütemezéseket tekinthetik meg.
    
- **Kérelmek létrehozása és jóváhagyása** – az üzletben dolgozók háromféle kérelmet hozhatnak létre:

    - Távolléti kérelem
    - Műszakcsere-kérelem
    - Műszakajánlat-kérelem

    Ezek a kérelmek a Kérelmek ütemezése művelettel hozhatók létre. Minden kérelem megadott munkafolyamatot követ, és a dolgozók könnyen láthatják a kérelmük aktuális állapotát.
    
    A távolléti kérelmek automatikusan az üzletvezető elé kerülnek jóváhagyásra. Több üzletvezető esetén az összes vezető megtekinthet egy adott kérelmet, de csak egy vezető hagyhatja jóvá vagy utasíthatja el azt. A távolléti típusok konfigurálása a kiskereskedelmi munkaállomáson történik a **Szabadság- és távolléttípusok** lapon a **Kiskereskedelmi** modulban. Miután az üzletvezető jóváhagyja vagy elutasítja a kérést, átkerül az **Előzmények** lapra a Kérelmek ütemezése művelethez.
    
    A műszakcsere- vagy a műszakajánlat-kérelem először ahhoz a dolgozóhoz kerül, akihez a kérést küldték. Az üzletvezető csak azt követően tekintheti meg a kérést, hogy ez a dolgozó jóváhagyta. Következésképpen ha a dolgozó visszautasítja a műszakcsere- vagy műszakajánlat-kérelmet, a vezető nem tekintheti meg. A kérelmet létrehozó dolgozó is visszavonhatja a kérést, mielőtt vezető jóváhagyja vagy megtagadhatja azt.

- **Aktív üzleti dolgozók megjelenítése ütemezési nézetben** – amikor egy dolgozó hozzáadódik az üzlethez, például úgy, hogy társítják az üzlet alkalmazotti címjegyzékével, a dolgozó elérhetővé válik a WFM szolgáltatásban történő ütemezésre. Az központ lefuttatja a **Dolgozó adatainak feldolgozása a munkaerő-kezeléshez** nevű ismétlődő kötegelt feladatot. Ez a feladat előkészíti az üzlet dolgozóinak hozzárendeléseit, amelyek átküldésre kerülnek a Common Data Service-be (CDS).

    Ugyanez az eljárást akkor is használatos, ha a dolgozót törölnek az üzletből. Azonban az eltávolított dolgozó továbbra is látható a múltbeli, jelenlegi és jövőbeli heteken, ha aktív műszak vagy távollét van hozzárendelve a dolgozóhoz. Emiatt, hacsak a műszakokat és a távolléteket nem törlik, az eltávolított dolgozó továbbra is megjelenik ezeken a heteken.

