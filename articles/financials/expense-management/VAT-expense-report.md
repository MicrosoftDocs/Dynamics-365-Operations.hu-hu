---
title: "Áfa-visszaigénylés a Költséggazdálkodás modulban"
description: "Ez a témakör bemutatja, hogyan lehet visszatérítést kapni az erre jogosult általános forgalmi adó (áfa) tranzakciók után."
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: d1c9357f8f51e1a87aebeb8f802dbe3b5fdd5aa0
ms.contentlocale: hu-hu
ms.lasthandoff: 03/13/2018

---

# <a name="vat-recovery-in-expense-management"></a>Áfa-visszaigénylés a Költséggazdálkodás modulban

Ha visszatérítést szeretne kapni az erre jogosult általános forgalmi adó (áfa) tranzakciók után, a vállalatnak vagy szervezetnek pontos adatokat kell azonosítania, gyűjtenie, ellenőriznie és elküldenie. Ez a folyamat több feladatokból áll, és a vállalat méretétől függően több alkalmazottat vagy szerepkört tartalmazhat.

Áfa-visszaigényléshez a Költséggazdálkodás modulban a következő előfeltételeket kell teljesíteni:

- Adókódokat kell létrehozni a költségkategóriákhoz kiosztott országok/területek számára.
- Áfakódonként egy áfacsoportot kell kötelezően létrehozni.
- Áfakódcsoportonként egy cikkáfakódot kell kötelezően létrehozni.

Az előfeltételek teljesítését követően az alkalmazottak a következő lépésekkel kérhetnek visszatérítést az áfa-tranzakciók után.

1. A költségjelentésen adja meg a hitelkártya-tranzakciók adózási információit az áfa-visszatérítési jogosultság megállapításához.
2. Győződjön meg arról, hogy minden adóadat teljes, és adja fel a költségjelentést.
3. Dolgozza fel azokat a költségeket, amelyek nemzetközi áfa-visszaigénylésre jogosultak.
4. Küldje el a harmadik fél szállítónak az áfa-visszaigénylési adatokat a nemzetközi visszaigénylések igényléséhez.
5. Dolgozza fel a kiadásokat a belföldi áfa-visszaigényléshez.

A következő szakaszok példaként ismertetik, hogy a Contoso-alkalmazottak hogyan hajtották végre az egyes lépéseket.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>A költségjelentésen adja meg a hitelkártya-tranzakciók adózási információit az áfa-visszatérítési jogosultság megállapításához

Nancy, a Contoso Egyesült Államokban dolgozó üzletkötője, nemrég tért vissza egy üzleti útról az Egyesült Királyságból. Az utazás során néhány hitelkártyára terhelt étkezési kiadás merült fel. Nancynek most létre kell hoznia egy költségjelentést a költségei egyeztetésére.

Amikor Nancy adatokat visz fel a költségjelentésbe, kiválasztja az **Egyesült Királyság** lehetőséget az **Ország/régió** mezőben a **Költségjelentés szerkesztése** oldalon. Az áfacsoportokat szűri a program, hogy csak az Egyesült Királyságban érvényes csoportok jelenjenek meg. Nancy kijelöli az **Egyesült Királyság 001** áfacsoportot, és kiválasztja az **Étkezés** cikkáfacsoportot. Ezután hozzáad egy új tranzakciót a szállásra vonatkozóan. Mivel csak egy áfacsoport és egy cikkáfacsoport létezik a szállás esetében az Egyesült Királyságra nézve, ez az információ automatikusan kitöltődik Nancy költségjelentésén.

A Contoso irányelvei szerint minden kiadásnak rendelkeznie kell kapcsolódó nyugtával. Ezért amikor Nancy menti a költségjelentést, üzenetet kap, amely arról tájékoztatja, hogy csatolnia kell a nyugtát minden egyes tranzakciókhoz, amelyet feltüntet a költségjelentésen. Nancy ellenőrzi, hogy minden tranzakcióhoz csatolta-e a nyugta digitális képét a költségjelentésben, és ezután elküldi jóváhagyásra a jelentést. Majd elküldi a papírra nyomtatott nyugtákat a háttérirodai feldolgozási csoportnak. A csoport elküldi a harmadik fél szállítónak az áfa-visszaigénylési adatokat: ez a szállító intézi a nemzetközi visszaigényléseket a Contoso számára.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Győződjön meg arról, hogy minden adóadat teljes, és adja fel a költségjelentést

