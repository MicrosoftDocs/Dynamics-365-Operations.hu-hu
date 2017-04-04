---
title: "A felhő POS és MPOS kiterjesztett bejelentkezési funkció beállítása"
description: "A wiki magába foglalja a felhőalapú pénztár és Kiskereskedelmi Modern pénztár (MPOS) kiterjesztett bejelentkezés beállításainak lehetőségeit."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 0dc80784a5c9a7de6009826284cb68f1aee83f70
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a>A felhő POS és MPOS kiterjesztett bejelentkezési funkció beállítása

A wiki magába foglalja a felhőalapú pénztár és Kiskereskedelmi Modern pénztár (MPOS) kiterjesztett bejelentkezés beállításainak lehetőségeit.

<a name="setting-up-extended-logon"></a>Kiterjesztett bejelentkezés beállítása
=========================

A vonalkódmaszkok megtalálhatja a telepítő **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**Funkcióprofilok**. A **Funkciók** gyorslap a következő kiterjesztett belépéshez tartozó beállításokat tartalmazza.

### <a name="staff-bar-code-logon"></a>Munkatárs - vonalkódos bejelentkezés

Amikor a **Személyzeti vonalkódos bejelentkezés** beállítás engedélyezve van, a pénztárhoz tartozó kiterjesztett bejelentkezéssel rendelkező dolgozók be tudnak lépni vonalkód használatával.

### <a name="staff-bar-code-logon-requires-password"></a>A személyzeti vonalkódos bejelentkezéshez jelszó szükséges

Ha a **A személyzeti vonalkódos bejelentkezéshez jelszó szükséges** beállítás engedélyezve van, a személyzeti vonalkódos bejelentkezés csak azt a dolgozót engedi belépni, akinek van jogosultsága az aktuális kiterjesztett belépéshez. A dolgozóknak be kell írniuk jelszavukat akkor is, ha ez a beállítás van engedélyezve.

### <a name="staff-card-logon"></a>Munkatárs - kártyás bejelentkezés

Amikor a **Személyzeti kártyás bejelentkezés** beállítás van engedélyezve, a pénztárhoz tartozó kiterjesztett bejelentkezéssel rendelkező dolgozók be tudnak lépni mágnescsík használatával.

### <a name="staff-card-logon-requires-password"></a>A személyzeti kártyás bejelentkezéshez jelszó szükséges

Ha a **A személyzeti kártyás bejelentkezéshez jelszó szükséges** beállítás engedélyezve van, a személyzeti kártyás bejelentkezés csak azt a dolgozót engedi belépni, akinek van jogosultsága az aktuális kiterjesztett belépéshez. A dolgozóknak be kell írniuk jelszavukat akkor is, ha ez a beállítás van engedélyezve.

<a name="assigning-an-extended-logon"></a>Hozzárendelés kiterjesztett bejelentkezéshez
===========================

Alapesetben csak a menedzser tud kiterjesztett bejelentkezést hozzárendelni a dolgozókhoz. Kiterjesztett bejelentkezési hozzárendeléséhez Ugrás **kiterjesztett bejelentkezés** a POS Terminálon. Saját Kezelőazonosító megadásakor a Keresés mezőbe, majd keresse meg a munkavállaló. Válassza ki a dolgozót, majd kattintson az **Hozzáadás** gombra. A következő oldalon húzza le vagy olvassa be a kiterjesztett belépést, hogy hozzárendelhesse azt a dolgozóhoz. Ha a lehúzás vagy a beolvasás sikeresen megtörtént, az **OK **gomb elérhetővé válik. Kattintson a **OK** gombra, hogy elmentse az adott dolgozóhoz kapcsolódó kiterjesztett bejelentkezést.

<a name="deleting-an-extended-logon"></a>Kiterjesztett bejelentkezés törlése
==========================

A dolgozó kiterjesztett bejelentkezésének törléséhez keresse meg a dolgozót a **Kiterjesztett bejelentkezés** művelet használatával. Válassza ki a dolgozót, majd kattintson az **Törlés** gombra. Minden (az adott dolgozóhoz tartozó) kiterjesztett bejelentkezési hitelesítő adat törlődik.

<a name="extending-extended-logon"></a>Kiterjesztett bejelentkezés kiterjesztése
========================

A bejelentkezés szolgáltatás kibővíthető, így pedig további beléptető szerkezetek is használhatóvá válnak (például: tenyér beolvasó). További részletek a Pénztár kiterjesztés dokumentációban találhatók.

<a name="using-extended-logon"></a>Kiterjesztett bejelentkezés használata
====================

Amennyiben a kiterjesztett bejelentkezés konfigurációja megtörtént és a dolgozóhoz hozzá lett rendelve jelszó vagy mágnescsík, a dolgozónak csupán le kell húznia vagy beolvastatnia a kártyáját, míg a pénztár belépő oldala meg van jelenítve. Ha a jelszó is szükséges a bejelentkezéshez, a dolgozónak azt is szükséges beütnie..


