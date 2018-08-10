--- 
title: "A kötelezettségek számlaegyeztetése hitelesítésének beállítása"
description: "Ez a felvétel az USMF bemutatócéget használja."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9bf83269c34133509734691fd018ee703c40626
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-accounts-payable-invoice-matching-validation"></a>A kötelezettségek számlaegyeztetése hitelesítésének beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a felvétel az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva. Ha az Ön vállalata a költségek lehetőség segítségével követi nyomon az olyan költségeket, mint például a szállítás, akkor győződjön meg arról, hogy a Költség-konfigurációs kulcs ki van választva.  A kötelezettségek számlaegyeztetése a szállítói számla, a beszerzési rendelés és a termékbevételezés egyeztetési folyamatát jelenti. A fenti dokumentumok közötti különbségeket egyeztetési eltérésnek nevezzük. Az egyeztetési eltéréseket a rendszer összeveti a megadott tűréshatárokkal. Amennyiben az egyezési eltérés meghaladja a tűréshatár-százalékot vagy összeget, a Szállítói számla adatlapon, illetve a Számlaegyeztetés részletei adatlapon megjelenik az egyeztetési eltérés ikon.

1. Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.
2. Kattintson a Számlaegyeztetés fülre.
3. Jelölje be a Számlaegyeztetés-ellenőrzés engedélyezése jelölőnégyzetet, vagy törölje a jelölést.
    * A mezőben válassza ki hogy előírja-e a jóváhagyást a számlaegyeztetési eltéréseket tartalmazó számlák feladása előtt. Ha az Engedélyezés figyelmeztetéssel lehetőség van beállítva, úgy vizuális jelzés mutatja, ha a számlaegyeztetési eltérés meghaladja a tűréshatárt. A számlát azonban fel tudja adni. A munkafolyamatok és a számlaegyeztetés-ellenőrzés együttes használatához győződjön meg arról, hogy, a többszörös jóváhagyás elkerülése érdekében, az Eltéréseket tartalmazó számla feladása mező beállítása Engedélyezés figyelmeztetéssel legyen.  
    * Válassza ki a Számlafejléc állapotának automatikus frissítése mezőben, hogy automatikus legyen-e az egyeztetés, amikor a rendszer a számla adatait tölti ki. A javasolt beállítás az Igen, kivéve, ha az adatbevitel teljesítménye nem megfelelő. Az automatikus frissítések letiltása gyorsíthatja a rendszer teljesítményét, mivel a rendszer mellőzi a számlaegyeztetés-ellenőrzést az adatbevitel során. Amennyiben a Nem beállítást választja, úgy az adatbeviteli adminisztrátornak manuálisan kell frissítenie a számlaegyeztetési állapotot a számlaegyeztetés-ellenőrzés eredményeinek megtekintéséhez.  
4. Módosítsa a Számlaösszegek szakasz bővítését.
5. A tényleges számlaösszegek és a várható összegek egyeztetéséhez jelölje be a Számlaösszeg egyeztetés jelölőnégyzetet, vagy törölje a jelölést.
    * Válassza ki, ikon jelezze-e, ha a számlaegyeztetési eltérés meghaladja a tűréshatárt. Választhat, hogy ikon, ha pozitív eltérés meghaladja a tűréshatárt, vagy ha a pozitív vagy negatív eltérés meghaladja a tűréshatára.  
    * Ha például a tűréshatára értéke 5 százalék, és a beszerzési rendelésen megadott teljes számlaösszeghez 100,00. Ezért áregyeztetési ikon jelenik meg a számlán a számla teljes összege meghaladja a 105,00. Amennyiben a Nagyobb vagy kisebb a tűréshatárnál beállítást választja, akkor is megjelenik az ikon, ha a számla összege kevesebb, mint 95,00.  
6. Adjon meg egy számot a Számlaösszeg tűréshatára százalékban mezőben.
7. Módosítsa az Ár és mennyiség egyeztetése szakasz bővítését.
    * A Soregyeztetési irányelv mezőben válassza ki az aktuális jogi személy kapcsán alapértelmezett irányelvként használandó értéket. A „Nem kötelező” beállítás azt jelenti, hogy nem szükséges a számlasorokban szereplő egyes árak, illetve a számlán feltüntetett mennyiségek összevetése a beszerzési rendelés árával, illetve a szállítólevélen feltüntetett mennyiségekkel. A „Kétirányú egyeztetés” azt jelenti, hogy szükséges a számlasorok ellenőrzése, de az kizárólag a beszerzési rendelés és a szállító számladokumentumai alapján történik. Az egyeztetési ellenőrzése nem terjed ki a termékbevételezési bizonylatra. A „Háromirányú egyeztetés” azt jelenti, hogy a rendszer a számla nettó egységárát a beszerzési rendelés nettó egységárával, a termékbevételezési mennyiséget pedig a számla szerinti mennyiséggel egyezteti.  
    * Ha Kétirányú egyeztetés vagy Háromirányú egyeztetés alapú soregyeztetési irányelvet használ, a Cikkár-tűréshatás oldalon be tud állítani az Ön vállalatára, a cikkekre és a szállítókra vonatkozó ár-tűréshatár százalékokat. A szállítói számláknak a beszerzési rendelés adataival való összehasonlítása során a a következő sorrendben keresi meg az alkalmazandó árkülönbözeti tűréshatárt.  
8. Válasszon egy lehetőséget a Soregyeztetési irányelv mezőben.
    * Ha engedélyezni szeretné egy cikk, szállító, szállító-cikk kombináció vagy beszerzési-rendelés sor eltérő szintű egyeztetését, úgy válasszon ki egy értéket az Egyeztetési irányelv felülbírálásának engedélyezése mezőben. Egy adott szállítóra, cikkre, vagy szállító-cikk kombinációra vonatkozóan az Egyeztetési irányelv oldalon tudja felülbírálni a jogi személy soregyeztetési irányelvét.  
    * A sorelemek teljes árainak, a számlákon történő egyeztetése érdekében válasszon ki egy értéket a Teljes árak egyeztetése mezőben. Az ilyen típusú egyeztetés akkor lehet hasznos, amikor a szállító több, ugyanarra a beszerzési-rendelési sorra vonatkozó számlát küld. Összehasonlíthatja az összes, a számla egyes soraiban feltüntetett nettó összegekre vonatkozó árinformációt és az összes függőben lévő, illetve korábban feladott számlasort a megfelelő beszerzési-rendelés sorral.  
9. Válasszon egy lehetőséget a Teljes árak egyeztetése mezőben.
10. Adjon meg egy számot a Teljes beszerzési ár mezőben.
11. Módosítsa a Költségek egyeztetése szakasz bővítését.
12. A tényleges költségek és a várható költségek, a beszerzési rendelés adatai alapján történő egyeztetéséhez jelölje be a Költségegyeztetés jelölőnégyzetet.
13. Zárja be a lapot.


