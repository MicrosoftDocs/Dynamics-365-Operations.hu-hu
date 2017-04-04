---
title: "A POS képernyő-elrendezések konfigurálása"
description: "Ez a témakör a Microsoft Dynamics 365 műveletek - kiskereskedelmi értékesítés (POS) tapasztalatok pont képernyő-elrendezések információt."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>A POS képernyő-elrendezések konfigurálása

Ez a témakör a Microsoft Dynamics 365 műveletek - kiskereskedelmi értékesítés (POS) tapasztalatok pont képernyő-elrendezések információt.

Műveletek - kiskereskedelmi pont (POS) értékesítés felhasználói felület a Microsoft Dynamics 365 vizuális profilok és a képernyő-elrendezések, üzletek, nyilvántartások, illetve a felhasználók rendelt kombinációjával kell konfigurálni.

## <a name="visual-profile"></a>Vizuális profil
Vizuális profilok nyilvántartások vannak rendelve, és a vizuális elemek, amelyek a nyilvántartás-specifikus és a megosztott keresztül a felhasználók megadott. Bárki, aki bejelentkezik a nyilvántartásba történő lesz az azonos téma, színek és képek. **Profil száma** -a profil értéke a vizuális profil egyedi azonosítója. **Leírás** -leírása segítségével adja meg egy beszédes nevet, amely segít azonosítani a megfelelő profilt az adott helyzetnek megfelelőt. **Téma** -felhasználók közül választhat a világos vagy sötét témák alkalmazást. Ezek a beállítások hatással az alkalmazás teljes betűtípus és a háttér színeit. **Hangsúlyos szín** -a Kiemelőszín használja mindenütt a POS különbséget tenni, vagy jelölje ki a mozaikok, parancsgombok vagy hivatkozások bizonyos vizuális elemek. Ezek általában az felróható elemei. **Fejléc színét** -fejléc színét lehetővé teszi, hogy a felhasználó konfigurálhatja a színt a védjegy a kiskereskedő igényeinek megfelelően oldalfej. Ez a funkció érhető el csak 365 Dynamics 1611 műveletek verziójához. **Bejelentkezés hátterek** -a felhasználók megadhatják a bejelentkezési képernyőn háttérképként. Háttérképek méretének meg kell őrizni minimalizálni, tárolására és nagy fájlok betöltése is hatással vannak a alkalmazás viselkedését és teljesítményét. **Alkalmazás háttér** -a POS is használható, kép háttér helyett a szilárd téma színei az alkalmazáson keresztül. A bejelentkezési háttérrel rendelkező ajánlatos megtartani a fájlméret a lehető legkisebb legyen.

## <a name="screen-layouts"></a>Képernyő-elrendezések
Képernyő-elrendezés konfigurációja határozza meg, hogy a műveletek, a tartalom és a POS üdvözlő képernyőjén és a tranzakciók képernyőn a felhasználói felület vezérlők elhelyezését. ** Az üdvözlőképernyő **-a legtöbb esetben az üdvözlőképernyő az a lap, amely a felhasználók látnak, amikor először jelentkeznek be POS. Az üdvözlőképernyő védjegyzés képének és POS-műveletekkel való hozzáférést biztosító gombrácsok állhat. Jellemzően műveletek, amelyek nem kötődnek a jelenlegi tranzakció Itt vannak elhelyezve. **Tranzakció képernyőn** -a tranzakciók képernyőn a POS a fő képernyőn az értékesítési tranzakciókat és a rendelések feldolgozása. A tranzakciók képernyőn a képernyő-elrendezés designer segítségével konfigurálható. **Alapértelmezett kezdőképernyőjén** -egyes kiskereskedők inkább, hogy a pénztáros léphet közvetlenül a tranzakciók képernyőn bejelentkezés után. Az alapértelmezett indítási képernyő beállítás be minden egyes képernyő-elrendezés lehetővé teszi.

### <a name="assignment"></a>Hozzárendelés

Képernyő-elrendezések tároló, nyilvántartást vagy felhasználói szinten is rendelhető. A felhasználó-hozzárendelés felülírja az oltalom alatt álló és hozzárendelés, és a nyilvántartás hozzárendelés felülbírálja a tároló hozzárendelés tárolására. Egyszerű forgatókönyv, ahol minden felhasználó használja a nyilvántartásban vagy a szerepkör azonos elrendezésű a képernyő-elrendezés állítható csak az üzletben. Azokban az esetekben, ahol bizonyos nyilvántartások vagy felhasználók igényel speciális elrendezések hozzárendelhető megfelelően.

### <a name="layout-sizes"></a>Elrendezési méretek