Aprilnek, a Contoso kötelezettségekkel foglalkozó koordinátorának minden adózási információt be kell vinnie, amelyik hiányzik a költségjelentésből, a jelentés feladása előtt. Megnyitja a **Költségjelentés részletei** lapot, és megnézi Nancy jóváhagyott költségjelentését. Ezután April megnyitja a költségjelentést, és megtekinti a tranzakciók részletes adatait. Azt látja, hogy Nancy nem adta meg a cikkáfacsoportját az egyik tranzakciónak. Mivel ezek az adatok nincsenek megadva, April nem adhatja fel a költségjelentést. Ezért April megnézi az **Adókonfigurációk** lapot a Költséggazdálkodás modulban, és megkeresi a megfelelő cikkáfacsoportot az ország/régió és a tranzakció típusa szerint. April most már feladhatja a költségjelentést a főkönyvbe.

Amikor April a költségjelentést feladja, visszaigényelhető áfa munkaelem jön létre. Ez a munkatétel az háttérirodai feldolgozási csoport egy tagjához lesz rendelve. April üzenetet kap, amely megerősíti, hogy a feladás sikeres volt. Ez az üzenet felsorolása a visszatérítésre jogosult áfa-tranzakciók számát is.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Dolgozza fel azokat a költségeket, amelyek nemzetközi áfa-visszaigénylésre jogosultak

Arnie a Contoso háttérirodai feldolgozási csoportjának a tagja, és az ő felelőssége az, hogy az áfa-visszaigényléshez szükséges összes információ megtalálható legyen a költségjelentésben. Megnyitja a **Költségadó-visszaigénylés** lapot, és kiválasztja a Nancy által elküldött költségjelentést. Arnie ellenőrzi, hogy minden szükséges nyugtát csatoltak, és hogy a megfelelő áfacsoportot és cikk-áfakódokat vittek be.

Amikor Arnie megkapja a papírra nyomtatott nyugtákat Nancytől, összeveti a digitalizált nyugtákat a papír nyugtákkal, majd módosítja a költségjelentés állapotát **Visszatérítésre kész** állapotra.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Küldje el a harmadik fél szállítónak az áfa-visszaigénylési adatokat a nemzetközi visszaigénylések igényléséhez

Amikor Arnie készen áll, hogy elküldje a harmadik fél szállítónak a költségjelentést, amelyik aztán elindítja az áfa-visszaigénylési folyamatot, megnyitja a **Költségadó-visszaigénylés** oldalt. Szűri az oldalt, hogy csak a **Visszatérítésre kész** megjelölésű költségjelentések legyenek láthatók. Arnie kiválasztja a **Fájl** &gt; **Exportálás az Excel programba** lehetőséget. A rendszer a költségjelentés áfa-adatait Microsoft Excel-munkalapba exportálja. Arnie ezt a munkalapot elküldi a külső szállítónak, és mellékel egy üzenetet, amely arról tájékoztat, hogy a papírra nyomtatott nyugtákat elküldte futárszolgálattal.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Dolgozza fel a kiadásokat a belföldi áfa-visszaigényléshez

Arnie-nak ellenőriznie kell, hogy a költségjelentés-tranzakciók jogosultak áfa-visszaigénylés, és hogy a digitális nyugtákat csatolták a jelentésekhez. A belföldi visszaigénylésre jogosult kiadások feldolgozásának elindításához Arnie megnyitja a **Költségadó-visszaigénylés** lapot, és kiválasztja a költségjelentést, amely megköveteli az ellenőrzést. Ellenőrzi, hogy nyugták ne az alkalmazott, hanem a vállalat nevére szóljanak. Áfa-visszaigényléshez a nyugtáknak a vállalat nevére kell szólniuk. Arnie ezután megerősíti, hogy a megfelelő áfacsoportot és cikk-áfakódokat alkalmazták.

Amikor Arnie megkapja a papírra nyomtatott nyugtákat, a költségjelentés állapotát módosítja **Visszatérítésre kész** állapotra. Ekkor továbbíthatja a visszaigénylési kérelmet a megfelelő adóhatóság felé. Ebben az esetben, az Egyesült Államokban, a megfelelő adóhatóság az Internal Revenue Service (IRS).

