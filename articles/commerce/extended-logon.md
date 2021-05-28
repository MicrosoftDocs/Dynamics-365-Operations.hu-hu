---
title: Kiterjesztett bejelentkezés funkció beállítása MPOS-hoz és Pénztár felhőhöz
description: A témakör magába foglalja a Cloud POS és Retail Modern POS (MPOS) kiterjesztett bejelentkezés beállításainak lehetőségeit.
author: rubencdelgado
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9d8889581e2e11fa5261805c866a6014df57611
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027576"
---
# <a name="set-up-extended-logon-functionality-for-mpos-and-cloud-pos"></a>Kiterjesztett bejelentkezési funkció beállítása az MPOS-hez és a Cloud POS-hez

[!include [banner](includes/banner.md)]

A témakör magába foglalja a Cloud POS és Retail Modern POS (MPOS) kiterjesztett bejelentkezés beállításainak lehetőségeit.

## <a name="setting-up-extended-logon"></a>Kiterjesztett bejelentkezés beállítása

A vonalkódmaszkok beállítását megtalálja a következő helyen: **Retail és Commerce** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztárprofilok** &gt; **Funkcióprofilok**. A **Funkciók** gyorslap a következő kiterjesztett belépéshez tartozó beállításokat tartalmazza.

### <a name="staff-bar-code-logon"></a>Munkatárs - vonalkódos bejelentkezés

Amikor a **Személyzeti vonalkódos bejelentkezés** beállítás engedélyezve van, a pénztárhoz tartozó kiterjesztett bejelentkezéssel rendelkező dolgozók be tudnak lépni vonalkód használatával.

### <a name="staff-bar-code-logon-requires-password"></a>A személyzeti vonalkódos bejelentkezéshez jelszó szükséges

Ha a **A személyzeti vonalkódos bejelentkezéshez jelszó szükséges** beállítás engedélyezve van, a személyzeti vonalkódos bejelentkezés csak azt a dolgozót engedi belépni, akinek van jogosultsága az aktuális kiterjesztett belépéshez. A dolgozóknak be kell írniuk jelszavukat akkor is, ha ez a beállítás van engedélyezve.

### <a name="staff-card-logon"></a>Munkatárs - kártyás bejelentkezés

Amikor a **Személyzeti kártyás bejelentkezés** beállítás van engedélyezve, a pénztárhoz tartozó kiterjesztett bejelentkezéssel rendelkező dolgozók be tudnak lépni mágnescsík használatával.

### <a name="staff-card-logon-requires-password"></a>A személyzeti kártyás bejelentkezéshez jelszó szükséges

Ha a **A személyzeti kártyás bejelentkezéshez jelszó szükséges** beállítás engedélyezve van, a személyzeti kártyás bejelentkezés csak azt a dolgozót engedi belépni, akinek van jogosultsága az aktuális kiterjesztett belépéshez. A dolgozóknak be kell írniuk jelszavukat akkor is, ha ez a beállítás van engedélyezve.

## <a name="assigning-an-extended-logon"></a>Hozzárendelés kiterjesztett bejelentkezéshez

Alapesetben csak a menedzser tud kiterjesztett bejelentkezést hozzárendelni a dolgozókhoz. Kiterjesztett bejelentkezés hozzárendeléséhez, kattintson a **Kiterjesztett bejelentkezés** opcióra a pénztárban. Ezután keressen rá a dolgozóra úgy, hogy begépeli annak dolgozói azonosítóját a keresőmezőbe. Válassza ki a dolgozót, majd kattintson az **Hozzáadás** gombra. A következő oldalon húzza le vagy olvassa be a kiterjesztett belépést, hogy hozzárendelhesse azt a dolgozóhoz. Ha a lehúzás vagy a beolvasás sikeresen megtörtént, az **OK** gomb elérhetővé válik. Kattintson a **OK** gombra, hogy elmentse az adott dolgozóhoz kapcsolódó kiterjesztett bejelentkezést.

## <a name="deleting-an-extended-logon"></a>Kiterjesztett bejelentkezés törlése

A dolgozó kiterjesztett bejelentkezésének törléséhez keresse meg a dolgozót a **Kiterjesztett bejelentkezés** művelet használatával. Válassza ki a dolgozót, majd kattintson az **Törlés** gombra. Minden (az adott dolgozóhoz tartozó) kiterjesztett bejelentkezési hitelesítő adat törlődik.

## <a name="extending-extended-logon"></a>Kiterjesztett bejelentkezés kiterjesztése

A bejelentkezés szolgáltatás kibővíthető, így pedig további beléptető szerkezetek is használhatóvá válnak (például: tenyér beolvasó). További részletek a Pénztár kiterjesztés dokumentációban találhatók.

## <a name="using-extended-logon"></a>Kiterjesztett bejelentkezés használata

Amennyiben a kiterjesztett bejelentkezés konfigurációja megtörtént és a dolgozóhoz hozzá lett rendelve jelszó vagy mágnescsík, a dolgozónak csupán le kell húznia vagy beolvastatnia a kártyáját, míg a pénztár belépő oldala meg van jelenítve. Ha a jelszó is szükséges a bejelentkezéshez, a dolgozónak azt is szükséges beütnie..


[!INCLUDE[footer-include](../includes/footer-banner.md)]