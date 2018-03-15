---
title: "POS-műveletek, online és offline"
description: "Ez a témakör a Microsoft Dynamics 365 for Retail pénztár (POS) műveleteinek részleteit mutatja be. Azt adja meg, ahol az alkalmazás a műveletek meghívhatók, és azt, hogy offline módban érhető el."
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: edfed83d4703c081d857faad0771dc1010be41b4
ms.openlocfilehash: edd6dd23066eca782b8fd510dabab612241e480a
ms.contentlocale: hu-hu
ms.lasthandoff: 02/13/2018

---

# <a name="pos-operations-online-and-offline"></a>POS-műveletek, online és offline

[!include[banner](includes/banner.md)]

A legtöbb felhasználó műveletek a pont (POS) értékesítési műveletek veszi figyelembe. A műveletek konfigurálása és kezelése a Microsoft Dynamics 365 for Retail háttérirodai szolgáltatásánál történik. A POS-gombrács gombjai számos művelet lehet hozzáadni. Felhasználó kiválaszthatja a gombokra kattintva hajtani a műveleteket, és a kapcsolódó feladatok végrehajtása. Egyéb műveletekhez részét képezik a fő POS alkalmazást, és előforduló vagy a gombok vagy más munkafolyamatokat, és a folyamatok részeként.

A következő táblázatban megtalálható a érhetők el a Retail Modern POS és a felhőből Dynamics 365 for Retail POS-műveletekkel kapcsolatos részletek. A táblázat azt adja meg, ahol az alkalmazás a műveletek meghívhatók, és azt, hogy a pénztár offline módjában elérhető-e.

Bizonyos műveleteket nem érhető el a Retail Modern POS vagy Dynamics 365 for Retail POS felhőből. Ezek a műveletek közül bármelyik területspecifikus szükséges további bővítmények és a konfigurációs műveletek. Más tulajdonságok és a Microsoft Dynamics AX 2012 rendszerből származó funkciók, amelyek jelenleg nem támogatott.

A következő oszlopok megadása, amennyiben a műveletek meghívhatók:

- **Gombrács** – a művelet a POS gombrácsokat, amelyek részei a POS képernyő-elrendezés gombok is hozzárendelhető.
- **Tranzakció-képernyő** – a művelet alapján a POS-tranzakciók képernyőn beállított POS-gombrács meghívhatók.
- **Tranzakció-képernyő** – a művelet alapján a POS-tranzakciók képernyőn beállított POS-gombrács meghívhatók.