Ez a szolgáltatás csak érvényes Dynamics 365 1611 műveletek verziójához. Sok esetben a képernyő-elrendezések között több képernyő méretű és felbontású is használható, mert a felhasználók beállíthatják az elrendezés és a tartalom minden. A POS alkalmazás indítása alkalmával automatikusan válassza az eszköz a legközelebbi elrendezés méretét. A képernyő-elrendezés teljes-és kompakt konfigurációk is tartalmazhat. Ez a beállítás lehetővé teszi a felhasználóknak kell rendelni a különböző méretű és a tárolóban gépformák keresztül működő egyetlen képernyőn elrendezés. **Modern POS - teljes** -teljes elrendezések általában legjobb használt számítógép-monitor vagy a tabletta nagyobb kijelzők esetén. Felhasználók választhatnak, melyik felhasználói felületének elemeit tartalmazza, határozza meg a méretét és elhelyezkedését és azok részletes tulajdonságainak beállítása. Teljes elrendezések álló és a fekvő konfigurációkat támogat. **Modern POS - Compact** -kompakt elrendezések általában leginkább használt telefonok vagy kis tabletta. Tervezési lehetőségek korlátozottak kompakt eszközök. Felhasználók beállíthatják az oszlopok és a mezők a Bevételezés és az összegek panelek.

### <a name="screen-layout-designer"></a>Képernyő-elrendezés tervezője

Minden elrendezés méretét a képernyő-elrendezés belül úgy kell konfigurálni, hogy a képernyő-elrendezés designer segítségével. A tervező segítségével a felhasználók megadásához és konfigurálni a tranzakció képernyő felhasználói felületének elemeit. A képernyő-elrendezés tervezője ClickOnce letöltésére, telepítésére és indítsa el az alkalmazás minden alkalommal, amikor a felhasználó fér hozzá, akkor a legújabb verzióját használja. Ellenőrizze böngészőprogrammal szembeni követelmények ClickOnce segítségével – egyes böngészőkben, például króm, szükséges bővítmények. **Számbillentyűzet** -a számbillentyűzet a fő felhasználói beavatkozásra a POS-tranzakciók képernyőn. A teljes képernyőn való megjelenítéséhez a pad ideális érintőképernyős, vagy csak a beviteli mező, amely a fizikai billentyűzettel használható konfigurálható. A szám pad beállítások állnak rendelkezésre a teljes elrendezés. Műveletek verzió 1611 365 Dynamics tömör elrendezés mindig rendelkeznek a teljes számbillentyűzet a tranzakció képernyőről érhető el. **Összegek panel** - az összegek panelen beállítható egy vagy két oszlop mezők megjelenítendő sorok száma, Sorengedmény összege, díjak, részösszeg és adó. Műveletek verzió 1611 365 Dynamics tömör elrendezés csak egyetlen összesen oszlop támogatja. **Nyugta** -** ** a beérkezés panel tartalmazza az eladási sorok, a fizetési sorok és szállítási adatainak a termékek és szolgáltatások a POS feldolgozása. Felhasználók megadhatják az oszlopok szélességét és elhelyezését. Műveletek verzió 1611 365 Dynamics tömör elrendezés további információkat, amelyek megjelennek a sor mellett a Fővonal is beállíthatja. **Vevő karton** - a vevő karton információk megjelenítése a vevő a tranzakció jelenleg társított kapcsolatos. A vevő karton beállítható úgy, hogy további információk megjelenítése vagy elrejtése. **Lap vezérlő** - elhelyezési és egyéb vezérlők, például a számbillentyűzet, vevő karton, a karton vezérlőelem el lehet helyezni, vagy gombrácsok el lehet helyezni a lapon belül. A karton vezérlőelem olyan tároló, amely segít a felhasználóknak több tartalom igazítása a képernyőn. Teljes elrendezések a karton vezérlőelem csak érhető el. ** Kép **-a kép vezérlőelem segítségével az üzlet embléma vagy más védjegyzés képének megjelenítése a tranzakciók képernyőn. A kép vezérlőelem lehetőség csak a teljes elrendezést. **Ajánlott termékek** - Ha a környezet konfigurálva vezérlő Termékjavaslatok gép tanulás alapján jeleníti meg az ajánlott termékek. Az ajánlott termékek ellenőrzési műveletek verzió 1611 365 Dynamics teljes elrendezések csak érhető el. ** Egyéni vezérlő **-az egyéni vezérlő működik, helyőrző belül a képernyő-elrendezés lehetővé teszi a felhasználók egyéni tartalom helyet foglalni. Az egyéni vezérlő lehetőség csak a teljes elrendezést.

<a name="see-also"></a>Lásd még
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)


