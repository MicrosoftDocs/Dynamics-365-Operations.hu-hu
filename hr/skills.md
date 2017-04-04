---
title: "A munkaerő szakértelmének üzleti igényű igazítása"
description: "Nyomon követheti azokat a szakértelmeket, amelyekkel dolgozók, pályázók vagy kapcsolattartók jelentkeznek vagy jelentkezniük kellene. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 720a1f272948eb310dc3cd02588aeec40b556d20
ms.openlocfilehash: 31dda85ff2e4a4e5380401b031b2dd74acff394b
ms.lasthandoff: 03/31/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>A munkaerő szakértelmének üzleti igényű igazítása

Nyomon követheti azokat a szakértelmeket, amelyekkel dolgozók, pályázók vagy kapcsolattartók jelentkeznek vagy jelentkezniük kellene. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.

Nyomon követheti a szakértelmek például a következők:
-   Felügyelet – képesség mások munkájának felügyelésére.
-   Vezetés – az alkalmazottak és a vállalati területek vezetésének képessége.
-   Tervezés – képesség az előrelátásra, az elképzelések formába öntésére, és azok átlátására.
-   HTML - HTML-kódolás ismerete.

A szakértelem adott személyhez vagy beosztáshoz való hozzárendelése, szakértelem-feltérképezési keresés futtatása és szakértelemprofil létrehozása előtt meg kell adnia a szakértelemre vonatkozó adatokat a **Szakértelmek** képernyőn. Minden egyes szakértelmhez kiválaszthatja a típust és a minősítési modellt.

## <a name="rating-models"></a>Minősítési modellek
A minősítési modellek segítenek meghatározni a személy valós szakértelmi szintjét, az elérendő szintet, vagy egy adott beosztáshoz szükséges szintet. Legfeljebb 10 minősítési szintet adhat meg.  A minősítési modell minden egyes szintje hozzá van rendelve egy tényező.  A tényező értéke lesz a pontszámokat, amely különböző minősítési modellek használata normalizálandó.  A tényezőnek kell lennie 0-9 és az egyes szintek között számos egyedi tényező kell rendelkeznie.  A magasabb értékű szorzóval rendelkező szintek nagyobb súlyt képviselnek a minősítés modellben.

## <a name="specify-job-skills"></a>Beosztáshoz szükséges szakértelmek meghatározása
A feladat adatainak bevitelekor szakértelemről, amely egy személy van szükség a projekthez szükséges munka elvégzése is megadhat.  Megadhatja továbbá a kívánt szinten minden szakértelem, valamint a szakértelem fontossági szintjét. Különböző beosztásoknál ugyanaz a szakértelem eltérő fontosságú lehet.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>A dolgozók, pályázók és kapcsolattartók szakértelmeinek megadása
A dolgozók, pályázók vagy kapcsolattartók megcélzott vagy már megszerzett szakértelmeit is rögzítheti. A megcélzott szakértelem olyan szakértelem, amelyet az adott személy el szeretne érni. A tényleges szakértelem az, amivel már rendelkezik.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> A szakértelem-feltérképezés és a szakértelem-feltérképezési profilok beállítása
Létrehozhat egy dolgozó, pályázó vagy kapcsolattartó személy, aki egy adott típusú feladat elvégzéséhez kereséséhez a szakértelem-feltérképezés keresése. Szakértelem-feltérképezési keresés megjelenését keresztül képességek, oktatás, tanúsítványok, a bizalom és a projekt tapasztalat és a megadott feltételeknek megfelelő találatot.  Például hasznos lehet tudni, ahol a munkavállalók a szervezetben létrehozott a CPA.

Szakértelem feltérképezése-profilok lehetővé teszik jelenlegi alkalmazottak vagy vállalat igényeinek közvetlenül megfelelő képesítéssel rendelkező jelöltek keresése.  Például létrehozhat egy nyitott pozíciót a szervezetben a szakértelem-feltérképezés profilt. Egy adott beosztáshoz profilok létrehozása és másolása a szakértelem, a végzettség és a tanúsítványt az adott feladat a profilt, gyorsan kereshet dolgozók, pályázó és kapcsolattartó személyek megfelelő egy vagy több mellőzhető a profilban megadott feltételeknek megfelelő és a pályázók, akiknek szakismeretei leginkább megfelelnek a projekthez szükséges szakértelmek listájának megtekintése.

<table>
<thead>
<tr class="header">
<th><strong>Megjegyzés </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Csak a kereséshez kiválasztott dolgozók, pályázók és kapcsolattartó személyek jelennek meg a szakértelem-feltérképezés eredménylistájában és kerülnek bele szakértelemprofilba. A dolgozó, pályázó vagy kapcsolattartó személy a szakértelem-feltérképezés kereséseinek szerepeltetéséhez beállítása a <strong>felvétel a szakértelem-feltérképezés</strong> kiválasztási Igen, a következő lapokon:
<ul>
<li>Dolgozó</li>
<li>Alkalmazott</li>
<li>Pályázó</li>
<li>Kapcsolattartók</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Szakértelemhiány-elemzések és szakértelemprofil-elemzések
Szakértelemprofil-elemzés létrehozásával egy dolgozó, pályázó vagy kapcsolattartó adott dátumon érvényes kompetenciáinak listáját tekintheti meg. Szakértelemhiány-elemzéssel egy személy szakértelmeit összehasonlíthatja egy adott feladathoz szükséges szakértelmi szintekkel  



<a name="see-also"></a>Lásd még
--------

[Human resources](index.md)