| Azonosító | Művelet | Leírás | Gombrács | Tranzakciós képernyő | Üdvözlőképernyő | Offline elérhető. | Területspecifikus |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Eszköz aktiválása | Az aktuális eszköz aktiválása azáltal, hogy hitelesített felhasználók kapcsolati adatokat tartalmaznak, és rendelje hozzá az eszköz, és regisztrálja az azonosítóját. | Nincs | Nincs | Nincs | Nincs | Nincs |
| 134 | Fiók hozzáadása | A kiválasztott fiók hozzáadása egy tranzakcióhoz. Jelölje ki a fiókot a **Gomb tulajdonságai** oldalon. | Igen | Igen | Nincs | Igen | Nincs |
| 135 | Fiók hozzáadása listából | Adjon hozzá egy fiókot a tranzakcióhoz a listában történő kijelöléssel. | Igen | Igen | Igen | Igen | Nincs |
| 643 | Utalványkód hozzáadása | Kupon hozzáadása kódjának pénztárnál való megadásával. | Igen | Igen | Nincs | Igen | Nincs |
| 117 | Hűségkártya hozzáadása | Kéri a felhasználót, amely hozzáadódik az aktuális tranzakció hűségkártya számának megadása. | Igen | Igen | Nincs | Igen | Nincs |
| 136 | Sorozatszám hozzáadása | Ez a művelet lehetővé teszi, hogy a felhasználó adja meg a kijelölt termék sorozatszámát. | Igen | Igen | Nincs | Igen | Nincs |
| 1214 | Szállítási cím hozzáadása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 519 | Hozzáadás ajándékutalványhoz | Pénz feltöltése a megadott ajándékutalványra. | Igen | Igen | Nincs | Nincs | Nincs |
| 6000 | Pénzügyi regisztráció kihagyásának engedélyezése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 1212 | Banki befizetés | A bankba beküldött pénz összegének rögzítése, továbbá egyéb információk (például a banki zsák azonosítójának) megadása. | Igen | Igen | Igen | Igen | Nincs |
| 923 | Banki összegek ellenőrzése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 915 | Üres művelet | Ez a művelet olyan testreszabható gombnak felel meg, amelyet a szoftverfejlesztők a vállalkozás speciális működési igényeinek megfelelően programozás útján testreszabhatnak. | Igen | Igen | Igen | Igen | Nincs |
| 1053 | Műszakzárás számlálás nélkül | Az aktuális műszak számlálás nélkül lezárt és a felhasználó kilép. Számlálás nélkül lezárt műszak további tranzakciók le van zárva, de a fiók műveletekre, például fizetőeszköz-eltávolítási és fizetőeszköz-elszámolási folyamatban. | Igen | Igen | Igen | Nincs | Nincs |
| 310 | Összeg kiszámítása | Engedmény kiszámítására szolgáló késik, amikor az ezt a műveletet a számítás az aktuális tranzakció kezdeményezi. | Igen | Igen | Nincs | Igen | Nincs |
| 642 | Összes termék elvégzése | Az összes sor a szállítási mód beállítása **Carryout**. | Igen | Igen | Nincs | Igen\* | Nincs |
| 641 | Kiválasztott termékek elvégzése | Az összes sor a szállítási mód beállítása a kijelölt **Carryout**. | Igen | Igen | Nincs | Igen\* | Nincs |
| 1215 | Jelszó módosítása | Ez a művelet lehetővé teszi, hogy a POS felhasználó módosíthatja a jelszavát. | Igen | Igen | Igen | Nincs | Nincs |
| 123 | Mértékegység módosítása | A kijelölt sortétel mértékegysége nem módosítható. | Igen | Igen | Nincs | Igen | Nincs |
| 639 | Alapértelmezett üzletkötő törlése a tranzakcióban | Távolítsa el a jutalék értékesítési csoportja (Üzletkötő), a tranzakció nem. | Igen | Igen | Nincs | Igen | Nincs |
| 106 | Mennyiség törlése | A jelenleg kijelölt rendeléssorban szereplő mennyiségtől alaphelyzetbe **1**. | Igen | Igen | Nincs | Igen | Nincs |
| 640 | Üzletkötő törlése a sorban | Távolítsa el a kijelölt sor a jutalék értékesítési csoportjának (Értékesítés munkatárs). | Igen | Igen | Nincs | Igen | Nincs |
| 121 | Értékesítő törlése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 1055 | Műszakzárás | Az aktuális Műszakzárás, és a Z-jelentés nyomtatása a rendszerből a felhasználói bejelentkezés. | Igen | Igen | Igen | Nincs | Nincs |
| 925 | Banki csekk másolása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 620 | Vevői rendelés létrehozása | A kijelölt pénztártranzakció átalakítása vevői rendeléssé | Igen | Igen | Nincs | Igen\* | Nincs |
| 621 | Árajánlat létrehozása | A kijelölt pénztártranzakció átalakítása értékesítési árajánlattá. | Igen | Igen | Nincs | Igen\* | Nincs |
| 636 | Kiskereskedelmi tranzakció létrehozása | Ez a művelet lehetővé teszi, hogy a felhasználó szokásos értékesítési tranzakció létrehozása a POS alapértelmezés vevői rendelések létrehozása esetén. | Igen | Igen | Nincs | Igen | Nincs |
| 600 | Vevő | Adja hozzá a megadott vevőt a tranzakcióhoz. | Nincs | Nincs | Nincs | Igen | Nincs |
| 1100 | Vevői számlára történő betét | Kifizetés teljesítése a vevő számlájára. | Igen | Igen | Igen | Igen | Igen |
| 612 | Vevő hozzáadása | Ez a művelet lehetővé teszi, hogy a felhasználó új vevőrekordot hozzon létre. | Igen | Igen | Igen | Igen† | Nincs |
| 603 | Vevő törlése | A vevő eltávolítása a jelenlegi tranzakcióból. | Igen | Igen | Nincs | Igen | Nincs |
| 602 | Vevőkeresés | Ez a művelet lehetővé teszi, hogy a felhasználó keresése a vevőrekord nyissa meg a vevő lapon a POS. | Igen | Igen | Igen | Igen | Nincs |
| 609 | Vevői tranzakciók | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 917 | Adatbázis-kapcsolat állapota | Ez a művelet lehetővé teszi, hogy a felhasználó az aktuális kapcsolat beállításainak megtekintése és online és offline módok közötti váltás. | Igen | Igen | Igen | Igen | Nincs |
| 1200 | Nyitó összeg elszámolása | A pénztárfiókban a nap vagy a műszak kezdetén lévő összeg közlése. | Igen | Igen | Igen | Igen | Nincs |
| 132 | Letét felülbírálása | A vevői rendelések alapértelmezett letétjének felülbírálása. | Igen | Igen | Nincs | Igen\* | Nincs |
| 913 | Tervező mód letiltása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 912 | Tervező mód engedélyezése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 1217 | Csomagok megbontása | Készlet szétszerelése az összetevő termékeire. | Igen | Igen | Igen | Igen | Nincs |
| 624 | Visszatérítési összegek megjelenítése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 513 | Összesítés megjelenítése | A tranzakció egyenlegének megjelenítése a vevői kijelzőn. | Igen | Igen | Igen | Igen | Nincs |
| 623 | Vevő szerkesztése | Az aktuális vevő adatainak szerkesztése. | Igen | Igen | Nincs | Nincs | Nincs |
| 614 | Vevői rendelés szerkesztése | A kiválasztott rendelés visszahívása, úgy, hogy a POS módosítható. | Nincs | Nincs | Nincs | Nincs | Nincs |
| 615 | Árajánlat szerkesztése | A kiválasztott árajánlat visszahívása, úgy, hogy a POS módosítható. | Nincs | Nincs | Nincs | Nincs | Nincs |
| 518 | Kiadási számlák | A pénztárfiókból eseti kiadásokra kivett készpénz nyilvántartása. | Igen | Igen | Igen | Igen | Nincs |
| 919 | Kiterjesztett bejelentkezés | Bejelentkezési jogosultság hozzárendelése vagy eltávolítása .vonalkód beolvasásával vagy kártya lehúzásával. | Igen | Igen | Igen | Nincs | Nincs |
| 1201 | Váltópénzbetét | Ez a művelet lehetővé teszi, hogy a felhasználó további pénzt hozzáadása az aktuális fiók vagy a műszak. | Igen | Igen | Igen | Igen | Nincs |
| 1218 | Perifériás eszköz zárfeloldásának kényszerítése | A rendszer ezt a műveletet segítségével zárolásának feloldása a POS-perifériák beállításait. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 520 | Ajándékutalvány egyenlege | Az ajándékutalvány egyenlegének megjelenítése. | Igen | Igen | Nincs | Nincs | Nincs |
| 708 | Eszköz inaktiválása | Az aktuális eszköz inaktiválása, így nem használható a POS-nál jegyzék. | Nincs | Nincs | Nincs | Nincs | Nincs |
| 517 | Bevételi számlák | Az értékesítésen kívüli okból a pénztárfiókban elhelyezett összeg rögzítése. | Igen | Igen | Igen | Igen | Nincs |
| 801 | Keresés a készletben | Keresse meg az aktuális üzletre és más elérhető helyekre vonatkozó mennyiségek érhető el, a rendelésen és a Ígérethez rendelkezésre álló (ATP). | Igen | Igen | Igen | Nincs | Nincs |
| 122 | Számlamegjegyzés | Ez a művelet lehetővé teszi, hogy a felhasználó adja meg az aktuális tranzakcióval kapcsolatos megjegyzés hozzáadása. | Igen | Igen | Nincs | Igen | Nincs |
| 511 | Jóváírás kibocsátása | Kiadás jóváírás helyett visszatérítést bizonylat megadását. | Igen | Igen | Nincs | Nincs | Nincs |
| 512 | Ajándékutalvány kibocsátása | Új ajándékutalvány kiadás a megadott összeget. | Igen | Igen | Nincs | Nincs | Nincs |
| 625 | Hűségkártya kibocsátása | Hűségkártya kiállítása a vevőnek az üzlet hűségprogramjában való részvételhez. | Igen | Igen | Igen | Nincs | Nincs |
| 300 | Sorengedmény összege | A tranzakció sortételére vonatkozó engedmény összegének megadása. Ez a művelet csak olyan cikkeknél használható, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nincs | Igen | Nincs |
| 301 | Sorkedvezmény százaléka | A tranzakció sortételére vonatkozó engedmény százalékos értékének megadása. Ez a művelet csak olyan cikkeknél használható, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nincs | Igen | Nincs |
| 703 | Jegyzék zárolása | Az aktuális jegyzék zárolása, hogy ne lehessen használni, de nem jelentkezteti ki az aktuális felhasználót. | Nincs | Nincs | Nincs | Igen | Nincs |
| 701 | Kijelentkezés | Az aktuális felhasználó kijelentkeztetése a jegyzékből. | Igen | Igen | Igen | Igen | Nincs |
| 521 | Hűségkártyapontok egyenlege | A megadott hűségkártya egyenlegének megjelenítése pontokban. | Igen | Igen | Nincs | Nincs | Nincs |
| 914 | POS ablak kis méretre állítása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 1000 | Fiók kinyitása | "Nincs értékesítés" művelet végrehajtása, majd a kijelölt pénztárfiók kinyitása. | Igen | Igen | Igen | Igen | Nincs |
| 928 | Rendelésteljesítés | Ez a művelet lehetővé teszi a felhasználók számára a rendelések kiválasztását, csomagolását, szállítását vagy visszahívását az üzleti felvételre nézve. | Igen | Igen | Igen | Nincs | Nincs |
| 129 | Sorban szereplő termék adójának felülbírálása | A kijelölt sortétel adójának felülírása és más megadott adó alkalmazása. | Igen | Igen | Nincs | Igen | Nincs |
| 1.3.0 | Sorban szereplő termék adójának felülírása listából | A kijelölt sortétel adójának felülírása a felhasználó által listából kiválasztott adóval. | Igen | Igen | Nincs | Igen | Nincs |
| 127 | Tranzakció adójának felülírása | A tranzakció adójának felülírása, és más megadott adó alkalmazása. | Igen | Igen | Nincs | Igen | Nincs |
| 128 | Tranzakció adójának felülírása listából | A tranzakció adójának felülírása, és a felhasználó által listából kiválasztott adó alkalmazása. | Igen | Igen | Nincs | Igen | Nincs |
| 131 | Szállítólevél | A kiválasztott rendelés csomagjegyzékének létrehozása. | Nincs | Nincs | Nincs | Nincs | Nincs |
| 710 | Hardverállomás párosítása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 201 | Fizetés kártyával | Kártya, például hitel- vagy bankkártya elfogadása fizetésként. | Igen | Igen | Nincs | Igen | Nincs |
| 200 | Készpénzes fizetés | Készpénz elfogadása fizetéskor. | Igen | Igen | Nincs | Igen | Nincs |
| 206 | Gyors készpénzes fizetés | Hajtsa végre a tranzakciót a egyetlen mozdulattal, és elfogadja a készpénzes (pontos módosítás) esedékes összeget. | Igen | Igen | Nincs | Igen | Nincs |
| 204 | Fizetés csekkel | Csekk elfogadása fizetéskor. | Igen | Igen | Nincs | Igen | Nincs |
| 213 | Fizetés jóváírással | Az áruház által kiállított jóváírás (kupon) elfogadása. | Igen | Igen | Nincs | Nincs | Nincs |
| 203 | Fizetés valutával | Különböző pénznemek elfogadása fizetéskor. | Igen | Igen | Nincs | Igen | Nincs |
| 202 | Fizetés vevői számlával | A tranzakció ráterhelése vevőszámlára. A fizetési mód nem érvényes a vevői rendelések letéteire. | Igen | Igen | Nincs | Nincs | Nincs |
| 214 | Fizetés ajándékutalvánnyal | Az üzlet által kiállított ajándékutalvány elfogadása. | Igen | Igen | Nincs | Nincs | Nincs |
| 207 | Hűségkártkártya kifizetése | A hűségkártyás fizetés elfogadása, valamint pontok beváltása a meghatározott termékekre. | Igen | Igen | Nincs | Nincs | Nincs |
| 634 | Kifizetési előzmények | Az aktuális vevői rendelés a vevő fizetési előzményeinek megjelenítése. | Igen | Igen | Nincs | Nincs | Nincs |
| 803 | Kitárolás és bevételezés | Nyissa meg a **Kitárolás és bevételezés** lapot, amelyen megadhatja a rendelések kitárolását és fogadását az üzletben. | Igen | Igen | Igen | Nincs | Nincs |
| 632 | Minden termék felvétele | Állítsa a teljesítési módszert **Átvétel az üzletben** értékre minden sorhoz. | Igen | Igen | Nincs | Igen\* | Nincs |
| 631 | Kijelölt termékek felvétele | Állítsa a teljesítési módszert **Átvétel az üzletben** értékre a kijelölt sorokhoz. | Igen | Igen | Nincs | Igen\* | Nincs |
| 400 | Előugró menü | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 101 | Árkeresés | Ez a művelet lehetővé teszi, hogy a felhasználó kikeresse egy adott termék árát. | Igen | Igen | Igen | Igen | Nincs |
| 104 | Ár felülbírálása | Termék árának felülbírálata, amennyiben a termék úgy van beállítva, hogy ez lehetséges. | Igen | Igen | Nincs | Igen | Nincs |
| 1058 | Pénzügyi X nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 1059 | Pénzügyi Z nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 927 | Cikkcímke nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 926 | Árucímke nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 1056 | X nyomtatás | X jelentés nyomtatása az aktuális műszakhoz. | Igen | Igen | Igen | Nincs | Nincs |
| 103 | Megjegyzés a termékhez | Megjegyzés hozzáadása a tranzakció kiválasztott sortételéhez. | Igen | Igen | Nincs | Igen | Nincs |
| 100 | Termékértékesítés | Meghatározott termék hozzáadása a tranzakcióhoz. | Igen | Igen | Igen | Igen | Nincs |
| 108 | Termékkeresés | Ez a művelet lehetővé teszi, hogy a felhasználó termékre keressen úgy, hogy hozzá navigál a pénztár keresőoldalán. | Igen | Igen | Igen | Igen | Nincs |
| 633 | Árajánlat lejárati dátuma | Ez a művelet lehetővé teszi, hogy a felhasználó megtekintse vagy módosítsa az értékesítési ajánlat lejárati dátumát. | Igen | Igen | Nincs | Igen\* | Nincs |
| 627 | Újraszámítás | Összes vevői rendeléssor és adók újraszámítása az aktuális konfiguráció alapján. | Igen | Igen | Nincs | Igen\* | Nincs |
| 515 | Rendelés visszahívása | Ez a művelet lehetővé teszi, hogy a felhasználó rákeressen a vevői rendelésekre és értékesítési ajánlatokra, és visszahívja őket. | Igen | Igen | Igen | Nincs | Nincs |
| 504 | Tranzakció visszahívása | Ez a művelet lehetővé teszi, hogy a felhasználó visszahívjon egy korábban felfüggesztett tranzakciót a jelenlegi üzletből. | Igen | Igen | Nincs | Igen‡ | Nincs |
| 305 | Hűségpontok beváltása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 635 | Szállítási költségek visszatérítése | Ez a művelet lehetővé teszi, hogy a felhasználó visszatérítse a szállítási költségeket egy érvénytelenített rendelésen. | Nincs | Nincs | Nincs | Nincs | Nincs |
| 644 | Utalványkód eltávolítása | Arra kéri a felhasználót, hogy távolítsa el a kuponokat úgy, hogy kiválasztja őket egy, a tranzakcióval jelenleg társított kuponlistából. | Igen | Igen | Nincs | Igen | Nincs |
| 1057 | Z újranyomtatás | Az előző műszak vagy a kijelölt műszak Z-jelentésének kinyomtatása. | Igen | Igen | Igen | Nincs | Nincs |
| 1216 | Adja meg az új jelszót. | Ez a művelet lehetővé teszi, hogy a jelszó-visszaállítási engedéllyel rendelkező felhasználó visszaállíthatja egy alkalmazott jelszavát egy ideiglenes jelszó használatával. | Igen | Igen | Igen | Nincs | Nincs |
| 109 | Visszaküldött termék | Egyedi termékek visszavételének végrehajtása. A következő leolvasott termék visszaküldött termékként jelenik meg, negatív mennyiséggel és árral. | Igen | Igen | Nincs | Igen | Nincs |
| 114 | Visszáru-tranzakció | Korábbi tranzakció visszahívása bizonylatszám alapján egy vagy több termék visszaküldéséhez. | Igen | Igen | Igen | Igen§ | Nincs |
| 1211 | Széfes befizetés | Széfes befizetés, mellyel a pénz áthelyezhető a pénztárból a széfbe. | Igen | Igen | Igen | Igen | Nincs |
| 516 | Értékesítési számla | Ez a művelet lehetővé teszi, hogy a vevő felé a kiválasztott értékesítési számla kifizetéseket. | Igen | Igen | Nincs | Nincs | Nincs |
| 502 | Értékesítő | Ez a művelet lehetővé teszi, hogy a felhasználó beállítsa az **Értékesítési átvevő** értéket az ügyfélrendelésekre vonatkozó értékesítési rendelésen a pénztárnál. | Igen | Igen | Nincs | Igen\* | Nincs |
| 2000 | Ütemezéskezelés | Ez a művelet segítségével a felhasználók létrehozása, módosítása vagy alkalmazott ütemezések megtekintése. | Igen | Igen | Igen | Nincs | Nincs |
| 2001 | Kérelmek ütemezése | Ez a művelet lehetővé teszi, hogy a felhasználó kérés ideje ki, műszakok felcserélése vagy más alkalmazottak ajánlja fel a műszakok. | Igen | Igen | Igen | Nincs | Nincs |
| 622 | Rendelések keresése | Ez a művelet segítségével a felhasználók előre POS cikk, vevő vagy kategória szerinti keresés gombra. | Igen | Igen | Igen | Igen | Nincs |
| 1213 | Szállítási cím keresése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 709 | Hardverállomás kiválasztása | Ez a művelet lehetővé teszi, hogy a felhasználó jelölje ki azt a rendelkezésre álló állomás listájában hardverállomás. | Igen | Igen | Igen | Igen | Nincs |
| 637 | Alapértelmezett üzletkötő beállítása a tranzakcióban | Ez a művelet lehetővé teszi, hogy a felhasználó alapértelmezett üzletkötő később hozzáadott sorok megjelölése a támogatható az értékesítési jutalékcsoportok (eladás kereskedőt) egyik. | Igen | Igen | Nincs | Igen | Nincs |
| 105 | Mennyiség beállítása | A tranzakcióban szereplő sortétel mennyiségének módosítása. | Igen | Igen | Nincs | Igen | Nincs |
| 638 | Üzletkötő beállítása a sorban | Ez a művelet lehetővé teszi, hogy a felhasználó alapértelmezett üzletkötő később hozzáadott sorok megjelölése a támogatható az értékesítési jutalékcsoportok a jelenleg kiválasztott sornál. | Igen | Igen | Nincs | Igen | Nincs |
| 630 | Az összes termék szállítása | A teljesítési mód beállításához **szállítási** sor összes cikkhez. | Igen | Igen | Nincs | Igen\* | Nincs |
| 629 | Kijelölt termékek szállítása | Az összes sor a szállítási mód beállítása a kijelölt **Szállítás**. | Igen | Igen | Nincs | Igen\* | Nincs |
| 918 | Számlálás nélkül lezárt műszakok megjelenítése | A számlálás nélkül lezárt műszakok listájának megjelenítése. | Igen | Igen | Igen | Nincs | Nincs |
| 115 | Napló megjelenítése | Az üzlet naplójának megjelenítése. Tranzakciók megjelenítése, és a bevételek ajándékutalvány újranyomtatása és visszaküldés visszahívása. | Igen | Igen | Igen | Igen\*\* | Nincs |
| 802 | Készletszámlálás | Ez a művelet lehetővé teszi, hogy a felhasználó létrehozása vagy módosítása a tényleges készlet vagy ciklikus leltározási számlálási naplókat. | Igen | Igen | Igen | Nincs | Nincs |
| 401 | Almenü | Ezt a műveletet a felhasználó egy másik csatolt gombrács vesz igénybe. | Igen | Igen | Igen | Igen | Nincs |
| 1054 | Műszak felfüggesztése | Az aktuális műszak felfüggesztése, úgy, hogy az aktuális jegyzék másik műszak aktiválható. | Igen | Igen | Igen | Nincs | Nincs |
| 503 | Tranzakció felfüggesztése | Az aktuális értékesítési tranzakció felfüggesztése, így később hívható vissza az üzletben. | Igen | Igen | Nincs | Igen‡ | Nincs |
| 1004 | Feladatrögzítő | Nyissa meg a műveleteket lépésről lépésre ismertető lépéseket rögzíti a POS Feladatrögzítő. | Nincs | Nincs | Nincs | Igen | Nincs |
| 1052 | Fizetőeszköz-elszámolás | Ez a művelet lehetővé teszi, hogy a felhasználó adja meg az összeget a fiókban a leszámlált fizetési módokhoz. | Igen | Igen | Igen | Igen | Nincs |
| 1210 | Fizetőeszköz kivétele | Ez a művelet lehetővé teszi, hogy a felhasználó pénzt vegyen el az aktuális fióktól vagy műszaktól. | Igen | Igen | Igen | Igen | Nincs |
| 920 | Blokkolóóra | Ez a művelet segítségével a felhasználók Lyukasztás és lyukasztás műszakok és szüneteket. | Igen | Igen | Igen | Nincs | Nincs |
| 302 | Teljes engedmény összege | Az engedmény összegének megadása. Ez a művelet csak olyan cikkeknél érvényes, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nincs | Igen | Nincs |
| 303 | Teljes engedmény (százalék) | Az engedmény százalékának megadása. Ez a művelet csak olyan cikkeknél érvényes, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nincs | Igen | Nincs |
| 501 | Tranzakció megjegyzése | Megjegyzés hozzáfűzése a jelenlegi tranzakcióhoz. | Igen | Igen | Nincs | Igen | Nincs |
| 922 | Termék részleteinek megtekintése | A kijelölt sorcikk termék Részletek lap megnyitása. | Igen | Igen | Nincs | Igen | Nincs |
| 1003 | Jelentések megtekintése | Az aktuális felhasználó beállított-jelentések megjelenítése | Igen | Igen | Igen | Nincs | Nincs |
| 921 | Blokkolóóra bejegyzéseinek megtekintése | Blokkolóóra minden üzletben dolgozóhoz tartozó bejegyzéseinek megjelenítése. | Igen | Igen | Igen | Nincs | Nincs |
| 211 | Fizetés érvénytelenítése | A tranzakcióból a jelenleg kiválasztott fizetési sor érvénytelenítését. | Igen | Igen | Nincs | Igen | Nincs |
| 102 | Érvénytelen termék | A tranzakcióból a jelenleg kiválasztott sor érvénytelenítését. | Igen | Igen | Nincs | Igen | Nincs |
| 500 | Tranzakció érvénytelenítése | Az aktuális tranzakció érvénytelenítése. | Igen | Igen | Nincs | Igen | Nincs |
| 916 | Windows folyamatkövető alaprendszer | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nincs |
| 924 | Bankkártyák X-jelentése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |

\* A művelet csak akkor, amikor a vevői rendelés vagy értékesítési ajánlat létrehozása folyamatban van, az offline módban érhető el, de csak akkor, ha a vevői rendelések és értékesítési ajánlatok létrehozása offline helyesek-e a POS funkcióprofil. A művelet nem hajtható végre, rendelések létrehozásakor a Real-time Service segítségével, vagy ha a rendelések visszahívásához vagy szerkeszteni.

† A művelet csak akkor, amikor a POS helyesek-e a POS funkcióprofil vevők nélküli létrehozásának engedélyezése a kapcsolat nélküli módban hajtható végre.

A felfüggesztett tranzakciók ‡ a POS offline állapotban, ha csak az aktuális jegyzék offline adatbázis is hívható. A felhasználók nem felfüggesztése és a tranzakció visszahívása jegyzékek között.

A felfüggesztett tranzakciók ‡ a POS offline állapotban a jelenlegi offline adatbázisban, ha csak az aktuális jegyzék offline adatbázis is hívható.

\*\* A felfüggesztett tranzakciók ‡ a POS offline állapotban a jelenlegi offline adatbázisban, ha csak az aktuális jegyzék offline adatbázis látható a naplóban.

