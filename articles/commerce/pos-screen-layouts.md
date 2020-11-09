---
title: Pénztár felhasználói felület vizuális konfigurációja
description: Ez a témakör a Dynamics 365 Commerce pénztár (POS) használatához kapcsolódó képernyő-elrendezésekről nyújt információkat.
author: boycezhu
manager: annbe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2a6fdbc957a50adba38627bc37622c17ab4be419
ms.sourcegitcommit: 9e7ceb5604472f3088f611aa0360bd6a716db32b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022471"
---
# <a name="pos-user-interface-visual-configurations"></a>Pénztár felhasználói felület vizuális konfigurációja

[!include [banner](includes/banner.md)]


A Microsoft Dynamics 365 Commerce pénztár (POS) felhasználói felülete vizuális profilok és képernyő-elrendezések kombinációjával konfigurálhat, amelyek üzletekhez, nyilvántartásokhoz és/vagy felhasználókhoz rendelhetők. Ez a témakör a konfigurációs lehetőségekkel kapcsolatos további információkat tartalmaz.

A következő ábra a POS felhasználói felület konfigurálható részeit leképező különböző entitások közötti összefüggéseket mutatja.

![POS képernyő-elrendezés entitások](../commerce/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Vizuális profil

A vizuális profilok nyilvántartásokhoz vannak rendelve, és a nyilvántartás-specifikus és a felhasználók számára közös vizuális elemek megadására szolgálnak. Bármelyik felhasználónak, aki bejelentkezik a nyilvántartásba, azonos lesz a téma az elrendezés a színek és a képek.

![Világos téma a POS üdvözlő képernyőn](../commerce/media/POS-Welcome-Screen-with-Light-theme.png)

![Sötét téma a POS üdvözlő képernyőn](../commerce/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Profil száma** - A profilszám a vizuális profil egyedi azonosítója.
- **Leírás** - Megadhat egy felismerhető nevet, amely segít azonosítani a megfelelő profilt az adott helyzetnek megfelelően.
- **Téma** – A **Világos** vagy a **Sötét** alkalmazástémák közül választhat. A téma hatással van a betűk és háttér színére az alkalmazás egészében.
- **Kiemelés színe** - A kiemelőszínt a rendszer használja a pénztárban mindenütt bizonyos vizuális elemek megkülönböztetésére és kiemelésére: ilyenek a csempék, a parancsgombok és a hivatkozások. Ezek az elemek általában interaktívak.
- **Fejléc színe** – Beállíthatja a kiskereskedő védjegy követelményeinek megfelelően az oldal fejlécének színét.
- **Betűtípusséma** – A **Standard** és a **Nagyméretű** betűtípussémák közül választhat. A Betűtípusséma hatással van a betűméretre az alkalmazás egészében. Alapértelmezetten a **Standard** lehetőség van kiválasztva.
- **Az alkalmazássáv címkéinek megjelenítése mindig** – Ha ez a beállítás be van kapcsolva, a címke szövege mindig látható az alkalmazássáv gombjai alatt.
- **Elrendezés** – A **Középre igazított** és a **Jobbra igazított** elrendezések közül lehet kiválasztani. Az elrendezés hatással van a bejelentkezési képernyőn a bejelentkezési mező igazítására. Alapértelmezetten a **Középre zárt** lehetőség van kiválasztva.
- **Dátum/idő megjelenítése** – Ha ez a beállítás be van kapcsolva, akkor az aktuális dátum és idő látható a pénztár fejlécében és a bejelentkezési képernyőn.
- **Billentyűzet** – Az **Operációs rendszer alapértelmezett billentyűzete** és a **Számbillentyűzet megjelenítése** közül választhat hogy a bejelentkezési képernyőn milyen alapértelmezett billentyűzetet kell használni a bevitelhez. A számbillentyűzet egy virtuális billentyűzet, amely elsősorban az érintés alapú eszközöknél használatos. Az alapértelmezett beállítás az **Operációs rendszer alapértelmezett billentyűzete**.
- **Logókép** – A bejelentkezési képernyőn megjelenítendő logó képét is megadhatja. Azt ajánljuk, hogy használjon átlátszó hátterű képet. A fájlméret a lehető legkisebb legyen, mivel a nagy fájlok tárolása és betöltése hatással lehet az alkalmazás viselkedésére és teljesítményére.
- **Bejelentkezési háttér** - Megadhatja a bejelentkezési képernyő háttérképét. A háttérképek fájlméretét a lehető legkisebbnek kell tartani.
- **Háttér** - Az egyszínű háttér helyett valamilyen beállítható képet is mutathat a háttérben az alkalmazás egészében. A bejelentkezési képernyő háttérképei esetében a fájlméretnek a lehető legkisebb méretben kell lennie.

> [!NOTE]
> A **Jobbra zárt** elrendezés és a dátum/idő megjelenítése nem érvényes a bejelentkezési képernyőre a kompakt nézetben.

Az **1090** ( **Pénztárgépek** ) elosztási ütemezési feladat futtatásával szinkronizálni kell a legfrissebb vizuális profilkonfigurációkat a csatorna-adatbázissal.

## <a name="screen-layouts"></a>Képernyő-elrendezések

A képernyő-elrendezés konfigurációja határozza meg a műveletek, a tartalom és a felhasználóifelület-vezérlők elhelyezését a pénztár **Üdvözlőképernyőjén** és **Tranzakciók** képernyőjén.

![Pénztár képernyő-elrendezés megtekintése](../commerce/media/POS-Screen-Layout-View.png)

- **Üdvözlőképernyő** - A legtöbb esetben az üdvözlőképernyő az a lap, amely a felhasználók látnak, amikor először jelentkeznek be pénztárba. Az üdvözlőképernyő védjegyképből és a POS-műveletekhez való hozzáférést biztosító gombrácsokból állhat. Jellemzően a műveletek, amelyek nem kötődnek a jelenlegi tranzakcióhoz, itt vannak elhelyezve.

    ![Pénztár üdvözlő képernyő](../commerce/media/POS-Welcome-Screen.png)

- **Tranzakció képernyőn** - A **Tranzakció** képernyő a pénztár fő képernyője az értékesítési tranzakciókat és a rendelések feldolgozásához. A képernyő-elrendezés tervezője használatával konfigurálhatók a tartalmak és az elrendezések.

    ![POS tranzakciós képernyő](../commerce/media/POS-Transaction-Screen.png)

- **Alapértelmezett kezdőképernyő** - Egyes kiskereskedők azt részesítik előnyben, ha a pénztáros közvetlenül a **Tranzakció** képernyőre lép a bejelentkezés után. Az **alapértelmezett kezdési képernyő** beállítással megadhatja az alapértelmezett képernyőt az egyes képernyő-elrendezésekre való bejelentkezéskor.

### <a name="assignment"></a>Hozzárendelés

Képernyő-elrendezések üzlet-, nyilvántartás- vagy felhasználószinten rendelhetők hozzá. A felhasználó-hozzárendelés felülírja a nyilvántartás- és üzlet-hozzárendeléseket, és a nyilvántartás-hozzárendelés felülbírálja az üzlet-hozzárendelést. Egyszerű forgatókönyvek esetén, ahol minden felhasználó ugyanazt az elrendezést használja a nyilvántartástól vagy a szerepkörtől függetlenül, a képernyő-elrendezés beállítható csak az üzlet szintjén. Azokban az esetekben, ahol bizonyos nyilvántartások vagy felhasználók speciális elrendezéseket igényelnek, ezek megfelelően hozzárendelhetők.

Attól függően, hogy milyen szintű képernyő-elrendezés van hozzárendelve, futtatnia kell az **1070** ( **Csatornakonfiguráció** ), az **1090** ( **Pénztárak** ) és/vagy az **1060** ( **Személyzet** ) elosztási ütemezési feladatokat a legfrissebb képernyő-elrendezési konfigurációk szinkronizálására a csatorna-adatbázisba.

### <a name="layout-sizes"></a>Elrendezési méretek

A pénztár kezelőfelületének nagy része interaktív, és az elrendezést automatikusan átméretezi és a képernyő mérete és tájolása alapján korrigálja. Azonban a POS **Tranzakció** képernyőjén minden várható képernyőfelbontást be kell állítani.

A pénztáralkalmazás az indítása alkalmával automatikusan kiválasztja a legközelebbi elrendezésméretet az eszközhöz. A képernyő-elrendezés az álló vagy fekvő módok, valamint teljes méretű és a kompakt eszközök konfigurációit is tartalmazhatja. Ezért a felhasználók hozzárendelhetők egyetlen képernyő-elrendezéshez, amely a különböző használt méretek és formátumok mindegyikén működik az üzletben.

![Pénztár elrendezési méretek](../commerce/media/POS-Screen-Layout-Sizes.png)

- **Név** – A képernyő mérete azonosítására szolgáló értelemszerű nevet is megadhat.
- **Elrendezés típusa** – A POS alkalmazás megjelenítheti a felhasználói felületet különböző módokon, biztosítva a legjob felhasználói élményt az adott eszköz.

    - **Modern POS - teljes** - A teljes elrendezések általában a nagyobb kijelzők esetén használhatók a legjobban, például az asztaliszámítógép-monitorokon vagy a táblagépeken. Kiválaszthatja a felhasználóifelület-elemeket, amelyeket az elrendezés tartalmazzon, megadhatja az elemek méretét és elhelyezését, és konfigurálhatja a részletes tulajdonságaikat. A teljes elrendezések az álló és a fekvő konfigurációkat egyaránt támogatják.
    - **Modern POS - kompakt** - A kompakt elrendezések általában a telefonokhoz és kis táblagépekhez használhatók a legjobban. A tervezési lehetőségek korlátozottak a kompakt eszközök esetében. A felhasználók beállíthatják az oszlopokat és a mezőket a bevételezés és az összegek panelekhez.

- **Szélesség/magasság** – Ezek az értékek képviselik az elrendezéshez várható valós képernyő méretet képpontban. Ne feledje, hogy egyes operációs rendszerek a nagyfelbontású kijelzőknél méretezést használnak.

> [!TIP]
> Megtudhatja az elrendezés kötelező méretét a képernyőhöz a felbontás megtekintésével az alkalmazásan. Indítsa el a pénztárat, és kattintson a **Beállítások \> Munkamenet-információk** elemre. A pénztár az aktuálisan betöltött képernyő-elrendezést mutatja, az elrendezés méretét és az alkalmazásablak felbontását.

![A pénztár munkamenet-információk oldala az aktuálisan betöltött képernyő-elrendezést mutatja, az elrendezés méretét és az alkalmazásablak felbontását](../commerce/media/POS-Session-Information.png)

### <a name="button-grids"></a>Gombrácsok

Az egyes elrendezésméretekhez a képernyő-elrendezésen gombrácsokat lehet konfigurálni és hozzárendelni az a POS üdvözlő képernyőhöz és a **Tranzakció** képernyőhöz. Az üdvözlő képernyő gombrácsainak automatikus elrendezése balról jobbra, a legkisebb számtól (1. üdvözlő képernyő) a legnagyobb számig.

A teljes pénztár képernyő-elrendezésekben a gombrácsok elhelyezése a képernyő-elrendezés tervezőjében van megadva.

A kompakt pénztár képernyő-elrendezésekben a gombrácsok automatikus elrendezése fentről le, a legkisebb számtól (1. tranzakció képernyő) a legnagyobb számig. Elérhetők el a **Műveletek** menüben.

![Gombrácsok kompakt elrendezésnél](../commerce/media/Compact-View-Button-Grids.png)

### <a name="images"></a>Képek

Minden egyes elrendezésmérethez a képernyő-elrendezésen, be lehet állítani a pénztár kezelőfelületen megjelenítendő képeket. A teljes pénztár képernyő-elrendezésekben egyetlen kép is megadható az üdvözlő képernyőhöz. A kép a bal oldali első kezelőfelületi elemként jelenik meg. A **Tranzakció** képernyőn a képek lap képként vagy emblémaként használhatók. A kompakt pénztár képernyő-elrendezések nem használják ezeket a képeket.

### <a name="screen-layout-designer"></a>Képernyő-elrendezés tervezője

A képernyő-elrendezés tervezője lehetővé teszi a pénztár **Tranzakció** képernyőjének különféle aspektusainak beállítását minden elrendezésmérethez, mind álló és fekvő módban, és a teljes és a kompakt elrendezésekhez is. A képernyő-elrendezés tervezője a ClickOnce telepítési technológiát használja az alkalmazás legújabb verziójának letöltésére, telepítésére és elindítására minden alkalommal, amikor a felhasználó megnyitja. Ügyeljen arra, hogy ellenőrizze a ClickOnce böngészővel szemben támasztott követelményeit. Néhány böngésző esetében, például a Google Chrome, bővítmények szükségesek.

> [!IMPORTANT]
> Be kell állítani egy képernyő-elrendezést minden egyes elrendezésmérethez, amely definiált és használt a pénztárban.

### <a name="full-layout-designer"></a>Teljes képernyőelrendezés-tervező

A teljes képernyőelrendezés-tervező segítségével a felhasználók felhasználóifelület-vezérlőit ráhúzhatják a pénztár **Tranzakció** képernyőjére, és beállíthatják a vezérlőelemek konfigurációját.

![Teljes pénztár képernyőelrendezés-tervező (fekvő mód)](../commerce/media/POS-Full-Layout-Designer-Landscape.png)

- **Elrendezés importálása/exportálása** – Exportálhatja és importálhatja a pénztár képernyő-elrendezéseket XML-fájlként, így egyszerű az újrafelhasználásuk és környezetek közötti megosztásuk. Fontos, hogy a megfelelő elrendezésmérethez tartozó elrendezési terveket importálja. Ellenkező esetben a felhasználói felület elemeivel előfordulhat, hogy nem férnek el megfelelően a képernyőn.
- **Fekvő/álló** – Ha a pénztár eszköz lehetővé teszi, hogy a felhasználók a fekvő és az álló üzemmódok között váltsanak, meg kell adnia minden üzemmódhoz a képernyő-elrendezést. A pénztár automatikusan észleli a képernyő elforgatását, és a helyes elrendezést jeleníti meg.
- **Elrendezésrács** – A pénztár képernyőelrendezés-tervező 4 képpontos rácsot használ. Felhasználói felület vezérlői a rácshoz „ugranak” a tartalom megfelelően igazításának elősegítésére.
- **Tervezői nagyítás** – A tervező nézet nagyítható a pénztár képernyő tartalmának jobb megjelenítéséhez. Ez a funkció akkor hasznos, ha a POS képernyőfelbontása jelentősen különbözik a tervező képernyőjének felbontásától.
- **Megjelenítés/elrejtés navigációs sáv** – A teljes pénztárelrendezések esetében választani lehet, hogy a bal oldali navigációs sáv megjelenjen-e a **Tranzakció** képernyőn. Ez hasznos az alacsony felbontású kijelzőknél. A láthatóság beállításához kattintson a jobb gombbal a navigációs sávra a tervezően, és jelölje be vagy törölje a **Mindig látható** négyzet jelölését. Ha a navigációs sáv nem látható, a POS-felhasználó továbbra is elérheti a bal felső menü használatával.

    ![A navigációs ablak megjelenítése és elrejtése](../commerce/media/Navigation-Bar.PNG)

- **POS-vezérlők** – A POS-képernyőelrendezés-tervező támogatja az alábbi vezérlőket. Kattintson a jobb gombbal, és a helyi menü segítségével beállíthat sok vezérlőt.

    ![Pénztár kezelőfelület-vezérlőelemek](../commerce/media/POS-UI-Controls.png)

    - **Számbillentyűzet** - A számbillentyűzet a fő felhasználói beviteli mód a pénztár **Tranzakció** képernyőjén. Beállíthatja a vezérlőt, hogy a teljes számbillentyűzetet jelenítse meg. Ez a beállítás az érintőképernyős eszközökhöz hasznos. Másik lehetőségként beállíthatja úgy, hogy csak a beviteli mező jelenjen meg. Ebben az esetben a fizikai billentyűzet szolgál a bevitelre. A számbillentyűzet-beállítások csak a teljes elrendezésben állnak rendelkezésre. A kompakt elrendezésekben a teljes számbillentyűzet mindig látható a **Tranzakció** képernyőn.
    - **Összegek panel** - Az összegek panel beállítható egy vagy két oszloposként, hogy olyan értékek legyenek megjeleníthetők, mint a sorok száma, az engedmény összege, a díjak, a részösszeg és az adó. A kompakt elrendezések csak egyetlen oszlopot támogatnak.
    - **Bevételezés panel** - A bevételezés panel tartalmazza az eladási sorokat, a fizetési sorokat és a pénztárban feldolgozott termékek és szolgáltatások szállítási adatait. Megadhatja az oszlopokat, a szélességüket és az elhelyezésüket. A kompakt elrendezések esetében további információkat is beállíthat, amelyek a fő vonal alatti sorban jelennek meg.
    - **Vevőkártya** - A vevőkártya a jelenlegi tranzakcióhoz társított vevővel kapcsolatos információkat jelenít meg. A vevőkártya beállítható úgy, hogy a további információk megjelenjenek vagy el legyenek rejtve.
    - **Lap vezérlőelem** - A lap vezérlőelem hozzáadható a képernyő-elrendezéshez, és a többi vezérlőelemet, például a számbillentyűzetet, a vevőkártyát vagy a gombrácsokat a lapon belül lehet elhelyezni. A lap vezérlőelem olyan tároló, amely segít több tartalom elhelyezésében a képernyőn. A lap vezérlőelem csak a teljes elrendezésekben érhető el.
    - **Kép** - A kép vezérlőelem segítségével az üzlet emblémája vagy más márkajelzése jeleníthető meg a **Tranzakció** képernyőn. A kép vezérlőelem csak a teljes elrendezésekben érhető el.
    - **Javasolt termékek** - Ha a környezethez konfigurálva van, a javasolt termékek vezérlő termékjavaslatokat jelenít meg a gépi tanulás alapján.
    - **Egyéni vezérlő** - Az egyéni vezérlő helyőrzőként működik a képernyő-elrendezésen belül, és lehetővé teszi a hely fenntartását egyéni tartalom számára. Az egyéni vezérlőelem csak a teljes elrendezésekben érhető el.

### <a name="compact-layout-designer"></a>Kompakt elrendezés tervezője

A teljes képernyőelrendezés-tervezőhöz hasonlóan a kompakt képernyőelrendezés-tervező teszi lehetővé a pénztár képernyő-elrendezés konfigurálását telefonokhoz és kis táblagépekhez. Azonban ebben az esetben az elrendezés rögzítve van. Kattintson a jobb gombbal, és a helyi menü segítségével beállíthatja az elrendezésben a vezérlőket. Azonban a további tartalmakhoz fogd és vidd műveleteket nem használhat.

![Kompakt elrendezés tervezője](../commerce/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Gombrács tervezője

A gombrácstervező használható a pénztár gombrácsok konfigurálásához a pénztár üdvözlő képernyőjén és a **Tranzakció** képernyőn a teljes és a kompakt elrendezésekhez. Ugyanaz a gombrács használható minden elrendezéshez és elrendezéstípushoz. Ahogy a képernyő-elrendezés tervezője, a gombrácstervező is a ClickOnce telepítési technológiát használja az alkalmazás legújabb verziójának letöltésére, telepítésére és elindítására minden alkalommal, amikor a felhasználó megnyitja. Ügyeljen arra, hogy ellenőrizze a ClickOnce böngészővel szemben támasztott követelményeit. Néhány böngésző esetében, például a Google Chrome, bővítmények szükségesek.

![Gombrács tervezője](../commerce/media/Button-Grid-Designer.png)

- **Új gomb** – Ide kattintva új gombot vehet fel a gombrácsa. Új gombok alapértelmezés szerint a rács bal felső sarkában jelennek meg. Beállíthatja azonban a gombok sorrendjét húzással az elrendezésben.

    > [!IMPORTANT]
    > A gombrács tartalma átfedésben is lehet. Gombok rendezésekor győződjön meg róla, hogy más gombokat nem rejtenek el.

- **Új terv** – Ide kattintva automatikusan beállít egy gombrácselrendezést a gombok számának megadásával sorok és oszlopok szerint.
- **Gomb tulajdonságai** – Gombtulajdonságok beállításához kattintson a jobb gombbal a gombra, és a helyi menü segítségével állítsa be.

    > [!IMPORTANT]
    > Néhány gombrácsbeállítás csak az Enterprise POS esetében aktív, a Modern POS és a Cloud POS esetében nem.

    ![Gombrácsgomb tulajdonságai](../commerce/media/Button-grid-button-properties.png)

    - **Művelet** – Az alkalmazható pénztárműveletek listájában válassza ki a műveletet, amely végrehajtódik a gombra való rákattintáskor a pénztárban.

        A támogatott pénztárműveletek listája: [Online és offline pénztár (POS) műveletek](pos-operations.md).

    - **Műveleti paraméterek** – Néhány POS-művelet használ további paramétereket, ha meghívják őket. A termék hozzáadása műveletnél például a felhasználók beállíthatják a terméket a hozzáadáshoz.
    - **Gombszöveg** – A mezőbe írja be a gombon a pénztárban megjelenő szöveget.
    - **Gomb szövegének elrejtése** – Használja ezt a jelölőnégyzetet a gomb feliratának megjelenítéséhez vagy elrejtéséhez. A gomb szövege gyakran rejtett kis gomboknál, amelyek csak egy ikont jelenítenek meg.
    - **Elemleírás** – Adja meg a további súgószöveget, amely megjelenik, amikor a felhasználó rámutat az egérgombbal.
    - **Mérete oszlopokban/Méret sorokban** – Megadhatja a gomb magasságát és szélességét.

        ![Pénztár gomb méretei a sorokban és oszlopokban](../commerce/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Egyéni betűtípus** – Ha bejelöli az **Egyéni betűtípus engedélyezése az POS szolgáltatáshoz** jelölőnégyzetet, az alapértelmezett rendszerbetűtípustól eltérő betűtípust adhat meg a pénztár számára.
    - **Egyéni téma** – A POS gombok alapértelmezés szerint a kiemelés színét használják a vizuális profilból. Ha bejelöli az **egyéni téma használata** négyzet jelölését, további színeket adhat meg.

        > [!NOTE]
        > A Modern POS és a Cloud POS csak a **háttérszín** és **betűszín** értékeket használja.

    - **Gomb kép** – A gomb tartalmazhat képeket és ikonat. A rendelkezésre álló képek közül választhat, amelyek itt vannak megadva: **Retail és Commerce \> Csatorna beállítása \> POS beállítása \> POS \> Képek**.

![Példa gombrács a pénztárban](../commerce/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>További erőforrások

[A Retail pénztár (POS) képernyőelrendezés-tervező telepítése](install-pos-layout-designer.md)
