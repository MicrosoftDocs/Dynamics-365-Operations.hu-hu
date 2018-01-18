---
title: "Képernyő elrendezésének beállítása a pénztár esetében"
description: "Ez a témakör a Microsoft Dynamics 365 for Operations for Retail pénztár (POS) használatához kapcsolódó képernyő-elrendezésekről nyújt információkat."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ad425ab0848ab04003b7378cb5c488650f01c441
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="configure-screen-layouts-for-pos"></a>Pénztár képernyő-elrendezésének beállítása

[!include[banner](includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 for Operations for Retail pénztár (POS) használatához kapcsolódó képernyő-elrendezésekről nyújt információkat.

A Microsoft Dynamics 365 for Operations for Retail pénztár (POS) felhasználói felülete vizuális profilok és képernyő-elrendezések kombinációjával konfigurálhat, amelyek üzletekhez, nyilvántartásokhoz és/vagy felhasználókhoz rendelhetők.

## <a name="visual-profile"></a>Vizuális profil
A vizuális profilok nyilvántartásokhoz vannak rendelve, és a nyilvántartás-specifikus és a felhasználók számára közös vizuális elemek megadására szolgálnak. Bármelyik felhasználónak, aki bejelentkezik a nyilvántartásba, azonos lesz a téma, a színek és a képek. 

**Profil száma** - A profilszám a vizuális profil egyedi azonosítója. 

**Leírás** - A leírása segítségével adhat meg egy felismerhető nevet, amely segít azonosítani a megfelelő profilt az adott helyzetnek megfelelően.

**Téma** - A felhasználók a világos vagy a sötét alkalmazástémák közül választhatnak. Ezek a beállítások hatással vannak az alkalmazás betűtípusaira és háttérszíneire.

**Kiemelés színe** - A kiemelőszínt a rendszer használja a pénztárban mindenütt bizonyos vizuális elemek megkülönböztetésére és kiemelésére: ilyenek a csempék, a parancsgombok vagy a hivatkozások. Ezek az elemek általában interaktívak.

**Fejléc színe** - A fejléc színe lehetővé teszi, hogy a felhasználó konfigurálja az oldal fejlécének színét, a kiskereskedő védjegyigényeinek megfelelően. Ez a funkció csak a Dynamics 365 for Operations for Retail 1611-es verziójában érhető el.

**Bejelentkezési hátterek** - A felhasználók megadhatják a bejelentkezési képernyő háttérképét. A háttérkép méretének a lehető legkisebbnek kell lennie, mivel a nagy fájlok tárolása és betöltése hatással lehet az alkalmazás viselkedésére és teljesítményére.

**Alkalmazásháttér** - A pénztár az egyszínű háttér helyett valamilyen képet is mutathat a háttérben az alkalmazás minden képernyőjén. A bejelentkezési háttérhez hasonlóan itt is ajánlatos a lehető legkisebb fájlméretet használni.

## <a name="screen-layouts"></a>Képernyő-elrendezések
A képernyő-elrendezés konfigurációja határozza meg a műveletek, a tartalom és a felhasználóifelület-vezérlők elhelyezését a pénztár üdvözlőképernyőjén és tranzakciók képernyőjén. 

**Üdvözlőképernyő**- A legtöbb esetben az üdvözlőképernyő az a lap, amely a felhasználók látnak, amikor először jelentkeznek be pénztárba. Az üdvözlőképernyő védjegyképből és a POS-műveletekhez való hozzáférést biztosító gombrácsokból állhat. Jellemzően a műveletek, amelyek nem kötődnek a jelenlegi tranzakcióhoz, itt vannak elhelyezve. 

**Tranzakció képernyőn** - A tranzakció képernyő a pénztár fő képernyője az értékesítési tranzakciókat és a rendelések feldolgozásához. A tranzakció képernyő a képernyő-elrendezés tervező segítségével konfigurálható. 

**Alapértelmezett kezdőképernyő** - Egyes kiskereskedők azt részesítik előnyben, ha a pénztáros közvetlenül a tranzakció képernyőre lép a bejelentkezés után. Az alapértelmezett indításiképernyő-beállítás lehetővé teszi ennek a beállítását minden egyes képernyő-elrendezéshez.

### <a name="assignment"></a>Hozzárendelés

Képernyő-elrendezések üzlet-, nyilvántartás- vagy felhasználószinten rendelhetők hozzá. A felhasználó-hozzárendelés felülírja a nyilvántartás- és üzlet-hozzárendelést, és a nyilvántartás-hozzárendelés felülbírálja az üzlet-hozzárendelést. Egyszerű forgatókönyvek esetén, ahol minden felhasználó ugyanazt az elrendezést használja a nyilvántartástól vagy a szerepkörtől függetlenül, a képernyő-elrendezés beállítható csak az üzlet szintjén. Azokban az esetekben, ahol bizonyos nyilvántartások vagy felhasználók speciális elrendezéseket igényelnek, ezek megfelelően hozzárendelhetők.

### <a name="layout-sizes"></a>Elrendezési méretek

Ez a funkció csak a Dynamics 365 for Operations for Retail 1611-es verziójára vonatkozik. Mivel sok esetben a képernyő-elrendezések több képernyőméreten és felbontáson is használhatók, a felhasználók mindegyikhez beállíthatják saját elrendezésüket és a tartalmukat. A pénztáralkalmazás az indítása alkalmával automatikusan kiválasztja a legközelebbi elrendezésméretet az eszközhöz. A képernyő-elrendezés emellett konfigurációkat is tartalmazhat a teljes-és kompakt eszközök számára. Ez a beállítás lehetővé teszi a felhasználók hozzárendelését egyetlen képernyő-elrendezéshez, amely a különböző méretű és formátumok mindegyikén működik az üzletben. 

**Modern POS - teljes** - A teljes elrendezések általában a nagyobb kijelzők esetén használhatók a legjobban, például a számítógép-monitorokon vagy a táblagépeken. A felhasználók kiválaszthatják, melyik felhasználóifelület-elemeket tartalmazza a rendszer, meghatározhatják a méretüket és az elhelyezkedésüket, és beállíthatják a részletes tulajdonságaikat. A teljes elrendezések az álló és a fekvő konfigurációkat egyaránt támogatják. 

**Modern POS - kompakt** - A kompakt elrendezések általában a telefonokhoz és kis táblagépekhez használhatók a legjobban. A tervezési lehetőségek korlátozottak a kompakt eszközök esetében. A felhasználók beállíthatják az oszlopokat és a mezőket a bevételezés és az összegek panelekhez.

### <a name="screen-layout-designer"></a>Képernyő-elrendezés tervezője

Minden elrendezésméretet a képernyő-elrendezésen belül a képernyő-elrendezés tervező segítségével kell konfigurálni. A tervező segítségével a felhasználók megadhatják és konfigurálhatják a tranzakció képernyő felhasználói felületének elemeit. A képernyő-elrendezés tervezője a ClickOnce megoldást használja az alkalmazás legújabb verziójának letöltésére, telepítésére és elindítására minden alkalommal, amikor a felhasználó megnyitja. Ellenőrizze a böngészőprogrammal szembeni követelményeket a ClickOnce használatához – egyes böngészőkben, például Chrome, bővítmények szükségesek. 

**Számbillentyűzet** - A számbillentyűzet a fő felhasználói beviteli mód a pénztár tranzakciók képernyőjén. Beállítható úgy, hogy a teljes, képernyőn megjelenő számbillentyűzetet mutassa, ami ideális az érintőképernyőkhöz, vagy csak a beviteli mező, amely a fizikai billentyűzettel használható. A számbillentyűzet-beállítások csak a teljes elrendezésben állnak rendelkezésre. A Dynamics 365 for Operations for Retail 1611-es verziójában a kompakt elrendezések mindig rendelkeznek a teljes számbillentyűzettel a tranzakciók képernyőn.

**Összegek panel** - Az összegek panel beállítható egy vagy két oszloposként, hogy olyan mezők legyenek megjeleníthetők, mint a sorok száma, az engedmény összege, a díjak, a részösszeg és az adó. A Dynamics 365 for Operations for Retail 1611-es verziójában a kompakt elrendezések csak egyetlen összegek oszlop használatát támogatják. 

**Bevételezés** - A bevételezés panel tartalmazza az eladási sorokat, a fizetési sorokat és pénztárban feldolgozott termékek és szolgáltatások szállítási adatait. A felhasználók megadhatják az oszlopok szélességét és elhelyezését. A Dynamics 365 for Operations for Retail 1611-es verziójában, a kompakt elrendezésekben, további információk is konfigurálhatók, amelyek a fő sor alatti sorban jelennek meg. 

**Vevőkártya** - A vevőkártya a jelenleg a tranzakcióhoz társított vevővel kapcsolatos információkat jelenít meg. A vevőkártya beállítható úgy, hogy a további információk megjelenjenek vagy el legyenek rejtve. 

**Lapvezérlő** – A lap vezérlőelem elhelyezhető a képernyő-elrendezésen, és a többi vezérlőelemet, például a számbillentyűzetet, a vevőkártyát vagy a gombrácsokat a lapon belül lehet elhelyezni. A lap vezérlőelem olyan tároló, amely segít a felhasználóknak több tartalom elhelyezésében a képernyőn. A lap vezérlőelem csak a teljes elrendezésekben érhető el. 

**Kép**- A kép vezérlőelem segítségével az üzlet emblémája vagy más márkajelzése jeleníthető meg tranzakció képernyőn. A kép vezérlőelem csak a teljes elrendezésekben érhető el. 

**Javasolt termékek** - Ha a környezethez konfigurálva van, a javasolt termékek vezérlő termékjavaslatokat jelenít meg a gépi tanulás alapján. A javasolt termékek vezérlő csak a teljes elrendezésekhez érhető el a Dynamics 365 for Operations for Retail 1611-es verziójában. ** Egyéni vezérlő ** - Az egyéni vezérlő helyőrzőként működik a képernyő-elrendezésen belül, és lehetővé teszi a felhasználók számára hely fenntartását egyéni tartalom számára. Az egyéni vezérlőelem csak a teljes elrendezésekben érhető el.

<a name="see-also"></a>Lásd még
--------

[Telepítse a Retail POS-képernyő elrendezéstervezőt](install-pos-layout-designer.md)




