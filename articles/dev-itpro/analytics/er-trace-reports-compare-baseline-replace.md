---
title: A létrehozott ER-jelentések eredményeinek nyomon követésében és a kiindulási értékekkel való összehasonlításukban végzett fejlesztések
description: Ez a témakör az ER alaptervfunkcióban végzett fejlesztésekről tájékoztat a Microsoft Dynamics 365 for Finance and Operations 10.0.3-as (2019. júniusi) verziójában.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 222a415f686c8028fc2a414f97eed0291d850ae7
ms.sourcegitcommit: 9917df8c0c9320955c61186cd922c8df894a4f25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700682"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>A létrehozott ER-jelentések eredményeinek nyomon követésében és a kiindulási értékekkel való összehasonlításukban végzett fejlesztések

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a fejlesztések első körét, amelyet az Elektronikus jelentéskészítés (ER) keretrendszer alaptervfunkciójában végeztek. Ezek a fejlesztések a Microsoft Dynamics 365 for Finance and Operations 10.0.3-as (2019. júniusi) és a újabb verziókban érhetők el.

## <a name="automate-the-setting-of-baseline-rules"></a>Alaptervszabályok beállításának automatizálása

[A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md) témakör bemutatja, hogy az ER-keretrendszer konfigurálása segítségével hogyan lehet információt gyűjteni az ER formátum-végrehajtásokról, és értékelni a végrehajtások eredményeit. Az ebben a témakörben szereplő példa bemutatja, hogy milyen lépéseket kell végrehajtani.

Az alábbiakban látható néhány ilyen lépés:

- Futtasson egy ER-formátumot egy kimenő fájl létrehozásához, és tárolja a fájlt helyileg.
- Adja hozzá a helyileg tárolt fájlt a alapterv mellékleteként, amelyet egy ER-formátumhoz hozzáadott.
- Konfigurálja az alaptervszabályt a hozzáadott alaptervhez. Ez a konfiguráció a következő lépéseket tartalmazza:

    - Adja meg a kimenő fájlok előállításához használt, ER-formátumelemet.
    - Válassza ki a létrejövő kimenő fájlra hivatkozó mellékletet.

> [!NOTE]
> Ezeket a lépéseket manuálisan kell elvégezni, még akkor is, ha az új ER-lehetőségek lehetővé teszik, hogy automatizáltak legyenek. Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Példa: Alaptervszabályok beállításának automatizálása

A példa lépéseinek végrehajtásához először végre kell hajtania [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a alaptervértékekkel](er-trace-reports-compare-baseline.md) témakör példájának lépéseit, egészen az „Új alapterv hozzáadása egy megtervezett ER-formátumhoz” szakaszig.

### <a name="review-added-baseline"></a>Hozzáadott alapterv áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. Válassza az **Alaptervek** lehetőséget.

    > [!NOTE]
    > Az **Alaptervek** gomb a műveleti ablaktáblán csak akkor elérhető, ha a **Futtatás hibakeresési módban** felhasználói ER-paraméter be van kapcsolva a jelenlegi vállalathoz.

A alaptervet a a rendszer hozzáadta a kiválasztott **ER-alaptervek tanulási formátuma** formátumhoz, de a alaptervszabályokat még nem adták hozzá az adott alaptervhez.

![Elektronikus jelentéskészítés alaptervformátumai oldal](media/GER-BaselineSample-AddBaseline2.PNG "Képernyőkép – Elektronikus jelentéskészítés alaptervformátumai oldal")

