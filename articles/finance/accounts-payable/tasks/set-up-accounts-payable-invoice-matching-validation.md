---
title: A Kötelezettségekre vonatkozó számlaegyeztetés-ellenőrzés beállítása
description: Ez a cikk a kötelezettségek számlaegyeztetésének hitelesítésbeállítását ismerteti.
author: abruer
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 602666df4cf015791398939a3067a2cae85a12eb
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182555"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>A Kötelezettségekre vonatkozó számlaegyeztetés-ellenőrzés beállítása

[!include [banner](../../includes/banner.md)]

Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva. Ha az Ön vállalata a költségek lehetőség segítségével követi nyomon az olyan költségeket, mint például a szállítás, akkor győződjön meg arról, hogy a Költség-konfigurációs kulcs ki van választva.  A kötelezettségek számlaegyeztetése a szállítói számla, a beszerzési rendelés és a termékbevételezés egyeztetési folyamatát jelenti. A fenti dokumentumok közötti különbségeket egyeztetési eltérésnek nevezzük. Az egyeztetési eltéréseket a rendszer összeveti a megadott tűréshatárokkal. Amennyiben az egyezési eltérés meghaladja a tűréshatár százalékos értékét vagy összegét, a **Szállítói számla**, illetve a **Számlaegyeztetés részletei** oldalon megjelennek az egyeztetési eltérés ikonjai.

## <a name="determine-which-invoice-matching-validation-to-use"></a>A számlaegyeztetés használandó ellenőrzésének meghatározása
Négy típusú egyeztetési ellenőrzés használható. 

- **Sorszintű egyeztetés** – Leggyakrabban a sorok szintjén történő egyeztetést szokták használni. A sorok szintjén két vagy három irányban történhet az egyeztetés. Az alapértelmezett sorszintű egyeztetés a **Kötelezettségek paraméterei** oldalon adható meg a jogi személyekhez. A kétirányú egyeztetés a számlán és a beszerzési rendelésen szereplő egységárat hasonlítja össze. A háromirányú egyeztetés a számlamennyiséget is összehasonlítja az egyeztetett termékbevételezési mennyiséggel.
- **Számlaösszegek egyeztetése** – A számlán szereplő végösszegek és a beszerzési rendelésen szereplő végösszegek egyeztetése. Az ilyen típusú számlaegyeztetés a legkevésbé részletes, így ez a lehetőség olyan ellenőrzések beállítására használható, amelyek minimálisra csökkentik a számlaegyeztetés áttekintésére fordítandó munkaidőt. A program összehasonlítja a hat végösszeget (a részösszeget, a teljes engedményt, a költségeket, az áfát, a kerekítést és a számla összegét). A rendszer ellenőrzi, hogy a számlán szereplő említett értékek bármelyike az elfogadható mértéknél jobban tér-e el a várt összegtől.
- **Költségek egyeztetése** – A számlán szereplő költséginformációk (összegek) és a beszerzési rendelésen szereplő költséginformációk (összegek) egyeztetése
- **A sorokhoz tartozó cikkek árának összegei** – ez az egyeztetési típus olyan vállalatok számára hasznos, amelyek általában több számlát kapnak egy beszerzési rendelési sorhoz. Ha a beszerzési rendelés egy-egy sorához csak egy számlát szokott kapni, akkor nem szükséges ilyen egyeztetést használnia. Ehhez az egyeztetéshez engedélyezni kell a két- vagy háromirányú egyeztetést. Ez az egyeztetés a tűréshatás százalékos értékén vagy összegén alapul, és a túl nem léphető nettó összeg ellenőrzésére szolgál.  Ez az egyeztetési típus összehasonlíthatja a számla egyes soraiban feltüntetett nettó összegekre vonatkozó árinformációt és az összes függőben lévő, illetve korábban feladott számlasort a beszerzési rendelés megfelelő sorával. A nettó összeg meghatározása a következő képlet alapján történik: (Egységár * A sorban szereplő Mennyiség) + A sorban szereplő Költségek - A sorban szereplő Engedmények. Teljes árak egyeztetése során százalékkal, a rendszer a tranzakciós pénznem használatával hasonlítja össze az értékeket. Teljes árak egyeztetése során mennyiség alapján, a rendszer a könyvelési pénznem használatával hasonlítja össze az értékeket.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Paraméterek beállítása a számlaegyeztetés ellenőrzésének engedélyezéséhez
1. Lépjen a **Kötelezettségek > Beállítás > Kötelezettségek paraméterei** részre.
2. Kattintson a **Számlaegyeztetés** fülre.
3. Jelölje be a **Számlaegyeztetés-ellenőrzés engedélyezése** jelölőnégyzetet, vagy törölje belőle a jelet.
    * A mezőben válassza ki hogy előírja-e a jóváhagyást a számlaegyeztetési eltéréseket tartalmazó számlák feladása előtt. Ha az **Engedélyezés figyelmeztetéssel** beállítást használja, akkor vizuális jelzés mutatja, ha a számlaegyeztetési eltérés meghaladja a tűréshatárt. A számlát azonban fel tudja adni. A munkafolyamatok és a számlaegyeztetés-ellenőrzés együttes használata esetén – a többszörös jóváhagyás elkerülése érdekében – győződjön meg arról, hogy az **Eltéréseket tartalmazó számla feladása** mező értéke **Engedélyezés figyelmeztetéssel**.  
    * Válassza ki a **Számlafejléc állapotának automatikus frissítése** mezőben, hogy automatikus legyen-e az egyeztetés, amikor a rendszer a számla adatait tölti ki. A javasolt beállítás az **Igen**, kivéve akkor, ha az adatbevitel teljesítménye nem megfelelő. Az automatikus frissítések letiltása gyorsíthatja a rendszer teljesítményét, mivel a rendszer mellőzi a számlaegyeztetés-ellenőrzést az adatbevitel során. Amennyiben a **Nem** beállítást választja, úgy az adatbeviteli adminisztrátornak manuálisan kell frissítenie a számlaegyeztetési állapotot a számlaegyeztetés-ellenőrzés eredményeinek megtekintéséhez.  
