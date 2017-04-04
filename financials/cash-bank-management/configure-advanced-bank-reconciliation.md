---
title: "Továbbfejlesztett banki egyeztetés áttekintés"
description: "Továbbfejlesztett banki egyeztetés lehetővé teszi elektronikus banki kivonatok importálása és a Microsoft Dynamics 365 műveletek banki tranzakciók automatikusan egyeztetni.  Ez a cikk a beállítási folyamatokról nyújt tájékoztatást az egyeztetésre vonatkozóan."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Továbbfejlesztett banki egyeztetés áttekintés

Továbbfejlesztett banki egyeztetés lehetővé teszi elektronikus banki kivonatok importálása és a Microsoft Dynamics 365 műveletek banki tranzakciók automatikusan egyeztetni.  Ez a cikk a beállítási folyamatokról nyújt tájékoztatást az egyeztetésre vonatkozóan.  

Számos darabot, hogy a továbbfejlesztett banki egyeztetés funkció használata előtt be kell állítani. Bankkivonat importálása beállításával kapcsolatos további tudnivalókért lásd: [a banki kivonat importálási folyamat beállítása](set-up-advanced-bank-reconciliation-import-process.md).  Állítsa be az egyeztetési folyamat követelményei vannak az alább részletezett.

## <a name="transaction-codes"></a>Tranzakciókódok
Kifizetésitranzakció-kódok a banki egyeztetési szabályok részeként használható.  Kifizetésitranzakció-kódok segítségével megfelelően csak az azonos típusú tranzakciók Dynamics 365 műveletekhez és a bankszámlakivonat között.  Ez a típus a megfelelő végrehajtásához kell először Dynamics 365 műveletekhez a banki tranzakciókhoz használt tranzakciótípus megadása, majd e típusok hozzárendelése a bank által használt szereplő tranzakciókódok.  Tranzakciótípusok 365 Dynamics műveletek banki tranzakciók meg vannak adva a **banki tranzakciótípus** oldalon.  Ez akkor is, ahol megadhatja a társított tranzakció típusát feladásokhoz használt fő számla. 

Miután a Dynamics 365 műveletek banki tranzakció kódok vannak megadva, akkor rendelje hozzá azokat, az elektronikus banki kivonatok használt tranzakciókódok.  Történik a leképezési folyamat segítségével a **Tranzakciókód-hozzárendelés** oldalon.  Minden bankszámlát külön kitöltése Tranzakciókód-hozzárendelés.

## <a name="matching-rules-and-matching-rule-sets"></a>Az Egyeztetési szabályok és a megfelelő szabálykészletek
Egyeztetési szabályok lehetővé teszik az automatikus egyeztetését Dynamics 365 műveletek banki tranzakciókhoz és a bankszámlakivonaton szereplő feltételek meghatározása.  Egyeztetési szabályok beállítása úgy történik, a **egyeztetési szabályok** oldalon.  További tudnivalókért lásd: [banki egyeztetési szabályok beállítása](set-up-bank-reconciliation-matching-rules.md). 

Adjon meg egy csoportot a megfelelő sorrendben a banki egyeztetés során futtatandó szabályok szabálykészletek szolgálnak.  Szabálykészletek van beállítva a **Egyeztetési szabálykészletek** oldalon.

## <a name="cash-and-bank-management-parameters"></a>Készpénz- és bankkezelési paraméterek
Számos paramétert a továbbfejlesztett banki egyeztetési folyamat jellemző a **banki paraméterek** oldalon.  A **megjelenítése kivonat sor összege tartozik/követel** megváltozik az összegek megtekintése a **banki kivonat** oldalon.  Ha ezt a beállítást választja, a banki kivonat tranzakció összegeit tartozik és a követel oszlopokban jelenik meg.  Ha nincs bejelölve, a banki kivonat tranzakció összegeit a megfelelő jelzéssel legyen egyetlen összeg oszlopban jelenik meg. 

A ellenőrzési beállításokat a Paraméterek lapon beállított egyeztetési szabályok beállítása a beállítások felülbírálása.  Például nem lehet manuálisan vagy automatikusan megfelelteti a dokumentumok a Paraméterek lapon beállított dátum különbség túl.  Is ha a lehetőséget, hogy **tranzakciótípus-leképezésének ellenőrzése** van jelölve, a tranzakciótípusok le kell képezni illeszkednie kell manuálisan vagy automatikusan a Dynamics 365 műveletek banki tranzakció és annak érdekében, hogy a tranzakciók a bankszámlakivonaton szereplő tranzakció között. 

Is konfigurálnia kell a szükséges számsorozatokat a **banki paraméterek** oldalon.  A a **Number sequences** lapon, a beállított számsorozat-kódok a Letöltés **azonosító, utasítást azonosító, azonosító összehangolása és banki egyeztetési** hivatkozásokat.

## <a name="bank-account-reconciliation-options"></a>Bankszámla-egyeztetés beállítások
Először engedélyeznie kell a bankszámlához tartozó speciális banki egyeztetést.  Számos további beállítások érhetők el a **bankszámla** oldalon a továbbfejlesztett banki egyeztetés funkció engedélyezése után. 

**Elektronikus fizetési visszaigazolásként használata banki kivonatok** funkció a banki egyeztetés funkciók integrálható elektronikus fizetési állapot.  Ha ez engedélyezve van, a banki bizonylat automatikusan létrejön az elektronikus fizetési állapot értéke a **küldött**.  Ezenkívül egy elektronikus fizetési állapotának frissülni fog a **küldött**, **érkezett** után a fizetési mérik, egyeztetett, és könyvelt. 

A **a kimutatásokban bankszámla neve** a neve, az elektronikus banki kivonatok a bankszámlához használt.  Ez a név használatos, mely tranzakciók importálása olyan nyilatkozat, amely több bankszámlákra vonatkozó információkat tartalmazhat a bankszámlához tartozó meghatározásakor. 

A lehetőséget, hogy **az importálás után összehangolás** lesz automatikusan a banki kivonat ellenőrzése, hozzon létre egy új bankszámla-egyeztetés és a munkalap és az alapértelmezett szabály beállítása megfelelő futtatásához.  Ez a funkció az előfizetőknek a tranzakciókat kézzel kell egyeztetni, pontig.  A bankszámla a beállítás alapértelmezés szerint importálásakor.