### <a name="make-a-new-baseline-rule"></a>Új alaptervszabály létrehozása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.
3. A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.
4. A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
5. Az **Azonosító megadása** mezőbe írja az **1** értéket.
6. A **Alaptervfájlok létrehozása** beállítást állítsa **Igen** értékre.
7. Válassza ki az **OK** lehetőséget.

    ![Elektronikus jelentés paraméterei párbeszédpanel](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Képernyőkép – Elektronikus jelentés paraméterei párbeszédpanel")

8. Válassza az **Alaptervek** lehetőséget.

    ![Elektronikus jelentéskészítés alaptervformátumai oldal](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Képernyőkép – Elektronikus jelentéskészítés alaptervformátumai oldal")

    A létrejövő kimenő fájl automatikusan a végrehajtott ER-formátum alaptervéhez van csatolva. A alaptervszabály automatikusan hozzáadódott ehhez az alaptervhez, és a csatolt fájlra mutató hivatkozást is tartalmaz.

9. A **Név** mezőbe írja be: **1. alapterv**.
10. Az **Fájlnév-maszk** mezőbe írja be a következőt: **.xml**.
11. Válassza a **Mentés** lehetőséget.

### <a name="run-the-format"></a>A formátum futtatása

Most már készen áll [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a alaptervértékekkel](er-trace-reports-compare-baseline.md) témakör példájának fennmaradó lépéseit megtenni, a „Megtervezett ER-formátum futtatása, és a napló áttekintése az eredmények elemzéséhez” szakasztól kezdve.

> [!NOTE]
> Amikor törli az automatikusan hozzáadott alaptervszabályt az **Alaptervek** gyorslapon, a hivatkozott mellékletet nem törli automatikusan a program.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Úgy konfigurálja az alaptervet, hogy figyelmen kívül hagyja az ER-kimenet állandóan változó részeit.

Ha egy ER-formátum úgy van kialakítva, hogy a formátum futtatásakor módosuló adatokat tartalmazzon, akkor a formátumnak kötelezően az ER alaptervfunkcióját kell alkalmaznia a létrejövő eredmények és a kiindulási érétkek összehasonlítására. Például előfordulhat, hogy az információ a dátumot és időpontot, vagy a létrehozott dokumentum egyedi azonosítóját különböző formátumban dolgozza fel (globálisan egyedi azonosító \[GUID\] stb.). Az új ER-lehetőséges segítségével az alaptervszabályokat úgy konfigurálhatja, hogy figyelmen kívül hagyja az ER-formátum módosítható elemeit, amikor a formátumot a kiindulási értékek és a formátum végrehajtási eredményeinek összehasonlítása céljából futtatták. Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Példa: Alapterv konfigurálása úgy, hogy figyelmen kívül hagyja az ER-kimenet állandóan változó részeit

A példa lépéseinek végrehajtásához először végre kell hajtania [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md) témakör példájának lépéseit.

### <a name="modify-a-configured-er-format"></a>Konfigurált ER-formátum módosítása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.
3. A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.
4. Válassza a **Tervező** lehetőséget.
5. A fában válassza ki a **Output\\Document** csomópontot.
6. Válassza a **Hozzáadás** lehetőséget.
7. A fastruktúra legördülő párbeszédpaneljében válassza az **XML\\Attribútum** elemet.
8. A **Név** mezőbe írja be a következőt: **ProcessingDateTime**.
9. Válassza ki az **OK** lehetőséget.
10. A **Hozzárendelés** lap fastruktúrájában válassza ki a **Kimenet\\Dokumentum\\ProcessingDateTime** elemet.
11. Válassza a **Képlet szerkesztése** elemet.
12. A **Képlet** mezőben adja meg a következő kifejezést: **DATETIMEFORMAT(NOW(), "O")**
13. Válassza a **Mentés** parancsot, majd válassza a **Teszt** elemet.
14. A konfigurált kifejezés újrateszteléséhez válassza újra a **Teszt** elemet.

    ![Képlettervező lap](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Képernyőkép – Képlettervező lap")

    > [!NOTE]
    > A **Teszteredmények** lap mutatja, hogy a konfigurált kifejezés más dátumot és időpontot ad vissza, amikor a lehívás történik.

15. Zárja be a **Képlettervező** lapot, majd válassza a **Mentés** gombot.

    ![Formátumtervező lap](media/GER-BaselineSample-FormatMappingDesign2.PNG "Képernyőkép – Formátumtervező lap")

16. Zárja be a **Formátumtervező** lapot.

### <a name="remove-an-existing-baseline-rule"></a>Létező alaptervszabály eltávolítása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. Válassza az **Alaptervek** lehetőséget.
3. Az alaptervek listájában válassza ki azt az alaptervet, amely az **ER-kiindulások tanulási formátuma** formátumra van beállítva.
4. Az **Alaptervek** gyorslapon válassza a **Törlés** parancsot a korábban konfigurált alaptervszabály eltávolításához.

![Elektronikus jelentéskészítés formátum-alaptervei oldal](media/GER-BaselineSample-AddBaseline3.PNG "Képernyőkép – Elektronikus jelentéskészítés formátum-alaptervei oldal")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>A megtervezett ER-formátum kötéseihez tartozó helyettesítések meghatározása

1. Válassza a **Konfigurációk** lap **Helyettesítések** gyorslapján az **Összetevők kiválasztása** elemet.
2. A formátum-összetevők fastruktúrájában bontsa ki a **Kimenet** elemet, majd a **Kimenet\\Dokumentum** pontot, és jelölje be a **Kimenet\\Dokumentum\\ProcessingDateTime** jelölőnégyzetet.

    ![Összetevők kiválasztása párbeszédpanel](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Képernyőkép – Összetevők kiválasztása párbeszédpanel")

3. Válassza ki az **OK** lehetőséget.

![Elektronikus jelentéskészítés formátum-alaptervei oldal](media/GER-BaselineSample-AddBaseline4.PNG "Képernyőkép – Elektronikus jelentéskészítés formátum-alaptervei oldal")

A kiválasztott ER-formátum-összetevő hozzá van adva az összetevők listájához a **Helyettesítések** gyorslapon. Ha a program hibakeresési módban futtatja az ER alapformátumát, akkor az egyes összetevők formátumának kötését a program a **Kötés** oszlopban szereplő kötéssel helyettesíti. Ha módosítani szeretné a **Helyettesítések** gyorslapon felsorolt összetevő alapértelmezett kötését, válassza a **Szerkesztés** parancsot.

### <a name="make-a-new-baseline-rule"></a>Új alaptervszabály létrehozása

Kövesse az aktuális témakör korábbi, „Példa: Kiindulási szabályok beállításának automatizálása” szakaszának lépéseit. Egy értesítés figyelmeztet arra, hogy a kimenő fájl az alapterv-beállítások alapján lett létrehozva, és a formátum kötésének kényszerű helyettesítése történt.

![Értesítés a konfigurációk lapon](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Képernyőkép – Értesítés a konfigurációk lapon")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>A formátumkötések helyettesítésével kapcsolatos figyelmeztetések figyelmen kívül hagyása

Meghatározott ER-paraméterek beállításával figyelmen kívül hagyhatja a formátumkötések helyettesítésével kapcsolatos figyelmeztetéseket. Ez a figyelmen kívül hagyás akkor lehet hasznos, ha a kötések formátumát egy felügyelet nélküli módban cseréli le a Regression Suite Automation Tool eszköz használatával. Ebben az esetben a figyelmeztetés a futó teszteset meghibásodását eredményezheti.

1. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, válassza a **Felhasználói paraméterek** lehetőséget.
2. Állítsa az **Alaptervvel kapcsolatos figyelmeztetések figyelmen kívül hagyása** beállítást **Igen** értékre, majd válassza az **OK** lehetőséget.

![Felhasználói paraméterek párbeszédpanel](media/GER-BaselineSample-ERUserParameters1.png "Képernyőkép – Felhasználói paraméterek párbeszédpanel")

### <a name="review-the-generated-baseline-file"></a>A létrehozott alaptervfájl ellenőrzése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. Válassza az **Alaptervek** lehetőséget.
3. Válassza a **Mellékletek** lehetőséget.

    ![Mellékletek lap](media/GER-BaselineSample-AttachedBaselineFile.PNG "Képernyőkép – mellékletek lap")

    > [!NOTE]
    > A létrehozott fájl tartalmazza a feldolgozás dátumának és időpontját szövegét (**"#"**), amely a hozzáadott alaptervszabályban konfigurált kötésből származik, nem pedig a formátum kötéséből.

4. Zárja be a **Mellékletek** lapot.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>A tervezett ER formátum futtatása és a napló áttekintése az eredmények elemzéséhez

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.
3. A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.
4. A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
5. Az **Azonosító megadása** mezőbe írja az **1** értéket.
6. Válassza ki az **OK** lehetőséget.
7. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk hibakeresési naplói**.

A végrehajtási napló a megadott alapterv és a létrejövő fájl összehasonlításának eredményeiről tartalmaz információkat. A napló azt jelzi, hogy a létrejövő fájl és az alapterv egyenlő, még akkor is, ha a végrehajtott formátum tartalmazza a kimenő fájlban folyamatosan változó dátum- és időpontértékének megadására vonatkozó kötést.

> [!NOTE]
> Annak ellenére, hogy a kimenő fájl olyan alaptervi beállításokkal lett létrehozva, amelyek a formátum kötéseinek helyettesítését kényszerítik, nem kap figyelmeztetést a helyettesítéssel kapcsolatban.

## <a name="exchange-baseline-settings-between-environments"></a>Alaptervi beállítások kicserélése környezetek között

### <a name="export-baseline-settings"></a>Alaptervi beállítások exportálása

Az új ER-funkciók lehetővé teszik a kiválasztott ER-formátum alaptervi beállításainak exportálását az aktuális Finance and Operations környezetből, és tárolásukat XML-fájlként. 

Az alaptervi beállítások exportálásához kattintson az **Elektronikus jelentéskészítés formátumának alaptervei** oldalon az **Exportálás** elemre.

### <a name="import-baseline-settings"></a>Kiindulási beállítások importálása

Az exportált alaptervi beállításokat másik Finance and Operations környezetbe importálhatja. A környezetet előbb ER-formátumként kell importálni. Ezt követően importálhatja az alaptervi beállításokat.

Ha egy helyileg tárolt XML-fájlból szeretne alaptervi beállításokat importálni, válassza az **Elektronikus jelentéskészítés formátumának alaptervei** lapot, válassza az **importálás** lehetőséget, majd válassza a **Tallózás** lehetőséget az XML-fájl kiválasztásához.

![Alaptervi beállítások importálása párbeszédpanel](media/GER-BaselineSample-ImportBaseline1.PNG "Képernyőkép – Alaptervi beállítások importálása párbeszédpanel")

Ha a Microsoft SharePoint Server felületén tárolt XML-fájlból szeretne alaptervi beállításokat importálni, az aktuális Dokumentumkezelési beállítások és a kiválasztott dokumentumtípus alapján, válassza az **Elektronikus jelentéskészítés formátumának alaptervei** oldalon az **Importálás forrásból** lehetőséget. Majd válassza ki a dokumentumtípust és az XML-fájlt. A SharePoint-mappához való hozzáféréshez szükséges dokumentumtípust be kell állítani előre.

![Importálás forrásból párbeszédpanel](media/GER-BaselineSample-ImportBaseline2.PNG "Képernyőkép – Importálás forrásból párbeszédpanel")

> [!NOTE]
> A Feladatrögzítő segítségével rögzítheti a szükség dokumentumtípus kiválasztásának lépéseit és a fájlnevet az **Importálás forrásból** párbeszédpanelben. Ily módon a szükséges alaptervi beállításokat SharePoint Server felületén tárolhatja, és automatikusan importálhatja őket egy feladatrögzítés lejátszásával a Regression Suite Automation Tool használatával futtatott automatizált tesztek futtatásakor.

## <a name="additional-resources"></a>További erőforrások

- [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md)
- [Feladatrögzítő](../user-interface/task-recorder.md)