4. Adja meg a **Számlaösszegek egyeztetése** beállítást.
5. A tényleges számlaösszegek és a várható összegek egyeztetéséhez jelölje be a **Számlaösszegek egyeztetése** jelölőnégyzetet, vagy törölje a jelölést.
    * Válassza ki, ikon jelezze-e, ha a számlaegyeztetési eltérés meghaladja a tűréshatárt. Választhat, hogy ikon, ha pozitív eltérés meghaladja a tűréshatárt, vagy ha a pozitív vagy negatív eltérés meghaladja a tűréshatára.  
    * Ha például a tűréshatára értéke 5 százalék, és a beszerzési rendelésen megadott teljes számlaösszeghez 100,00. Ezért áregyeztetési ikon jelenik meg a számlán a számla teljes összege meghaladja a 105,00. Amennyiben a **Nagyobb vagy kisebb a tűréshatárnál** beállítást választja, akkor is megjelenik az ikon, ha a számla összege kisebb, mint 95,00.  
6. A **Számlaösszegek tűréshatára százalékban** mezőbe írja be az elfogadható eltérés százalékos értékét. Ez az érték a vállalathoz tartozó alapértelmezett érték. Ez az érték meghatározott szállítók esetében felülbírálható a **Számlaösszegek tűréshatárai** oldalon. Egy adott szállító százalékban megadott számlaösszeg-tűréshatárának a felülbírálásáról a cikk későbbi részében, a „Tűréshatárnak megfelelő számlaösszegek beállítása a szállítókhoz” című szakaszban talál további információt.
7. Adja meg az **Ár és mennyiség egyeztetése** beállítást.
8. A **Soregyeztetési irányelv** mezőben válassza ki az aktuális jogi személyhez alapértelmezett irányelvként használandó értéket. A **Nem kötelező** beállítás azt jelenti, hogy nem szükséges a számlasorokban szereplő egyes árak, illetve a számlán feltüntetett mennyiségek összevetése a beszerzési rendelés árával, illetve a szállítólevélen feltüntetett mennyiségekkel. A **Kétirányú egyeztetés** azt jelenti, hogy szükséges a számlasorok ellenőrzése, de az kizárólag a beszerzési rendelés és a szállító számladokumentumai alapján történik. Az egyeztetési ellenőrzése nem terjed ki a termékbevételezési bizonylatra. A **Háromirányú egyeztetés** azt jelenti, hogy a rendszer a számla nettó egységárát a beszerzési rendelés nettó egységárával, a termékbevételezési mennyiséget pedig a számla szerinti mennyiséggel egyezteti.
9. Ha engedélyezni szeretné egy cikk, szállító, szállító-cikk kombináció vagy beszerzési-rendelési sor eltérő szintű egyeztetését, akkor válasszon ki egy értéket az **Egyeztetési irányelv felülbírálásának engedélyezése** mezőben. Egy adott szállítóra, cikkre, vagy szállító-cikk kombinációra vonatkozóan az **Egyeztetési irányelv** oldalon tudja felülbírálni a jogi személy soregyeztetési irányelvét.
    * Ha kétirányú vagy háromirányú egyeztetésen alapuló soregyeztetési irányelvet használ, a **Cikkár-tűréshatás** oldalon be tud állítani a jogi személyre, a cikkekre és a szállítókra vonatkozó ár-tűréshatár értékeket. A jogi személy alapértelmezett ártűréshatára nulla százalék lesz a két- és a háromirányú egyeztetésnél. A szállítói számláknak a beszerzési rendelés adataival való összehasonlítása során a a következő sorrendben keresi meg az alkalmazandó árkülönbözeti tűréshatárt.   
