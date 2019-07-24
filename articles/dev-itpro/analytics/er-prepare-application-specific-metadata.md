---
title: Alkalmazásspecifikus metaadatok előkészítése az RCS és ER számára
description: Ez a témakör azt mutatja be, hogyan kell előkészíteni az alkalmazásspecifikus metaadatokat a Regulatory Configuration Service (RCS) és az elektronikus jelentés (ER) számára.
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 289f901501a68319c9d85e993d8dfbfc3838a8eb
ms.sourcegitcommit: d940c7892b6caa6141b3bda8abf1c56e9df4687a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2019
ms.locfileid: "1726432"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a>Alkalmazásspecifikus metaadatok előkészítése az RCS számára

[!include[banner](../includes/banner.md)]

Ez a témakör a következő feladatok példáival nyújt útmutatót:

- [RCS-ben felhasználandó alkalmazás-metaadatok előkészítése](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Alkalmazás-metaadatokhoz való hozzáférés egy ER-konfiguráció használatával](#access-application-metadata-by-using-an-er-configuration)
- [Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>RCS-ben felhasználandó alkalmazás-metaadatok előkészítése

A következő eljárás ismerteti, hogy a Finance and Operations megoldásban a **Rendszergazda** vagy **Elektronikus jelentések fejlesztője** szerepkörrel rendelkező felhasználók hogyan hozhatnak létre olyan új Elektronikus jelentéskészítési konfigurációt, amely tartalmazza a Microsoft Dynamics 365 for Finance and Operations  alkalmazás metaadatait, és amely az ER modell-leképezési konfigurációk Regulatory Configuration Service (RCS) rendszerben való kialakításához használt. A példában létrehozott minta ER-modell-leképezési konfigurációval hozzá lehet férni a külkereskedelmi tranzakciókhoz.

A példában tegyük fel, hogy az RCS használatával olyan ER-megoldást szeretnének kialakítani a Finance and Operations alkalmazáshoz, amely a külkereskedelmi üzleti tartományból származó adatokat tartalmazó elektronikus dokumentumokat készít. Ha meg szeretné adni az ER-adatmodell és a szükséges adatok forrása közötti leképezést, akkor az RCS-ben hozzáféréssel kell rendelkeznie a Finance and Operations alkalmazás metaadataihoz. Ennek megfelelően az ER-megoldás tervezési folyamata során olyan új ER-metaadat-konfigurációt kell beállítani, amely a kiválasztott üzleti tartományok ER-jelentéseinek a létrehozásához pillanatnyilag szükséges összes metaadatot tartalmazza.

> [!NOTE]
> Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket bármilyen vállalatban végrehajthatja.

1. Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket. 
3. Kattintson a **Metaadat-konfigurációk** elemre.
4. Válassza a **Konfiguráció létrehozása** lehetőséget.
5. Írjon be egy nevet a legördülő párbeszédpanel **Név** mezőjébe. A példa esetében adja meg a **Külkereskedelmi metaadatok** szöveget.
6. Válassza a **Konfiguráció létrehozása** lehetőséget.
7. Válassza a **Tervező** lehetőséget.
8. Válassza a **Hozzáadás** lehetőséget.

    > [!NOTE]
    > Minden metaadatot kiválaszthat a teljes alkalmazáshoz, a kiválasztott modellekhez vagy a kiválasztott modulokhoz. Mindkét esetben a program automatikusan felveszi a következő metaadatokat: a rekordok, a felsorolások és a kiterjesztett adattípusok táblázatai (EDT). Ha további típusú metaadatokra van szüksége, akkor manuálisan kell őket felvennie.

Hozzá kell adni bizonyos külkereskedelmi tranzakciókkal kapcsolatos metaadatokat, és manuálisan ki kell választani a metaadatelemeket.

9. Jelölje be az **Adatforrás hozzáadása \> Táblához tartozó rekordok** elemet.
10. Az **Intrastat** értékére szűrjön a **Név** mezőben.
11. Az **Intrastat** táblarekordjának kiválasztása.
12. Válassza ki az **OK** lehetőséget.

A rekordok Intrastat-táblázatára vonatkozó metaadat-információkat kell hozzáadnia.

13. A fastruktúrában válassza ki a **Táblarekordok: Intrastat \> \>Kapcsolatok\> IntrastatCommodity (Táblarekordok: EcoResCategory)** részt.
14. Válassza a **Metaadatok hozzáadása** lehetőséget.

    > [!NOTE]
    > A kiválasztott rekordtábla szükséges kapcsolatainak metaadatait manuálisan kell felvenni.

15. **Adatforrás hozzáadása** lehetőség választása.
16. A **Számbavétel** kiválasztása.
17. Az **IntrastatDirection** értékére szűrjön a **Név** mezőben.
18. Válassza ki az **IntrastatDirection** felsorolásrekordot.
19. Válassza ki az **OK** lehetőséget.
20. Válassza a **Mentés** lehetőséget.
21. Zárja be a lapot.
22. A metaadat-konfiguráció piszkozatának befejezése:

    1. Válassza az **Állapot módosítása \>Teljes** lehetőséget.
    2. Válassza ki az **OK** lehetőséget.
    3. Válassza ki a befejezett verziót 1.

23. A metaadat-konfiguráció befejezett verziójának exportálása az alkalmazásból XML-fájlként:

    1. Válassza ki az **Exchange \> Export XML-fájlként** elemet.
    2. Válassza ki az **OK** lehetőséget.

A létrehozott ER-metaadat konfigurációt a rendszer **Foreign trade metadata. XML** fájlként menti. Ezt követően importálhatja az RCS-be, hogy a Finance and Operations megoldásban használható metaadatok forrásaként szerepeljen a külkereskedelmi üzleti tartományban. Az információ alapján meg tudja határozni az alkalmazás metaadatai és az ER-adatmodell közötti leképezést.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Alkalmazás-metaadatokhoz való hozzáférés egy ER-konfiguráció használatával

A következő eljárás bemutatja, hogy egy RCS felhasználó, aki rendelkezik a **Rendszergazda** vagy az **Elektronikus jelentéskészítési fejlesztő** szerepkörrel, megtervezhet egy új ER-modellhozzárendelést a Finance and Operations alkalmazás metaadatainak segítségével. Az alkalmazás metaadatainak egy olyan ER-metaadat konfigurációval érhető el, amely minta metaadatkészletet tartalmaz, amelyek a külföldi kereskedelmi tranzakciók eléréséhez használható.

Mielőtt teljesítené ezt az eljárást, végre kell hajtania a következő eljárásokat:

- [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [RCS-ben felhasználandó alkalmazás-metaadatok előkészítése](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket. 
3. Importálja a Finance and Operations alkalmazáshoz tartozó metaadatokat tartalmazó ER-metaadat konfigurációt, valamint a külkereskedelmi üzleti tartományhoz elektronikus dokumentumokat létrehozó konfigurációs konfigurációt. Létrehozta ezt az ER-metaadat konfigurációt, és exportálta XML-fájlként az [ RCS-ben felhasználandó alkalmazás-metaadatok előkészítése](#prepare-application-metadata-that-can-be-used-in-rcs) eljárásban a témakör korábbi részében.

    1. Kattintson a **Metaadat-konfigurációk** elemre.
    2. **Árfolyam** kijelölése.
    3. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    4. Tallózással válassza ki a **Foreign trade metadata.xml** fájlt.
    5. Válassza ki az **OK** lehetőséget.
    6. Zárja be a lapot.

4. Adatmodell-konfiguráció létrehozása:

    1. Válassza a **Jelentéskészítési konfigurációk** elemet.
    2. Válassza a **Konfiguráció létrehozása** lehetőséget.
    3. Írjon be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Külkereskedelmi modell**.
    4. Válassza a **Konfiguráció létrehozása** lehetőséget.
    5. Válassza a **Tervező** lehetőséget.
    6. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.

        1. A **Név** mezőbe írja be a következőt: **Gyökér**.
        2. Válassza a **Hozzáadás** lehetőséget.
    
    7. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.

        1. A **Név** mezőbe írja be a **Tranzakció** szöveget.
        2. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
        3. Válassza a **Hozzáadás** lehetőséget.
 
    8. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.

        1. A **Név** mezőbe írja be az **Árucikk-kód** szöveget.
        2. A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
        3. Válassza a **Hozzáadás** lehetőséget.

    9. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.

        1. A Név mezőbe írja be a következőt: **Számlázott összeg**.
        2. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
        3. Válassza a **Hozzáadás** lehetőséget.

    10. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.

        1. A **Név** mezőbe írja be a következőt: **Dátum**.
        2. A **Cikktípus** mezőben válassza ki a **Dátum** lehetőséget.
        3. Válassza a **Hozzáadás** lehetőséget.
 
    11. Válassza a **Hozzáadás \> Gyökérreferencia** elemet.
    12. Válassza ki az **OK** lehetőséget.
    13. Válassza a **Mentés** lehetőséget.
    14. Zárja be a lapot.
    15. Válassza az **Állapot módosítása \>Teljes** lehetőséget.
    16. Válassza ki az **OK** lehetőséget.

5. Modell-leképezési konfiguráció létrehozása:

    1. Válassza a **Konfiguráció létrehozása** lehetőséget.
    2. A legördülő párbeszédpanel **Új** mezőjébe írja be ezt: **Külkereskedelmi modell adatmodellen alapuló modell-leképezés**.
    3. A **Név** mezőbe írja be, hogy **Külkereskedelmi leképezés**.
    4. Válassza a **Konfiguráció létrehozása** lehetőséget.
    5. Válassza az **Előfeltételek** gyorslap **Szerkesztés** elemét.
    6. Válassza az **Új** lehetőséget.
    7. Az **Előfeltétel összetevő típusa** mezőben válassza ki a **Konfiguráció** lehetőséget.
    8. A **Külkereskedelmi metaadatok** konfiguráció kiválasztása.
    9. Válassza a **Mentés** lehetőséget. Figyelje meg, hogy a hivatkozás hozzáadódik a **Külkereskedelmi metaadat** konfiguráció 1. verziójához. A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.
    10. Zárja be a lapot.
    11. Válassza a **Tervező** lehetőséget.
    12. Válassza a **Tervező** lehetőséget.
    13. A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations \> Tábla rekordjai** csomópont.
    14. Válassza a **Gyökér hozzáadása** elemet.
    15. A **Név** mezőbe írja be a **Intrastat** szót.
    16. Az **Intrastat** táblarekordjainak kiválasztása.
    17. Válassza ki az **OK** lehetőséget.

        > [!NOTE]
        > Csak két tábla van felkínálva, mert csak két tábla lett hozzáadva a jelenleg használt metaadatok készletéhez.

    18. Válassza a **Bind** elemet.
    19. A fastruktúrában válassza ki az **Instrastat \> AmountMST** elemet.
    20. A fán jelölje be a **Transaction = Intrastat \> Számlázott összeg** lehetőséget.
    21. Válassza a **Bind** elemet.
    22. A fastruktúrában válassza ki az **Instrastat \> TransDate** elemet.
    23. A fastruktúrában válassza ki a **Tranzakció = Intrastat \> Dátum** elemet.
    24. Válassza a **Bind** elemet.
    25. A faszerkezetben válassza ki ezt: **Intrastat \> \>Kapcsolatok \> IntrastatCommodity \> Kód**.
    26. A fán jelölje be a **Transaction = Intrastat \> Árucikk kódja** lehetőséget.
    27. Válassza a **Bind** elemet.
    28. A **Validálás**kiválasztása.

        > [!NOTE]
        > Az érvényesítés befejezését követően az adatmodell elemeit az adatforrások olyan cikkeihez társította, amelyek leírása az alkalmazási metaadatoknak a hivatkozott ER-metaadat konfigurációkból származó beállításával történik.

    29. Válassza a **Mentés** lehetőséget.

A szükséges módon a meglévő metaadatok készletét a Finance and Operations alkalmazásban kibővítheti. Ezt követően exportálhatja a Finance and Operations alkalmazásból származó ER-metaadat konfiguráció új, kész verzióját, importálhatja a RCS-be, és frissítheti a konfigurált modell-hozzárendelési konfiguráció előfeltételeit, hogy az importált metaadat-konfiguráció egy új verziójára hivatkozzon.

> [!NOTE]
> Ez a módszer az alkalmazás metaadatainak információinak beolvasására az egyetlen elérhető módszer a helyileg telepített alkalmazások esetében (azaz amikor a helyi üzleti adatok \[LBD\] vagy telephelyi, telepítési modell használata történik a Finance and Operations alkalmazásban).

## <a name="access-application-metadata-by-using-connected-applications"></a>Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával

A következő eljárás bemutatja, hogy egy RCS felhasználó, aki rendelkezik a **Rendszergazda** vagy az **Elektronikus jelentéskészítési fejlesztő** szerepkörrel, megtervezhet egy új ER-modellhozzárendelést a Finance and Operations alkalmazás metaadatainak segítségével. Alkalmazás-metaadatokhoz való hozzáférés online RCS összekapcsolt alkalmazások használatával történik A minta ER-modell-hozzárendelést a külföldi kereskedelmi tranzakciók elérése érdekében konfigurálja a program.

A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az [ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárás lépéseit. Ha még nem végezte el a témakör lépéseit [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](#access-application-metadata-by-using-an-er-configuration) korábban a témakörben, nyissa meg az [Elektronikus jelentéskészítési feladat-útmutatók a Dynamics 365 for Finance and Operations 8.1 alkalmazáshoz](https://go.microsoft.com/fwlink/?linkid=2082739) lapot a következő ER-konfigurációk letöltéséhez és előzetes helyi mentéséhez: **Foreign trade metadata.xml**, **Foreign trade model.xml** és **Foreign trade mapping.xml**.


### <a name="get-required-er-configurations"></a>Szükséges elektronikus jelentéskészítés-konfigurációk lekérése

Ha már végrehajtotta az [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](#access-application-metadata-by-using-an-er-configuration) eljárásban megadott lépéseket korábban a témakörben, akkor az aktuális RCS már rendelkezik az összes szükséges ER konfigurációval (külkereskedelmi metaadatok, modell-hozzárendelési konfigurációk) az aktuális ER-példányban. Ebben az esetben ki lehet hagyni ezt az eljárást.

1. Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. Töltse be a **Foreign trade metadata.xml**, **Foreign trade model.xml** és **Foreign trade mapping.xml** konfigurációs fájlokat, a következő lépéseket ismételve meg mindegyikhez:

    1. **Exchange** kijelölése.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. **Tallózás** és fájl kiválasztása.
    4. Válassza ki az **OK** lehetőséget.

### <a name="register-the-connection-with-finance-and-operations"></a>Regisztráció és kapcsolódás a Finance and Operations alkalmazáshoz.

1. Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.
2. Kattintson az **Összekapcsolt alkalmazások** elemre.
3. Ellenőrizze, hogy a konfigurált alkalmazás Microsoft Azure alapú-e, és hogy a felhasználók számára elérhető-e általában a RCS. Az aktuális RCS felhasználó hozzá kell férjen a regisztráció alatt levő konfigurált alkalmazáshoz az alkalmazás felhasználóként olyan szerepkörben, amely lehetővé teszi az alkalmazás metaadatainak elérését.
4. Válassza az **Új** lehetőséget.
5. A **Név** mezőbe írja be **MyConnectedApp** a csatlakoztatott pályázat neveként.
6. Az **Alkalmazás** mezőben adja meg az alkalmazás URL-címét.
7. A **Bérlő** mezőben adja meg az alkalmazás szolgáltatóját.
8. Válassza a **Mentés** lehetőséget. 
9. Ha ellenőrzi a kapcsolatot a konfigurált alkalmazással, akkor a **Csatlakozás a távoli alkalmazáshoz** lapon kattintson a **Kattintson ide a kijelölt távoli alkalmazáshoz való kapcsolódáshoz** elemre. 
10. Válassza a **Kapcsolat ellenőrzése** lehetőséget konfigurált alkalmazáshoz való hozzáférés ellenőrzéséhez.
11. Válassza **Bezárás** lehetőséget.

Amikor az eljárás befejeződött és a kapcsolat ellenőrzése sikeres volt, a program frissíti a verziószámot és a bérlő adatait a konfigurált alkalmazáshoz az aktuális rácsban.

### <a name="review-the-existing-model-mapping-configuration"></a>Meglévő modell leképezés konfiguráció áttekintése

1. Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A fán válassza ki a **Foreign trade model \> Foreign trade mapping** elemet.
4. Válassza az **Előfeltételek** gyorslapot.

    > [!NOTE]
    > Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik. A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.

4. Válassza a **Tervező** lehetőséget.
5. Válassza a **Tervező** lehetőséget.
6. A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations \> Tábla rekordjai** csomópont.
7. Válassza a **Gyökér hozzáadása** elemet.
8. A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket.

    > [!NOTE]
    > Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik. A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.

9. Válassza a **Mégse** lehetőséget.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Csatlakoztatott alkalmazás társítása a modell-hozzárendeléshez

1. Válassza ki a **Szerkesztés** opciót.
2. A **Csatlakoztatott alkalmazás mezőben** válassza ki a **MyConnectedApp** alkalmazást.

    > [!NOTE]
    > Ez a leképezés a kiválasztott összekapcsolt alkalmazás metaadataira vonatkozik. Ha ugyanaz a leképezés a metaadatok konfigurációját és a kapcsolódó alkalmazást egyszerre hivatkozza, a program a csatlakoztatott alkalmazás metaadatait fogja használni.

3. Válassza a **Tervező** lehetőséget.
4. Válassza a **Tervező** lehetőséget.
5. A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations \> Tábla rekordjai** csomópont.
6. Válassza a **Gyökér hozzáadása** elemet.
7. A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket.

    > [!NOTE]
    > Ennél a pontnál már több, mint két alkalmazástábla szerepelt, mivel ez a leképezés a társított alkalmazás összes metaadatát felhasználja.

8. Válassza a **Mégse** lehetőséget.
9. A **Validálás**kiválasztása.

Az adatmodell elemeit az adatforrások olyan cikkeihez társítottuk, amelyek leírása az ehhez a leképezéshez hozzárendelt összekapcsolt alkalmazás metaadatainak részleteivel történik.

Ha egy másik verziójú alkalmazás metaadatainak használatával kell értékelnie ezt a modellt, akkor regisztráljon egy másik összekapcsolt alkalmazást, rendelje hozzá a modell hozzárendeléséhez, és ellenőrizze az új metaadatokkal összevetve.

## <a name="additional-resources"></a>További erőforrások

Azt is megteheti, hogy lejátssza az **RCS-ben felhasználandó alkalmazás-metaadatok előkészítése** feladat-útmutatót a Finance and Operations alkalmazásban, valamint az **Alkalmazás-metaadatokhoz való hozzáférés egy ER-konfiguráció használatával** és az **RCS és a hozzáférés modulban. az alkalmazás metaadatainak a csatlakoztatott alkalmazások** feladat-útmutatókat az RCS-ben. Ezeket a feladat-útmutatókat az [Elektronikus jelentéskészítési feladat-útmutatók a Dynamics 365 for Finance and Operations 8.1 alkalmazáshoz](https://go.microsoft.com/fwlink/?linkid=2082739) oldalról lehet letölteni.
