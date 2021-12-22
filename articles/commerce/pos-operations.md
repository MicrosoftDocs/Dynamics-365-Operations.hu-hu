---
title: Online és offline pénztár (POS) műveletek
description: Ez a témakör ismerteti a pénztár (POS) műveleteit Dynamics 365 Commerce alkalmazásban. Azt adja meg, ahol az alkalmazás a műveletek meghívhatók, és azt, hogy offline módban érhető el.
author: jblucher
ms.date: 11/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 88daca466e0e01bf3870b6eeee0628e0c159fea3
ms.sourcegitcommit: 971456c197820421f108ad7345001cc1b6c99949
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2021
ms.locfileid: "7875477"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Online és offline pénztár (POS) műveletek

[!include [banner](includes/banner.md)]

A felhasználók legtöbb művelete műveletnek számít a pénztárnál. Műveletek konfigurálása és kezelése a Dynamics 365 Commerce háttérirodában történik. A POS-gombrács gombjai számos művelet lehet hozzáadni. Felhasználó kiválaszthatja a gombokra kattintva hajtani a műveleteket, és a kapcsolódó feladatok végrehajtása. Egyéb műveletekhez részét képezik a fő POS alkalmazást, és előforduló vagy a gombok vagy más munkafolyamatokat, és a folyamatok részeként.

A következő táblázatban a Modern POS és a Cloud POS rendszerekben rendelkezésre álló műveleteket találja. A táblázat azt adja meg, ahol az alkalmazás a műveletek meghívhatók, és azt, hogy a pénztár offline módjában elérhető-e.

Bizonyos műveleteket jelenleg nem érhetők el a Modern POS vagy Cloud POS rendszerben. Ezek a műveletek közül bármelyik területspecifikus szükséges további bővítmények és a konfigurációs műveletek. Más tulajdonságok és a Microsoft Dynamics AX 2012 rendszerből származó funkciók, amelyek jelenleg nem támogatott.

A következő oszlopok megadása, amennyiben a műveletek meghívhatók:

- **Gombrács** – a művelet a POS gombrácsokat, amelyek részei a POS képernyő-elrendezés gombok is hozzárendelhető.
- **Tranzakció-képernyő** – a művelet alapján a POS-tranzakciók képernyőn beállított POS-gombrács meghívhatók.
- **Tranzakció-képernyő** – a művelet alapján a POS-tranzakciók képernyőn beállított POS-gombrács meghívhatók.

> [!NOTE]
> Az alább felsorolt műveletek a legújabb Commerce rendszerre vonatkoznak. Bizonyos műveletek megváltozhattak, vagy nem állnak rendelkezésre a termék korábbi verzióiban.