10. A sorelemek teljes árának a számlákon történő egyeztetéséhez válasszon ki egy értéket a **Teljes árak egyeztetése** mezőben. Az ilyen típusú egyeztetés akkor lehet hasznos, amikor a szállító több, ugyanarra a beszerzési-rendelési sorra vonatkozó számlát küld. Összehasonlíthatja az összes, a számla egyes soraiban feltüntetett nettó összegekre vonatkozó árinformációt és az összes függőben lévő, illetve korábban feladott számlasort a megfelelő beszerzési-rendelés sorral.  A használható beállítások: **Egyik sem**, **Százalék**, **Összeg** és **Százalék és összeg**.
11. A **Beszerzési ár teljes tűréshatárának százaléka** mezőbe írja be az eltérés elfogadható százalékos értékét. Ez a mező csak akkor érhető el, ha a **Teljes árak egyeztetése** mező értéke **Százalék** vagy **Százalék és összeg**.
12. A **Beszerzési ár teljes tűréshatára** mezőben adjon meg egy összeget a könyvelési pénznemben. Ez a mező csak akkor érhető el, ha a **Teljes árak egyeztetése** mező értéke **Összeg** vagy **Százalék és összeg**.
13. A **Teljes ár egyeztetését jelző ikon megjelenítése** mezőben adja meg, hogy jelenjen-e meg egy ikon, ha a számlaegyeztetési eltérés meghaladja a tűréshatárt. Választhat, hogy ikon, ha pozitív eltérés meghaladja a tűréshatárt, vagy ha a pozitív vagy negatív eltérés meghaladja a tűréshatára.
Ha például a tűréshatára értéke 5 százalék, és a beszerzési rendelésen megadott teljes számlaösszeghez 10,00. Ezért áregyeztetési ikon jelenik meg a számlán a számla teljes összege meghaladja a 10,50. Amennyiben a **Nagyobb vagy kisebb a tűréshatárnál** beállítást választja, akkor is megjelenik az ikon, ha a számla sorában a teljes ár kisebb, mint 9,50.
13. A költségegyeztetés **beállítása**
14. A tényleges költségek és a várható költségek beszerzési rendelés adatai alapján történő egyeztetéséhez jelölje be a **Költségegyeztetés** jelölőnégyzetet.

## <a name="set-up-unit-price-tolerance-percentages"></a>Egységár-tűréshatár százalékos értékének beállítása
Lépjen a **Kötelezettségek > Beállítás > Számlaegyeztetés beállítása > Árkülönbözet tűréshatárai** részre az ár engedélyezett tűréshatárához tartozó százalékos érték megadásához. Ha kétirányú vagy háromirányú egyeztetésen alapuló soregyeztetési irányelvet használ, be tud állítani a jogi személyre, a cikkekre és a szállítókra vonatkozó ár-tűréshatár értékeket. A szállítói számláknak a beszerzési rendelés adataival való összehasonlítása során a a következő sorrendben keresi meg az alkalmazandó árkülönbözeti tűréshatárt. Az alapértelmezett keresési sorrend a következő:
* Tábla/tábla
* Tábla/csoport
* Tábla/mind
* Csoport/tábla
* Csoport/csoport
* Csoport/mind
* Mind/tábla
* Mind/csoport
* Mind/mind

