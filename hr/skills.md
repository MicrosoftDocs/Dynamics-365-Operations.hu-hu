---
title: "A munkaerő szakértelmének üzleti igényű igazítása"
description: "Nyomon követheti azokat a szakértelmeket, amelyekkel dolgozók, pályázók vagy kapcsolattartók jelentkeznek vagy jelentkezniük kellene. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ae940cdbab2166d8fe3f2f396c84ed4a09c2ca7e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>A munkaerő szakértelmének üzleti igényű igazítása

[!include[banner](includes/banner.md)]


Nyomon követheti azokat a szakértelmeket, amelyekkel dolgozók, pályázók vagy kapcsolattartók jelentkeznek vagy jelentkezniük kellene. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.

Nyomon követheti a szakértelmek például a következők:
-   Felügyelet – képesség mások munkájának felügyelésére.
-   Vezetés – az alkalmazottak és a vállalati területek vezetésének képessége.
-   Tervezés – képesség az előrelátásra, az elképzelések formába öntésére, és azok átlátására.
-   HTML - HTML-kódolás ismerete.

A szakértelem adott személyhez vagy beosztáshoz való hozzárendelése, szakértelem-feltérképezési keresés futtatása és szakértelemprofil létrehozása előtt meg kell adnia a szakértelemre vonatkozó adatokat a **Szakértelmek** képernyőn. Minden egyes szakértelmhez kiválaszthatja a típust és a minősítési modellt.

## <a name="rating-models"></a>Minősítési modellek
A minősítési modellek segítenek meghatározni a személy valós szakértelmi szintjét, az elérendő szintet, vagy egy adott beosztáshoz szükséges szintet. Legfeljebb 10 minősítési szintet adhat meg.  Egy értékelési modell minden szintjéhez tényező társul.  A tényező értékét a különböző minősítési modelleket használó készségek pontszámainak normalizálására használják.  A tényezőnek egy 0 és 9 közötti számnak kell lennie, és minden szinthez egyedi tényezőnek kell tartoznia.  A magasabb értékű szorzóval rendelkező szintek nagyobb súlyt képviselnek a minősítés modellben.

## <a name="specify-job-skills"></a>Beosztáshoz szükséges szakértelmek meghatározása
Ha információkat ad meg egy munkakörről, megadhatja azokat a készségeket, amelyekre a személynek szüksége van a munkakörhöz szükséges munka elvégzéséhez.  Emellett megadhatja a kívánt szintet minden egyes készség számára, továbbá a készség fontosságának szintjét is. Különböző beosztásoknál ugyanaz a szakértelem eltérő fontosságú lehet.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>A dolgozók, pályázók és kapcsolattartók szakértelmeinek megadása
A dolgozók, pályázók vagy kapcsolattartók megcélzott vagy már megszerzett szakértelmeit is rögzítheti. A megcélzott szakértelem olyan szakértelem, amelyet az adott személy el szeretne érni. A tényleges szakértelem az, amivel már rendelkezik.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> A szakértelem-feltérképezés és a szakértelem-feltérképezési profilok beállítása
Létrehozhat egy készségleképező keresést olyan dolgozó, jelentkező vagy kapcsolattartó kereséséhez, aki megfelelő képesítéssel rendelkezik egy adott feladattípus végrehajtásához. A készségleképező keresések készségek, képzés, tanúsítványok, megbízható pozíciók és projekttapasztalatok között keresnek, és olyan találatokat adnak vissza, amelyek megfelelnek a megadott feltételeknek.  Például hasznos lehet tudni, hogy szervezete mely dolgozói keresték meg a CPA-jukat.

A készségleképező profilokkal olyan jelenlegi alkalmazottakra vagy jelöltekre kereshet, akiknek olyan végzettségei vannak, amelyek közvetlenül megfelelnek az üzleti szükségleteknek.  Létrehozhat például egy készségleképezési profilt a szervezeténél meglévő nyitott pozícióhoz. Egy adott beosztáshoz profilok létrehozása és másolása a szakértelem, a végzettség és a tanúsítványt az adott feladat a profilt, gyorsan kereshet dolgozók, pályázó és kapcsolattartó személyek megfelelő egy vagy több mellőzhető a profilban megadott feltételeknek megfelelő és a pályázók, akiknek szakismeretei leginkább megfelelnek a projekthez szükséges szakértelmek listájának megtekintése.

>**Megjegyzés** Csak a kereséshez kiválasztott dolgozók, pályázók és kapcsolattartó személyek jelennek meg a szakértelem-feltérképezés eredménylistájában és kerülnek bele szakértelemprofilba. A dolgozó, pályázó vagy kapcsolattartó személy a szakértelem-feltérképezés kereséseinek szerepeltetéséhez beállítása a **felvétel a szakértelem-feltérképezés** kiválasztási Igen, a következő lapokon:

> + Dolgozó
> + Alkalmazott
> + Pályázó
> + Kapcsolattartók

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Szakértelemhiány-elemzések és szakértelemprofil-elemzések
Szakértelemprofil-elemzés létrehozásával egy dolgozó, pályázó vagy kapcsolattartó adott dátumon érvényes kompetenciáinak listáját tekintheti meg. Szakértelemhiány-elemzéssel egy személy szakértelmeit összehasonlíthatja egy adott feladathoz szükséges szakértelmi szintekkel  



<a name="see-also"></a>Lásd még
--------

[Emberi erőforrások](index.md)