| Azonosító | Művelet | Leírás | Gombrács | Tranzakciós képernyő | Üdvözlőképernyő | Offline elérhető. | Területspecifikus |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Eszköz aktiválása | Az aktuális eszköz aktiválása azáltal, hogy hitelesített felhasználók kapcsolati adatokat tartalmaznak, és rendelje hozzá az eszköz, és regisztrálja az azonosítóját. | Nem | Nem | Nem | Nem | Nem |
| 134 | Fiók hozzáadása | A kiválasztott fiók hozzáadása egy tranzakcióhoz. Jelölje ki a fiókot a **Gomb tulajdonságai** oldalon. | Igen | Igen | Nem | Igen | Nem |
| 135 | Fiók hozzáadása listából | Adjon hozzá egy fiókot a tranzakcióhoz a listában történő kijelöléssel. | Igen | Igen | Igen | Igen | Nem |
| 137 | Egy fiók hozzáadása vevőhöz | Adjon hozzá fiókot a vevőhöz a **Vevőadatok** oldalon. | Nem | Nem | Nem | Igen | Nem |
| 138 | Fiók eltávolítása az ügyfélről | Távolítsa el a fiókot a vevőtől a **Vevőadatok** oldalon. | Nem | Nem | Nem | Igen | Nem |
| 643 | Utalványkód hozzáadása | Kupon hozzáadása kódjának pénztárnál való megadásával. | Igen | Igen | Nem | Igen | Nem |
| 141 | Fejlécköltségek hozzáadása | Vegyes költség hozzáadása a rendelés fejlécéhez. | Igen | Igen | Nem | Nem| Nem |
| 141 | Sorköltségek hozzáadása | Vegyes költség hozzáadása egy kijelölt értékesítési sorhoz. | Igen | Igen | Nem | Nem| Nem |
| 117 | Hűségkártya hozzáadása | Kéri a felhasználót, amely hozzáadódik az aktuális tranzakció hűségkártya számának megadása. | Igen | Igen | Nem | Igen | Nem |
| 136 | Sorozatszám hozzáadása | Ez a művelet lehetővé teszi, hogy a felhasználó adja meg a kijelölt termék sorozatszámát. | Igen | Igen | Nem | Igen | Nem |
| 1214 | Szállítási cím hozzáadása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 519 | Hozzáadás ajándékutalványhoz | Pénz feltöltése a megadott ajándékutalványra. | Igen | Igen | Nem | Nem | Nem |
| 6000 | Pénzügyi regisztráció kihagyásának engedélyezése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 1212 | Banki befizetés | A bankba beküldött pénz összegének rögzítése, továbbá egyéb információk (például a banki zsák azonosítójának) megadása. | Igen | Igen | Igen | Igen | Nem |
| 923 | Banki összegek ellenőrzése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 915 | Üres művelet | Ez a művelet olyan testreszabható gombnak felel meg, amelyet a szoftverfejlesztők a vállalkozás speciális működési igényeinek megfelelően programozás útján testreszabhatnak. | Igen | Igen | Igen | Igen | Nem |
| 1053 | Műszakzárás számlálás nélkül | Az aktuális műszak számlálás nélkül lezárt és a felhasználó kilép. Számlálás nélkül lezárt műszak további tranzakciók le van zárva, de a fiók műveletekre, például fizetőeszköz-eltávolítási és fizetőeszköz-elszámolási folyamatban. | Igen | Igen | Igen | Nem | Nem |
| 310 | Összeg kiszámítása | Engedmény kiszámítására szolgáló késik, amikor az ezt a műveletet a számítás az aktuális tranzakció kezdeményezi. | Igen | Igen | Nem | Igen | Nem |
| 642 | Összes termék elvégzése | Az összes sor a szállítási mód beállítása **Carryout**. | Igen | Igen | Nem | Igen\* | Nem |
| 641 | Kiválasztott termékek elvégzése | Az összes sor a szállítási mód beállítása a kijelölt **Carryout**. | Igen | Igen | Nem | Igen\* | Nem |
| 647 | Szállítási mód módosítása | Szállítási mód módosítása az előre konfigurált szállítási értékesítési sorokhoz. | Igen | Igen | Nem | Nem| Nem |
| 1215 | Jelszó módosítása | Ez a művelet lehetővé teszi, hogy a POS felhasználó módosítsa a jelszavát. | Igen | Igen | Igen | Nem | Nem |
| 123 | Mértékegység módosítása | A kijelölt sortétel mértékegysége nem módosítható. | Igen | Igen | Nem | Igen | Nem |
| 639 | Alapértelmezett üzletkötő törlése a tranzakcióban | Távolítsa el a jutalék értékesítési csoportja (Üzletkötő), a tranzakció nem. | Igen | Igen | Nem | Igen | Nem |
| 106 | Mennyiség törlése | A jelenleg kijelölt rendeléssorban szereplő mennyiségtől alaphelyzetbe **1**. | Igen | Igen | Nem | Igen | Nem |
| 640 | Üzletkötő törlése a sorban | Távolítsa el a kijelölt sor a jutalék értékesítési csoportjának (Értékesítés munkatárs). | Igen | Igen | Nem | Igen | Nem |
| 121 | Értékesítő törlése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 1055 | Műszakzárás | Az aktuális Műszakzárás, és a Z-jelentés nyomtatása a rendszerből a felhasználói bejelentkezés. | Igen | Igen | Igen | Nem | Nem |
| 139 | Tranzakció lezárása | Megkéri a felhasználót, hogy válasszon fizetési módot | Igen | Igen | Nem | Igen | Nem |
| 925 | Banki csekk másolása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 620 | Vevői rendelés létrehozása | A kijelölt pénztártranzakció átalakítása vevői rendeléssé | Igen | Igen | Nem | Igen\* | Nem |
| 621 | Árajánlat létrehozása | A kijelölt pénztártranzakció átalakítása értékesítési árajánlattá. | Igen | Igen | Nem | Igen\* | Nem |
| 636 | Kiskereskedelmi tranzakció létrehozása | Hozzon létre egy szokásos értékesítési tranzakciót, ha a POS alapértelmezett viselkedése a vevői rendelések létrehozása. | Igen | Igen | Nem | Igen | Nem |
| 600 | Vevő | Adja hozzá a megadott vevőt a tranzakcióhoz. | Nem | Nem | Nem | Igen | Nem |
| 1100 | Vevői számlára történő betét | Kifizetés teljesítése a vevő számlájára. | Igen | Igen | Igen | Igen | Igen |
| 612 | Vevő hozzáadása | Új vevőrekord létrehozása | Igen | Igen | Igen | Igen† | Nem |
| 603 | Vevő törlése | A vevő eltávolítása a jelenlegi tranzakcióból. | Igen | Igen | Nem | Igen | Nem |
| 602 | Ügyfélkeresés | Vevőrekord keresése a POS vevőkereső oldalára való navigálásval. | Igen | Igen | Igen | Igen | Nem |
| 609 | Vevői tranzakciók | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 917 | Adatbázis-kapcsolat állapota | Az aktuális kapcsolati beállítások megtekintése, valamint váltás az online és offline üzemmódok között. | Igen | Igen | Igen | Igen | Nem |
| 1200 | Nyitó összeg elszámolása | A pénztárfiókban a nap vagy a műszak kezdetén lévő összeg közlése. | Igen | Igen | Igen | Igen | Nem |
| 132 | Letét felülbírálása | A vevői rendelések alapértelmezett letétjének felülbírálása. | Igen | Igen | Nem | Igen\* | Nem |
| 913 | Tervező mód letiltása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 912 | Tervező mód engedélyezése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 1217 | Csomagok megbontása | Készlet szétszerelése az összetevő termékeire. | Igen | Igen | Igen | Igen | Nem |
| 624 | Visszatérítési összegek megjelenítése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 513 | Összesítés megjelenítése | A tranzakció egyenlegének megjelenítése a vevői kijelzőn. | Igen | Igen | Igen | Igen | Nem |
| 623 | Vevő szerkesztése | Az aktuális vevő adatainak szerkesztése. | Igen | Igen | Nem | Nem | Nem |
| 614 | Vevői rendelés szerkesztése | A kiválasztott rendelés visszahívása, úgy, hogy a POS módosítható. | Nem | Nem | Nem | Nem | Nem |
| 615 | Árajánlat szerkesztése | A kiválasztott árajánlat visszahívása, úgy, hogy a POS módosítható. | Nem | Nem | Nem | Nem | Nem |
| 518 | Kiadási számlák | A pénztárfiókból eseti kiadásokra kivett készpénz nyilvántartása. | Igen | Igen | Igen | Igen | Nem |
| 919 | Kiterjesztett bejelentkezés | Bejelentkezési jogosultság hozzárendelése vagy eltávolítása .vonalkód beolvasásával vagy kártya lehúzásával. | Igen | Igen | Igen | Igen | Nem |
| 1201 | Váltópénzbetét | Adjon hozzá további pénzt az aktuális fiókhoz vagy műszakhoz. | Igen | Igen | Igen | Igen | Nem |
| 1218 | Perifériás eszköz zárfeloldásának kényszerítése | A rendszer ezt a műveletet segítségével zárolásának feloldása a POS-perifériák beállításait. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 520 | Ajándékutalvány egyenlege | Az ajándékutalvány egyenlegének megjelenítése. | Igen | Igen | Nem | Nem | Nem |
| 708 | Eszköz inaktiválása | Az aktuális eszköz inaktiválása, így nem használható a POS-nál jegyzék. | Nem | Nem | Nem | Nem | Nem |
| 804 | Bejövő művelet | A bejövő üzleti készletkezelési szolgáltatások elérése. | Igen | Nem | Igen | Nem| Nem |
| 517 | Bevételi számlák | Az értékesítésen kívüli okból a pénztárfiókban elhelyezett összeg rögzítése. | Igen | Igen | Igen | Igen | Nem |
| 801 | Keresés a készletben | Keresse meg az aktuális üzletre és más elérhető helyekre vonatkozó mennyiségek érhető el, a rendelésen és a Ígérethez rendelkezésre álló (ATP). | Igen | Igen | Igen | Nem | Nem |
| 122 | Számlamegjegyzés | Az aktuális tranzakcióval kapcsolatos megjegyzés beírva. | Igen | Igen | Nem | Igen | Nem |
| 511 | Jóváírás kibocsátása | Kiadás jóváírás helyett visszatérítést bizonylat megadását. | Igen | Igen | Nem | Nem | Nem |
| 512 | Ajándékutalvány kibocsátása | Új ajándékutalvány kiadás a megadott összeget. | Igen | Igen | Nem | Nem | Nem |
| 625 | Hűségkártya kibocsátása | Hűségkártya kiállítása a vevőnek az üzlet hűségprogramjában való részvételhez. | Igen | Igen | Igen | Nem | Nem |
| 300 | Sorengedmény összege | A tranzakció sortételére vonatkozó engedmény összegének megadása. Ez a művelet csak olyan cikkeknél használható, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nem | Igen | Nem |
| 301 | Sorkedvezmény százaléka | A tranzakció sortételére vonatkozó engedmény százalékos értékének megadása. Ez a művelet csak olyan cikkeknél használható, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nem | Igen | Nem |
| 703 | Jegyzék zárolása | Az aktuális jegyzék zárolása, hogy ne lehessen használni, de nem jelentkezteti ki az aktuális felhasználót. | Nem | Nem | Nem | Igen | Nem |
| 701 | Kijelentkezés | Az aktuális felhasználó kijelentkeztetése a jegyzékből. | Igen | Igen | Igen | Igen | Nem |
| 521 | Hűségkártyapontok egyenlege | A megadott hűségkártya egyenlegének megjelenítése pontokban. | Igen | Igen | Nem | Nem | Nem |
| 142 | Költségek kezelése | A tranzakcióra alkalmazott vegyes költségek megtekintése és kezelése. | Igen | Igen | Nem | Nem| Nem |
| 918 | Műszakok kezelése | Az aktív, felfüggesztett és számlálás nélkül lezárt műszakok listájának megjelenítése. | Igen | Igen | Igen | Nem | Nem |
| 914 | POS ablak kis méretre állítása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 1000 | Fiók kinyitása | "Nincs értékesítés" művelet végrehajtása, majd a kijelölt pénztárfiók kinyitása. | Igen | Igen | Igen | Igen | Nem |
| 928 | Rendelésteljesítés | Ez a művelet lehetővé teszi a felhasználók számára a rendelések kiválasztását, csomagolását, szállítását vagy visszahívását az üzleti felvételre nézve. | Igen | Igen | Igen | Nem | Nem |
| 805 | Kimenő művelet | A kimenő átmozgatási rendelések szállítmányainak kezelésére szolgáló elérési lehetőségek. | Igen | Nem | Igen | Nem| Nem |
| 129 | Sorban szereplő termék adójának felülbírálása | A kijelölt sortétel adójának felülírása és más megadott adó alkalmazása. | Igen | Igen | Nem | Igen | Nem |
| 1.3.0 | Sorban szereplő termék adójának felülírása listából | A kijelölt sortétel adójának felülírása a felhasználó által listából kiválasztott adóval. | Igen | Igen | Nem | Igen | Nem |
| 127 | Tranzakció adójának felülírása | A tranzakció adójának felülírása, és más megadott adó alkalmazása. | Igen | Igen | Nem | Igen | Nem |
| 128 | Tranzakció adójának felülírása listából | A tranzakció adójának felülírása, és a felhasználó által listából kiválasztott adó alkalmazása. | Igen | Igen | Nem | Igen | Nem |
| 131 | Szállítólevél | A kiválasztott rendelés csomagjegyzékének létrehozása. | Nem | Nem | Nem | Nem | Nem |
| 710 | Hardverállomás párosítása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 201 | Fizetés kártyával | Kártya, például hitel- vagy bankkártya elfogadása fizetésként. | Igen | Igen | Nem | Igen | Nem |
| 200 | Készpénzes fizetés | Készpénz elfogadása fizetéskor. | Igen | Igen | Nem | Igen | Nem |
| 206 | Gyors készpénzes fizetés | Hajtsa végre a tranzakciót a egyetlen mozdulattal, és elfogadja a készpénzes (pontos módosítás) esedékes összeget. | Igen | Igen | Nem | Igen | Nem |
| 204 | Fizetés csekkel | Csekk elfogadása fizetéskor. | Igen | Igen | Nem | Igen | Nem |
| 213 | Fizetés jóváírással | Az áruház által kiállított jóváírás (kupon) elfogadása. | Igen | Igen | Nem | Nem | Nem |
| 203 | Fizetés valutával | Különböző pénznemek elfogadása fizetéskor. | Igen | Igen | Nem | Igen | Nem |
| 202 | Fizetés vevői számlával | A tranzakció ráterhelése vevőszámlára. A fizetési mód nem érvényes a vevői rendelések letéteire. | Igen | Igen | Nem | Nem | Nem |
| 214 | Fizetés ajándékutalvánnyal | Az üzlet által kiállított ajándékutalvány elfogadása. | Igen | Igen | Nem | Nem | Nem |
| 207 | Hűségkártkártya kifizetése | A hűségkártyás fizetés elfogadása, valamint pontok beváltása a meghatározott termékekre. | Igen | Igen | Nem | Nem | Nem |
| 634 | Kifizetési előzmények | Az aktuális vevői rendelés a vevő fizetési előzményeinek megjelenítése. | Igen | Igen | Nem | Nem | Nem |
| 803 | Kitárolás és bevételezés | Nyissa meg a **Kitárolás és bevételezés** lapot, amelyen megadhatja a rendelések kitárolását és fogadását az üzletben. | Igen | Igen | Igen | Nem | Nem |
| 632 | Minden termék felvétele | Állítsa a teljesítési módszert **Átvétel az üzletben** értékre minden sorhoz. | Igen | Igen | Nem | Igen\* | Nem |
| 631 | Kijelölt termékek felvétele | Állítsa a teljesítési módszert **Átvétel az üzletben** értékre a kijelölt sorokhoz. | Igen | Igen | Nem | Igen\* | Nem |
| 400 | Előugró menü | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 101 | Árkeresés | Ez a művelet lehetővé teszi, hogy a felhasználó kikeresse egy adott termék árát. | Igen | Igen | Igen | Igen | Nem |
| 104 | Ár felülbírálása | Termék árának felülbírálata, amennyiben a termék úgy van beállítva, hogy ez lehetséges. | Igen | Igen | Nem | Igen | Nem |
| 1058 | Pénzügyi X nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 1059 | Pénzügyi Z nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 927 | Cikkcímke nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 926 | Árucímke nyomtatása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 1056 | X nyomtatás | X jelentés nyomtatása az aktuális műszakhoz. | Igen | Igen | Igen | Nem | Nem |
| 103 | Megjegyzés a termékhez | Megjegyzés hozzáadása a tranzakció kiválasztott sortételéhez. | Igen | Igen | Nem | Igen | Nem |
| 100 | Termékértékesítés | Meghatározott termék hozzáadása a tranzakcióhoz. | Igen | Igen | Igen | Igen | Nem |
| 108 | Termékkeresés | Termék keresése a POS termékkereső oldalára való navigálásval. | Igen | Igen | Igen | Igen | Nem |
| 633 | Árajánlat lejárati dátuma | Az értékesítési ajánlat lejárati dátumának megtekintése vagy módosítása. | Igen | Igen | Nem | Igen\* | Nem |
| 627 | Újraszámítás | Összes vevői rendeléssor és adók újraszámítása az aktuális konfiguráció alapján. | Igen | Igen | Nem | Igen\* | Nem |
| 143 | Költségek újraszámítása | A rendelésre alkalmazott automatikus költségek újraszámítása. | Igen | Igen | Nem | Nem| Nem |
| 515 | Rendelés visszahívása | Vevői rendelések és értékesítési ajánlatok keresése és visszahívása. | Igen | Igen | Igen | Nem | Nem |
| 504 | Tranzakció visszahívása | Egy korábban felfüggesztett tranzakció visszahívása az aktuális üzletből. | Igen | Igen | Nem | Igen‡ | Nem |
| 305 | Hűségpontok beváltása | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 635 | Szállítási költségek visszatérítése | Az érvénytelenített rendelés szállítási költségeinek visszatérítése | Nem | Nem | Nem | Nem | Nem |
| 644 | Utalványkód eltávolítása | Arra kéri a felhasználót, hogy távolítsa el a kuponokat úgy, hogy kiválasztja őket egy, a tranzakcióval jelenleg társított kuponlistából. | Igen | Igen | Nem | Igen | Nem |
| 1057 | Z újranyomtatás | Az előző műszak vagy a kijelölt műszak Z-jelentésének kinyomtatása. | Igen | Igen | Igen | Nem | Nem |
| 1216 | Adja meg az új jelszót. | Ez a művelet lehetővé teszi, hogy a jelszó-visszaállítási engedéllyel rendelkező felhasználó visszaállíthatja egy alkalmazott jelszavát egy ideiglenes jelszó használatával. | Igen | Igen | Igen | Nem | Nem |
| 1219 | URl megnyitása a pénztárban | Nyisson meg egy rendszergazda által konfigurált URL-címet a POS-terminálon. | Igen | Igen | Igen | Igen | Nem |
| 109 | Visszaküldött termék | Egyedi termékek visszavételének végrehajtása. A következő leolvasott termék visszaküldött termékként jelenik meg, negatív mennyiséggel és árral. | Igen | Igen | Nem | Igen | Nem |
| 114 | Visszáru-tranzakció | Korábbi tranzakció visszahívása bizonylatszám alapján egy vagy több termék visszaküldéséhez. | Igen | Igen | Igen | Igen§ | Nem |
| 1211 | Széfes befizetés | Széfes befizetés, mellyel a pénz áthelyezhető a pénztárból a széfbe. | Igen | Igen | Igen | Igen | Nem |
| 516 | Értékesítési számla | Ez a művelet lehetővé teszi, hogy a vevő felé a kiválasztott értékesítési számla kifizetéseket. | Igen | Igen | Nem | Nem | Nem |
| 502 | Értékesítő | A POS-ban vevői rendelések értékesítési rendelésében az **Értékesítés** át vevője értékének beállítása. | Igen | Igen | Nem | Igen\* | Nem |
| 2000 | Ütemezéskezelés | Ez a művelet még nem támogatott. | Igen | Igen | Igen | Nem | Nem |
| 2001 | Kérelmek ütemezése | Ez a művelet még nem támogatott. | Igen | Igen | Igen | Nem | Nem |
| 622 | Rendelések keresése | Ez a művelet segítségével a felhasználók előre POS cikk, vevő vagy kategória szerinti keresés gombra. | Igen | Igen | Igen | Igen | Nem |
| 1213 | Szállítási cím keresése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 709 | Hardware station kiválasztása | Hardverállomás kiválasztása a rendelkezésre álló hardverhibák listájáról. | Igen | Igen | Igen | Igen | Nem |
| 637 | Alapértelmezett üzletkötő beállítása a tranzakcióban | Válassza ki a később hozzáadott sorok alapértelmezett üzletkötőiként a megfelelő jutalékos értékesítési csoportok (üzletkötők) valamelyikét. | Igen | Igen | Nem | Igen | Nem |
| 105 | Mennyiség beállítása | A tranzakcióban szereplő sortétel mennyiségének módosítása. | Igen | Igen | Nem | Igen | Nem |
| 638 | Üzletkötő beállítása a sorban | Az aktuálisan kiválasztott sorra vonatkozó jutalékos értékesítési csoportok (üzletkötők) egyikének kiválasztása. | Igen | Igen | Nem | Igen | Nem |
| 630 | Az összes termék szállítása | A teljesítési mód beállításához **szállítási** sor összes cikkhez. | Igen | Igen | Nem | Igen\* | Nem |
| 629 | Kijelölt termékek szállítása | Az összes sor a szállítási mód beállítása a kijelölt **Szállítás**. | Igen | Igen | Nem | Igen\* | Nem |
| 115 | Napló megjelenítése | Az üzlet naplójának megjelenítése. Tranzakciók megjelenítése, és a bevételek ajándékutalvány újranyomtatása és visszaküldés visszahívása. | Igen | Igen | Igen | Igen\*\* | Nem |
| 802 | Leltár | Leltárnaplók létrehozása vagy módosítása tényleges készlethez vagy ciklikus leltározáshoz. | Igen | Igen | Igen | Nem | Nem |
| 401 | Almenü | Ezt a műveletet a felhasználó egy másik csatolt gombrács vesz igénybe. | Igen | Igen | Igen | Igen | Nem |
| 1054 | Műszak felfüggesztése | Az aktuális műszak felfüggesztése, úgy, hogy az aktuális jegyzék másik műszak aktiválható. | Igen | Igen | Igen | Nem | Nem |
| 503 | Tranzakció felfüggesztése | Az aktuális értékesítési tranzakció felfüggesztése, így később hívható vissza az üzletben. | Igen | Igen | Nem | Igen‡ | Nem |
| 1004 | Feladatrögzítő | Nyissa meg a műveleteket lépésről lépésre ismertető lépéseket rögzíti a POS Feladatrögzítő. | Nem | Nem | Nem | Igen | Nem |
| 1052 | Fizetőeszköz-elszámolás | Az egyes leszámolt fizetési módoknál adja meg a pénz mennyiségét a fiókban. | Igen | Igen | Igen | Igen | Nem |
| 1210 | Fizetőeszköz kivétele | Pénz eltávolítása az aktuális fiókból vagy műszakból. | Igen | Igen | Igen | Igen | Nem |
| 920 | Blokkolóóra | A műszakok és szünetek be- és kiverődjön. | Igen | Igen | Igen | Nem | Nem |
| 302 | Teljes engedmény összege | Az engedmény összegének megadása. Ez a művelet csak olyan cikkeknél érvényes, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nem | Igen | Nem |
| 303 | Teljes engedmény (százalék) | Az engedmény százalékának megadása. Ez a művelet csak olyan cikkeknél érvényes, amelyekre engedmény adható, és csak a megadott határértékek között. | Igen | Igen | Nem | Igen | Nem |
| 501 | Tranzakció megjegyzése | Megjegyzés hozzáfűzése a jelenlegi tranzakcióhoz. | Igen | Igen | Nem | Igen | Nem |
| 922 | Termék részleteinek megtekintése | A kijelölt sorcikk termék Részletek lap megnyitása. | Igen | Igen | Nem | Igen | Nem |
| 1003 | Jelentések megtekintése | Az aktuális felhasználó beállított-jelentések megjelenítése | Igen | Igen | Igen | Nem | Nem |
| 921 | Blokkolóóra bejegyzéseinek megtekintése | Blokkolóóra minden üzletben dolgozóhoz tartozó bejegyzéseinek megjelenítése. | Igen | Igen | Igen | Nem | Nem |
| 211 | Fizetés érvénytelenítése | A tranzakcióból a jelenleg kiválasztott fizetési sor érvénytelenítését. | Igen | Igen | Nem | Igen | Nem |
| 102 | Érvénytelen termék | A tranzakcióból a jelenleg kiválasztott sor érvénytelenítését. | Igen | Igen | Nem | Igen | Nem |
| 500 | Tranzakció érvénytelenítése | Az aktuális tranzakció érvénytelenítése. | Igen | Igen | Nem | Igen | Nem |
| 916 | Windows folyamatkövető alaprendszer | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem |
| 924 | Bankkártyák X-jelentése | A művelet nem támogatott. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Igen |
| 311 | Rendszerengedmények eltávolítása a tranzakciókból | Távolítsa el az összes rendszer által alkalmazott engedményt, beleértve a kupon alapú kedvezmények, a tranzakcióból. Ez nem távolítja el a manuális engedményeket. | Igen | Igen | Igen | Igen | Nem |
| 312 | Rendszerengedmények újbóli alkalmazása | Alkalmazza újra a tranzakcióra vonatkozó rendszerengedményeket, ha azokat a **Rendszerengedmények eltávolítása a tranzakcióból** művelettel távolították el. | Igen | Igen | Igen | Igen | Nem |

\* A művelet csak akkor, amikor a vevői rendelés vagy értékesítési ajánlat létrehozása folyamatban van, az offline módban érhető el, de csak akkor, ha a vevői rendelések és értékesítési ajánlatok létrehozása offline helyesek-e a POS funkcióprofil. A művelet nem hajtható végre, rendelések létrehozásakor a Real-time Service segítségével, vagy ha a rendelések visszahívásához vagy szerkeszteni.

† A művelet csak akkor, amikor a POS helyesek-e a POS funkcióprofil vevők nélküli létrehozásának engedélyezése a kapcsolat nélküli módban hajtható végre.

A felfüggesztett tranzakciók ‡ a POS offline állapotban, ha csak az aktuális jegyzék offline adatbázis is hívható. A felhasználók nem felfüggesztése és a tranzakció visszahívása jegyzékek között.

A felfüggesztett tranzakciók ‡ a POS offline állapotban a jelenlegi offline adatbázisban, ha csak az aktuális jegyzék offline adatbázis is hívható.

\*\* A felfüggesztett tranzakciók ‡ a POS offline állapotban a jelenlegi offline adatbázisban, ha csak az aktuális jegyzék offline adatbázis látható a naplóban.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