A vállalat alapértelmezett árkülönbözeti tűréshatára 0 százalék, ez vonatkozik minden cikkre és minden kódra (Minden, Minden). A vállalat alapértelmezett árkülönbözeti tűréshatár rekordját nem törölheti.

A  alapértelmezés szerint megengedi a negatív áreltéréseket. Negatív árkülönbözeti tűréshatár nem adható meg. A negatív ártűréshatár százalékos értékeinek nyomon követéséhez a **Kötelezettségek paraméterei** oldal **Egységár-egyeztetés ikonjának megjelenítése** mezőjében válassza a **Ha nagyobb vagy kisebb a tűréshatárnál** beállítást. Ezt követően adja meg az ár tűréshatárának százalékos értékét az **Árkülönbözet tűréshatárai** oldalon.

## <a name="set-up-matching-policy-override"></a>Egyeztetési irányelv felülbírálásának beállítása

Menjen a **Kötelezettségek > beállítási > Számlaegyeztetés beállítása > Egyeztetési** **irányelv, ha meg kell határoznia a Beszerzési rendelés oldal sorai egyeztetési irányelv** **mezőjének alapértelmezett** bejegyzését. Ez a beállítás nem kötelező. Ezen a lapon beállíthatja a cikkek, szállítók, illetve cikk- és szállítókombinációk oda-vissza egyeztetését. Ezekkel a bejegyzésekkel részletesebben határozhatók meg az egyeztetési irányelvek, mint a jogi személyre vonatkozó, a **Kötelezettségek paraméterei** lapon megadott egyeztetési irányelvvel. Az alapértelmezett jogi személy soregyeztetési irányelve csak azokra a tételekre és szállítókra nem vonatkozik, amelyekhez ehhez a lapon eltérő soregyeztetési irányelvet határoztak meg.

Ezen a lapon válassza ki az **Egyeztetési irányelv szintje** beállítást. Az a hierarchiaszint, amelynél felül kell bírálni a vállalat soregyeztetési irányelvét.

- **Cikk és szállító** – Adja meg az egyes szállítóktól vásárolt konkrét cikkek egyeztetési irányelvét.
- **Cikk** – Ha az irányelvet nem a cikk és a szállító szintjén határozza meg, adja meg az egyik szállítótól vásárolt konkrét cikkek egyeztetési irányelvét.
- **Szállító** – Ha az irányelvet nem a cikk és a szállító szintjén határozza meg, adja meg a konkrét szállítóktól vásárolt összes cikk egyeztetési irányelvét.
  
A következő hierarchia a használt egyeztetési irányelv meghatározására szolgál:
  *  Cikk és szállító
  *  Tétel
  *  Szállító
  *  Jogi személy
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Teljes számlaösszeg egyeztetési tűréshatárának beállítása a szállítókhoz

A teljes számlaösszeg egyeztetésének szállítóspecifikus tűréshatárai a **Kötelezettségek > Beállítás > Számlaegyeztetés beállítása > Számlaösszegek tűréshatárai** részen adhatók meg. Az egyeztetési számítás a számla teljes összegének a szállítói számlán megjelenő rendelési számlaként megadott szállítói számla százalékos tűréshatárát használja. Ha a szállítói számlánál nincs megadott százalékos tűréshatár a számlaösszegekhez, akkor a rendszer a számlaösszegek tűréshatárának azt a százalékos értékét használja a jogi személyhez, amelyet a **Kötelezettségek paraméterei** oldalon adtak meg.

1. Ha egyes szállítóknál külön, az alapértelmezett tűréshatárt felülbíráló tűréshatárt szeretne megadni, válassza a **Szállítói számla** lehetőséget.
2. Adja meg a szállítónál elfogadható eltérési százalékot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
