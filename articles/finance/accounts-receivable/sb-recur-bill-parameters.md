---
title: Ismétlődő szerződéses számlázási paraméterek
description: Ez a cikk bemutatja az ismétlődő szerződéses számlázásban létrehozott számlázási ütemezések alapértelmezett értékeinek beállítását. Ezenkívül bemutatja a számlázási ütemezési csoportok létrehozásához szükséges beállításokat is.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 64d6e21c2d8c588a64f0f4cf8b7a0bafc853bcab
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644003"
---
# <a name="recurring-contract-billing-parameters"></a>Ismétlődő szerződéses számlázási paraméterek

Az Ismétlődő szerződés **számlázási paraméterei** lapon beállíthatja az ismétlődő szerződés számlázása esetén létrehozott számlázási ütemezések alapértelmezett értékeit. Ezeket az alapértelmezett értékeket kezdetben az összes létrehozott számlázási ütemezés fogja használni. Szükség esetén azonban módosítani lehet az egyes számlázási ütemezések értékeit.

## <a name="general-tab"></a>Általános fül

1. Az Ismétlődő szerződés **számlázási paraméterei** lap **·** **Általános lapján, a Számlázási ütemezés csoport** mezőben válasszon ki egy számlázási ütemezési csoportot. A számlázási ütemezési csoportok [beállítását a cikk számlázási ütemezési csoportjai](#set-up-billing-schedule-groups) című későbbi részében olvashatja.
2. A Felmondás **típusa mezőben** válassza ki, hogyan történik a végső számla kiszámítása a számlázási ütemezés megszüntetésekor:

    - **Ütemezés módosítása** – a felmondási dátum számlázási ütemezésének kikapcsolása, **az** ütemezés állapotának módosítása Utolsó számlázás állapotra, és a kapcsolódó halasztás ütemezésének módosítása a már nem felismerhető összeg megfordítása alapján. Ha a számlázás kezdő dátuma a munkaviszony megszűnésének dátuma utánra kerül, a fennmaradó számlázási időszakok törlődnek.
    - **Fennmaradó számla** – a számlázási ütemezésben fennmaradó összegek hozzáadása a felmondási időszakhoz, **az** ütemezés állapotának módosítása Utolsó számlázás állapotra, és a halasztás ütemezésének frissítése. Ha a számlázás kezdő dátuma a munkaviszony megszűnésének dátuma utánra van adva, a rendszer hozzáadja a számlázási időszakhoz a hátralévő számlázási időszakok teljes összegét, és eltávolítja a hátralévő számlázási időszakokat.
    - **Nincs módosítás** – a felmondás napján megszünteti a számlázási ütemezést. A számlázási ütemezésen nem végez módosítást.

3. Az Egyedi **ütemezéstípus mezőBen** a Nincs **lehetőséget** választva megadhatja, hogy a vevők csak egyetlen számlázási ütemezésre korlátozódnak. Válassza vevőnként **vagy** **végfelhasználónként** annak megadását, hogy a vevők csak egyedi ütemezésre korlátozódnak.
4. Ha a számlázási **ütemezés részletes** **sorait** a számlázási ütemezés létrehozása vagy frissítése esetén a hónap végi dátumhoz igazítja, állítsa Igen beállításra a Hónaphoz igazítás beállítást. Állítsa Nem beállításra **a** növekményes dátumok használatára.
5. Állítsa a **Részleges időszakok arányos beállítása** Igen beállításra **a** számlázási összegeknek az időszak napjainak száma alapján való felosztásához. Állítsa Nem **értékűre**, hogy minden számlázási időszakban a napok számától függetlenül egyforma legyen az összege.
6. Ha a **Részleges időszakok megtérítése** **lehetőséget** Igen beállításra adja meg, **állítsa a Proration Method** **mezőt** Napi beállításra, és az összegeket az időszak napjainak száma alapján osztja fel. Állítsa **havira**, hogy minden hónapban egyforma legyen az összeg.
7. Adja meg, hogy az újonnan létrehozott számlázási ütemezések alapértelmezés szerint le vannak-e állítva.

    > [!NOTE]
    > Ha el szeretné távolítani a számlázási ütemezések által visszatartott adatokat, akkor a felhasználónak egy felhasználói csoportnak kell lennie. Ha olyan **felhasználócsoportot** szeretne beállítani, amelyben engedélyezve van a **Hold-eltávolítás engedélyezése**, válassza A visszatartott csoport felülbírálatának eltávolítása" lehetőséget.

8. **IA Számla tranzakciótípus mezőben** válassza ki az új számlázási ütemezések alapértelmezett számlatranzakció-típusát.
9. A **Halasztás igazítása** számlázásihoz beállítás **Igen** beállítással a megfelelő halasztás ütemezésének megfelelően beállíthatja, hogy a számlázási ütemezéssel azonos dátumokat használ. Állítsa **Nem** beállításra, ha más dátumokat ad meg.
10. A bevétel felosztása funkció használata esetén állítsa **Igen** beállításra a **Bevétel felosztása automatikus létrehozása beállítást**, amikor cikkeket adnak hozzá a számlázási ütemezéshez. A **bevétel felosztása** jelölőnégyzet automatikusan be lesz jelölve a számlázási ütemezés sorában, ha a cikk bevétel szerinti felosztási cikkként van beállítva. Állítsa **Nem** beállításra, ha manuálisan szeretné bejellni a **Bevétel** felosztása jelölőnégyzetet.
11. A Vevő felosztása **beállítás** Igen **beállítással** engedélyezheti a számlázási ütemezés különböző vevőknek való számlázását. Igen beállítás **esetén** **a** vevői felosztás lehetőség elérhető a számlázási ütemezés fejlécében és sorában. 
12. Az értékesítési rendelés létrehozására vonatkozó mezők beállítása:

    - A számlák időszak, vevő vagy cikk szerint konszolidálhatók. Az **Igen** és a **Nem** érték bármilyen kombinációja beállítható. A számlák cikkcsoport szerint is feloszthatóak.
    - A számlákhoz a következő feladási lehetőségek érhetők el:

        - **Értékesítési rendelés létrehozása**– csak az értékesítési rendelés létrehozása.
        - **Számlafeladás megjelenítése**– az értékesítési rendelés számlázása, és egy olyan lap megnyitása, ahol manuálisan fel lehet állítani a számlát.
        - **Díjszöveges számla** létrehozása – akkor válassza ezt a lehetőséget, ha szabadszöveges számlákat használ.
        - **Számla automatikus feladása**– az értékesítési rendelés számlázása és automatikus feladása.

    - A Számlázási dátumok **hozzáadása a cikkleíráshoz beállítás Igen** beállítással **a** számlázás kezdő és záró dátumát tartalmazó leírás hozzáadásához.
    - A Nulla felhasználás **kizárása** beállítás Igen **beállítással** kizárhatja azokat a számlázási ütemezési sorokat, amelyekhez nincs felhasználás. Állítsa Nem **beállításra**, ha fel kell foglalnia ezeket a sorokat az értékesítési rendelésbe.
    - Állítsa Igen **beállítással** **a** Gyermek cikkek nyomtatása nem nyomtatva beállítást, ha nem szeretné az értékesítési rendelésre felosztani a bevételbe felosztott gyermek cikkeket. A számlán csak a szülő cikk fog megjelenni. Ha a (rejtett) gyermekelemek nettó összege nem nulla összeg, a szülősor nettó összege a gyermeksorok összegzését jeleníti meg. Állítsa Nem beállításra, **ha** minden gyermektételt a szülőcikk alá szeretné nyomtatni az értékesítési számlán.

12. A mezők beállítása támogatásra és megújításra:

    - Ha az értékesítési **rendelés támogatási** **és** megújítási funkcióját automatikusan használni szeretné, állítsa Az automatikus engedélyezés és megújítás lehetőséget Igen beállításra.
    - A Támogatás **és megújítási szint mezőben** válassza ki az alapértelmezett támogatást és megújítási szintet.
    - A Támogatás **és megújítási mennyiség** mezőben adja meg a támogatás és a megújítási mennyiséget.
    - Az Alapértelmezett **támogatás és megújítás kezdő** dátuma mezőben adja meg a támogatás és megújítás alapértelmezett kezdési dátumaként használni kívánt dátumot:

        - **Tranzakció dátuma** – a tranzakció dátuma legyen a kezdő dátum.
        - **A jelenlegi hónap kezdete** – a kezdő dátum az aktuális hónap első napja.
        - **A következő hónap kezdete** – a következő hónap első napját használja kezdő dátumként. Ha a tranzakció dátuma az első, akkor a program az aktuális hónap első hónapját használja.
        - **15-ös** szabály – az aktuális hónap első napja legyen a kezdő dátum, ha a tranzakció dátuma a hónap első és tizenötödik napja közé esik. Ha a tranzakció dátuma a tizenhatod vagy későbbi, akkor a kezdő dátum a következő hónap első napja legyen.

    - Ha az **engedmény összegét beleveszi** **a** támogatásba vagy a megújítási összegbe, állítsa Igen beállításra az engedmény szerepeljen a számítási számításban beállításnál. Állítsa Nem beállításra **az** engedmény összegének kizárására.
    - **A Támogatás gyakorisága** **és** megújítása gyakorisági mezőben adja meg, hogy a számlázási ütemezéshez hozzáadja-e a támogatás és a megújítás gyakoriságát: **Napi,** Havi **·**, **Negyedéves**, **Semjén** **vagy Éves.**
    - Az Új cikkek **kezdő** **és** záró dátumának igazítása a meglévő cikkekhez a cikkcsoport alapján beállítása Igen beállítással.
    - A **következő** **nemszámlázatlan** időszakhoz való igazítás beállítása Igen beállítással határozza meg a megújítási cikk igazításának dátumát a megújítást követően következő nemszámlázatlan időszak dátuma alapján.
    - A Sorozatszám **másolása beállítás** **Igen** beállítással a cikk sorozatszámát a kezdeti értékesítésirendelés-sorból a megfelelő számlázási ütemezési sorba másolhatja.

13. Ha a számlázási ütemezésben eszkalációt használ, válassza ki a felhasználói árindex számításához használt módszert.
14. Ha rögzíteni **szeretné** **az** árváltozásokat a számlázási ütemezés sorai között, állítsa Igen beállításra. Ha a számlázási ütemezés egy sorát manuálisan normálról egyszerűre változott, és új árat ad meg, a rendszer nyomon követi a számlázási ütemezés sorának könyvvizsgálati adatait. Állítsa Nem **beállításra**, ha nem szeretné nyomon követni ezeket a módosításokat.
15. Adja meg, hogy a rendszer alapértelmezés szerint szűri-e a rekordokat a Kezdő dátum vagy a Záró dátum szerint a Számla **létrehozása lapon**.
16. A Nemszámlázatlan **bevétel** funkció használata esetén adja meg az alkalmazott beállításokat:

    - Állítsa az **Általános napló automatikus feladása** lehetőséget Igen **beállításra**, ha azt szeretné, hogy az általános napló egyidejűleg megjelenik és fel legyen adva. Állítsa Nem **beállításra**, ha létre szeretné hozni az általános naplót, majd manuálisan fel szeretné adja.
    - Az Alapértelmezett **naplónév mezőben** válassza ki az általános napló létrehozásakor használni kívánt alapértelmezett naplónevet.
    - A Rövid **távú nemszámlázatlan** mód mezőben válassza ki a rövid távú nemszámlázatlan módszert, ha használ egyet. Ha a Nincs **lehetőséget** választja, akkor a rövid távú funkció nem lesz használva a nemszámlázatlan bevétellel. Válassza **a Görgető időszakok** lehetőséget, ha mindig 12 hónapot **vagy rögzített évet** használ a hátralévő pénzügyi év használatára.

17. Adja meg a számlázási ütemezés és annak sorai felmondása esetén használt beállításokat:

    - **Jóváírás kiállítása** – jóváírás létrehozása számlázási ütemezés vagy számlázási ütemezési sor megszüntetése esetén.
    - **Jóváírás-korrekció** – jóváírás-korrekció létrehozása számlázási ütemezéshez sor megszüntetése esetén. A jóváírás-korrekció a számlázási ütemezés jövőbeli számlázási időszakában jelenik meg. A jóváírás-korrekció mindaddig frissíti a következő számlázási időszak számlaösszegét, amíg a jóváírást be nem fejezte a számlázási ütemezésre.
    - **Nincs jóváírás** – ne hozzon létre jóváírást vagy jóváírást, ha egy számlázási ütemezés vagy számlázási ütemezési sor megszűnik. Ez a lehetőség csak akkor érhető el, ha **a** Nincs beállítás beállítás van használva a számlázási ütemezés megszüntetéséhez.
18. Ha egy visszatérítéssel le lehet állítani az "Egyszer" lehetőséget, és a számlázási ütemezés egyszeres számlázási gyakorisággal lesz kiállítva, **akkor** a számlázási ütemezés számlázása után a **számlázási** ütemezés sorának állapota "Befejezve" lesz.**·** **·** Ez a számlázási ütemezés nem szüntethető meg, és nem lehet jóváírást kibocsátani. Ha **egy alkalommal a** **·** **·** **visszatérítéssel** le lehet állítani, igen a számlázási ütemezésnek az Egyszer számlázási gyakorisággal beállított állapota a számlázási ütemezés számlázása után aktív lesz. A számlázási ütemezési sor megszakítható, és a visszatérítés feldolgozható. 
19. A **paraméterek között beállított** napi beállítás alapértelmezett beállítása a tömeges felmondási lap, valamint a számlázási ütemezés fejléce és sor felmondása párbeszédpanel lesz. A felmondási folyamat során módosítható. Igen beállítás esetén **minden** visszatérítési összeg számítása napi díj alapján történik. Nem beállítás esetén **a** rendszer a felmondási dátum és a számlázási gyakoriság alapján jóváírást hoz létre. Ha például a havi gyakoriságot és a számlázási összeget $100 meg, akkor a követel összeg a havi gyakorisággal $100. Ha a számlázási gyakoriság egyszeres, akkor a követel összeg $0.00. Ahhoz, hogy visszatérítést kap az egyszeres számlázási gyakorisággal, napi időkorrektációt kell beállítani Igen beállításra. 
20. Halasztás **létrehozása** **követelhez** beállítás Igen beállítással új halasztás ütemezést hozhat létre meglévő halasztás ütemezésének jóváírása esetén. A meglévő halasztás ütemezésének **jóváírásának** létrehozásához hagyja a Nem lehetőséget.

## <a name="sequence-number-tab"></a>Sorszám lap

Az Ismétlődő szerződés **számlázási** paraméterei lap **Sorozatszám** lapján beállíthatja a számlázási ütemezési számok alapértelmezett értékét. Az alapértelmezett értékeket a **Számsorozatok lapon lehet beállítani (** Szervezet **felügyelete – Számsorozatok \>\>).**

## <a name="set-up-billing-schedule-groups"></a>Számlázási ütemezési csoportok beállítása

A Számlázási ütemezés **csoport lapon** hozhat létre számlázási ütemezési csoportot az ismétlődő szerződéses számlázáshoz. Új számlázási ütemezés létrehozásakor és egy számlázási ütemezési csoport alkalmazásakor a **számlázási** ütemezés lapon meghatározott értékek határozzák meg a számlázási ütemezés alapértelmezett értékeit. A létrehozott számlázási ütemezéshez bármelyik alapértelmezett értéket módosíthatja. Több számlázási ütemezési **csoportot is be lehet állítani, majd az ismétlődő szerződés számlázási paraméterei oldalon az egyiket alapértelmezett számlázási ütemezési csoportként lehet beállítani**.

A következő lépések szerint hozhat létre számlázási ütemezési csoportot az ismétlődő szerződés számlázásához.

1. A Számlázási **ütemezés csoport lapon** az Új **gombra** választva hozzon létre számlázási ütemezési csoportot.
2. A Számlázási **ütemezés csoport mezőben** adjon meg egy egyedi azonosítót.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. A Számlázási **gyakoriság** mezőben adja meg, hogy milyen gyakran számlázható a számlázási ütemezés a vevőnek: **egyszeres**, napi, **havi** **·**,**negyedéves**, **félévenkénti** **vagy éves ütemezésű**.
5. A Számlázási **időszak mezőben** adja meg a számlázási intervallumot. Például állítsa **a Számlázás gyakorisága** mezőt **Havi** **·** **, a Számlázási intervallum mező értéke pedig 2-re** minden más hónapban.
6. Az Árképzési **módszer mezőben** válassza ki a számlázási ütemezésben található cikkek alapértelmezett árképzési módszerét:

    - **Normál** – az egységár számítása a megadott teljes mennyiség alapján, **és** a Termékinformációk kezelése lap Kiadott termékek lapjára vonatkozó normál árképzés használata.
    - **Lakás** – a számlázási ütemezés sorában megadott egyszerű ár alkalmazása.
    - **Szint** – az egységár számítása rögzített mennyiséggel, eltérő árképzési zárójellel. A következő ár zárójelbe lépése előtt minden szintet ki kell tölteni.
    - **Fix réteg** – az egységár számítása rögzített mennyiséggel és kiterjesztett árösszegekkel különböző ár zárójelek esetén. A számlázási időszakban felszámított ár azt a kiterjesztett árat használja, amely megfelel annak a szintnek, ahol a számlázási mennyiség létezik.

7. A Cikktípus **mezőben** válassza ki a számlázási csoport cikkének típusát:

    - **Normál** – akkor válassza ezt az értéket, ha a mennyiség statikus.
    - **Használat** – akkor válassza ezt az értéket, ha a mérő vagy a felhasználás típusú cikkeknél ezt az értéket választja. Ha ezt az értéket választja, **·** **állítsa** Olvasás beállításra a Használat beolvasás beállítását, hogy a mérő vagy eszköz számlázási időszakának értékét (olvasását) adja meg. A felhasznált érték számítása az előző számlázási időszak és a beolvasott aktuális leolvasás alapján történik.
    - **Mérföldkő** – válassza ezt az értéket a Mérföldkőszámlázás funkció használatához. Ha ezt az értéket választja, akkor **a Mérföldkősablon** mezőben válassza ki a mérföldkősablont, ha használ egyet.
    - **Felhasználás** – ezzel az értékkel megadhatja a számlázási időszakban felhasznált értéket.

8. A Számla külön **beállítása** Igen beállítással **konszolidált** számlák és külön számlák kombinációját hozhatja létre ugyanannak a vevőnek. Egy vevőnek például öt számlázási ütemezése van. Mindhárom külön számlán lesz konszolidálva, a másik kettő azonban külön számlát igényel. Állítsa Nem **beállításra**, ha csak egy összesített számlát hoz létre a vevő számára.
9. Ha a számla létrehozásakor **automatikusan** **meg** kell újítani a következő számlázási időszak ismétlődő számlázási ütemezését, válassza az Automatikus megújítás lehetőséget. Állítsa Nem beállításra **a** számlázási ütemezés manuális megújításához. A Megújításonként **hozzáadni kívánt sorok mezőben** adja meg, hogy hány sort kell hozzáadni a megújításhoz.
10. **Az eszkaláció beállítása** **Igen** *beállítással eszkalációkat* (áremeléseket) alkalmazhat az ehhez a számlázási ütemezési csoporthoz társított számlázási ütemezésekre.
