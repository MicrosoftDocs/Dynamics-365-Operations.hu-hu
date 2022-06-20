---
title: Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI-be való lehívásához
description: Ez a cikk bemutatja, hogy hogyan lehet az elektronikus jelentési (ER) konfigurációban rendezni a példány adatainak szolgáltatásokba történő átvitelét Power BI.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e6903513dec4da20dbc4463fbae6a406fc06e1a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896734"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI-be való lehívásához

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet az elektronikus jelentési (ER) konfigurációban rendezni a példány adatainak szolgáltatásokba történő átvitelét Power BI. Ez a cikk például az Intrastat-tranzakciókat átvihető üzleti adatként használja. A Power BI térképes megjelenítése ezt az Intrastat-tranzakciós adatot használja egy olyan nézet bemutatásához, amellyel egy vállalat importálási/exportálási tevékenységeit lehet elemezni a Power BI-jelentésben.

## <a name="overview"></a>Áttekintés

A Microsoft Power BI olyan szoftverek, szolgáltatások, alkalmazások és összekötők gyűjteménye, amelyek együtt dolgoznak azért, hogy a külső forrásokból származó adatokat koherens, vizuálisan élményt nyújtó és interaktív betekintéssé alakítsák. Elektronikus jelentés (ER) lehetővé teszi, hogy a felhasználók könnyen beállíthatják az adatforrásokat és megszervezhetik az adatok átvitelét a szolgáltatásból a Power BI szolgáltatásba. Az adatok átvitele fájlokban történik, OpenXML munkalap (Microsoft Excel-munkafüzet) formátumban. Az átvitt fájlok tárolása a Microsoft SharePoint Server felületén történik, amely ennek a célnak megfelelően lett konfigurálva. A tárolt fájlokat a Power BI olyan jelentések elkészítésére használja, amelyek tartalmaznak megjelenítőeszközöket (táblázatok, diagramok, térképek stb.). A Power BI-jelentések megosztásra kerülnek a Power BI-felhasználókkal, hozzáférésük a Power BI-irányítópulton és az alkalmazásoldalakon történik. Ez a témakör a következő feladatokat mutatja be:

- A Microsoft Dynamics 365 Pénzügy konfigurálása.
- Az ER-formátum konfigurációjának előkészítése a Finance adatainak beolvasásához.
- Az ER-környezet konfigurálása a Power BI szolgáltatásba történő adatátvitelhez.
- Az átvitt adatok felhasználása Power BI-jelentés létrehozására.
- A Power BI-jelentés elérhetővé tétele a Finance alkalmazásban.

## <a name="prerequisites"></a>Előfeltételek
Az ebben a példában olvasható példához a következő hozzáféréssel kell rendelkezik:

- Hozzáférés a következő szerepkörök egyikével:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- Hozzáférés a SharePoint-kiszolgálóhoz, amelyet az alkalmazással való használatra konfiguráltak
- Hozzáférés a Power BI-keretrendszerhez

## <a name="configure-document-management-parameters"></a>Dokumentumkezelés paraméterek konfigurálása
1. A **Dokumentumkezelés paraméterei** lapon állítsa be a hozzáférést ahhoz a SharePoint-kiszolgálóhoz, amelyet az a vállalat fog használni, amelybe Ön bejelentkezett (ebben a példában a DEMF vállalat).
2. Ellenőrizze a csatlakozást a SharePoint-kiszolgálóhoz, és győződjön meg róla, hogy rendelkezik hozzáféréssel.

    [![Dokumentumkezelés paramétereinek lapja.](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. Nyissa meg a konfigurált SharePoint-webhelyet. Hozzon létre egy új mappát, ahol az ER azokat az Excel-fájlokat fogja tárolni, amelynek üzleti adataira a Power BI-jelentéseknek szükségük van a Power BI-adatkészletek forrásaként.
4. Az alkalmazásban, a **Dokumentumtípusok** lapon hozzon létre egy új dokumentumtípust, amely az imént létrehozott SharePoint-mappa elérésére szolgál. Adja meg a **Fájlt** a **Csoport** mezőben és a **SharePoint** értékét a **Hely** mezőben, majd adja meg a SharePoint-mappa címét.

    [![Dokumentumtípusok lapja.](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása
1. Az **Elektronikus jelentések** munkaterületen kattintson az **Elektronikus jelentések paraméterei** hivatkozására.
2. A **Mellékletek** lapon jelölje be a **Fájl** dokumentumtípust az összes mezőnél.
3. Az **Elektronikus jelentések** munkaterületén aktiválja a megfelelő szolgáltatót; ehhez kattintson a **Beállítás aktívként** lehetőségre. További információkhoz játssza le az **ER-szolgáltató kijelölése** feladat-útmutatót.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>ER-adatmodell használata adatforrásként
A Power BI-jelentésekben használt üzleti adatok forrásának ER-adatmodellnek kell lennie. Ennek az adatmodellnek a feltöltése a ER-konfigurációk tárházából történik. További tudnivalókért lásd: [Elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](download-electronic-reporting-configuration-lcs.md), vagy játssza le az **ER-konfiguráció importálása a Lifecycle Services rendszerből** feladat-útmutatót. Válassza ki az **Intrastatot** azon adatmodellként, amelyet a program a kiválasztott ER-konfigurációk tárházából feltölt. (Ebben a példában a modell 1. verzióját használjuk.) Ezután érheti el az **Intrastat** ER-modell konfigurációját a **Konfigurációk** oldalon.

[![Intrastat ER-modellkonfiguráció a Konfigurációk lapon.](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Egy ER-formátumú konfiguráció kialakítása
Létre kell hoznia egy olyan új ER-formátum konfigurációt, amely az **Intrastat** adatmodellt használja az üzleti adatok forrásaként. Ennek a formátumkonfigurációnak OpenXML (Excel-fájl) formátumú, elektronikus dokumentumokként kell létrehoznia a kimeneti eredményeket. További információkhoz játssza le az **ER-konfiguráció létrehozása OPENXML formátumú jelentésekhez** feladat-útmutatót. Nevezze el az új konfiguráció **importálási / exportálási tevékenységeknek**, a következő ábrán látható módon. Használja a [ER-érték – importálás és exportálás részletei](https://download.microsoft.com/download/f/7/5/f755c0fd-025c-4aa9-920b-909abb8302ad/ER-data-import-and-export-details.xlsx) Excel-fájlt sablonként, amikor megtervezi az ER formátumát. (A formátumsablonok importálására vonatkozó további tudnivalókkal kapcsolatban játssza le a feladat-útmutatót.)

[![Importálási / exportálási tevékenységek konfigurálása.](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

Az **importálási / exportálási tevékenységek** formátumkonfigurációjának módosításához kövesse ezeket a lépéseket.

1. Kattintson a **Tervező** pontra.
2. A **Formátum** lapon adjon nevet a fájlelemnek ehhez a formátumhoz: **Excel kimeneti fájl**.

    [![Excel kimeneti fájlelem.](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. A **Leképezés** lapon adja meg annak az Excel-fájlnak a nevét, amely létrejön, amikor ezt a formátumot futtatják Konfigurálja az **importálás és exportálás részletei** érték megadásához szükséges, kapcsolódó kifejezést (az .xlsx fájlkiterjesztést a rendszer automatikusan hozzáadja).

    [![Formátumtervező.](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. Adjon hozzá egy új adatforrás-elemet ehhez a formátumhoz. (Erre a számbavételre a további adatok kötéséhez van szükség.)

    1. Adja a következő nevet az adatforrásnak: **direction\_enum**.
    2. Válassza ki az **Adatmodell számbavételét** az adatforrás típusaként.
    3. Lásd: **Irány** adatmodell számbavétele.

    [![direction_enum.](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. Végezze el az **Intrastat** adatmodell elemeinek és a kialakított formátum elemeinek összekötését, amint azt a következő ábra mutatja.

    [![A kötés elvégzése.](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

A futtatás után az ER-formátum létrehozza a kimeneti eredményeket Excel-formátumban. A rendszer elküldi az Intrastat-tranzakciók részleteit a kimeneti adatokhoz, és különválasztja ezeket olyan tranzakciókká, amelyek vagy importálási tevékenységeket vagy exportálási tevékenységeket írnak le. Kattintson a **Futtatás** elemre ahhoz, hogy kipróbálja az új ER-formátumot az Intrastat-tranzakciók listájával az **Intrastat** lapon (**Adó** &gt; **Nyilatkozatok** &gt; **Külkereskedelem** &gt; **Intrastat**).

[![Intrastat oldal.](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

A következő kimeneti eredmény jön létre. A fájl neve **Import and export details.xlsx**, ahogyan a formátum beállításainál megadta.

[![Import and export details.xlsx.](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>ER-célhely konfigurálása
Az ER-keretrendszert úgy kell konfigurálnia, hogy az új ER-formátumkonfigurálás kimeneti eredményeit speciális módon küldje el.

- A kimeneti eredményt a kiválasztott SharePoint-kiszolgáló mappájába kell elküldeni.
- A formátumkonfiguráció minden egyes végrehajtásakor ugyanannak az Excel-fájlnak egy új verziójának kell létrejönnie.

Az **Elektronikus jelentések** lapon (**Szervezet felügyelete** &gt; **Elektronikus jelentések**) kattintson az **Elektronikus jelentések célhelye** elemre, és adjon meg egy új célhelyet. A **Hivatkozás** mezőben válassza ki azt az **importálási / exportálási tevékenységek** formátumkonfigurációt, amelyet korábban létrehozott. Végezze el a következő lépéseket ahhoz, hogy az új fájl célhely-rekordját hozzáadja a hivatkozáshoz.

1. A **Név** mezőbe írja be a fájl célhelyének megnevezését.
2. A **Fájlnév** mezőben válassza ki az **Excel kimeneti fájl** nevet az Excel formátumú összetevőhöz.

Kattintson az új célhely rekordjának **Beállítások** gombjára. Ezután a **Célhely beállításai** párbeszédpanelben végezze el az alábbi lépéseket.

1. A **Power BI** lapon az **Engedélyezett** lehetőséget állítsa **Igen** értékre.
2. A **SharePoint** mezőben válassza ki azt a **Megosztott** dokumentumtípust, amelyet korábban létrehozott.

## <a name="schedule-execution-of-the-configured-er-format"></a>A beállított ER-formátum végrehajtási ütemezése
1. A **Konfigurációk** oldalon (**Szervezet felügyelete** &gt; **Elektronikus jelentések** &gt; **Konfigurációk**), a konfigurációs fában, válassza ki azt az **importálási / exportálási tevékenységekre** vonatkozó konfigurációt, amelyet korábban létrehozott.
2. Az 1.1 verzió állapotát módosítsa **Vázlatról** **Készre** , hogy ez a formátum használható legyen.

    [![Tevékenységek konfigurációjának importálása/exportálása a Konfigurációk lapon.](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. Válassza ki az **importálási / exportálási tevékenységekre** vonatkozó konfiguráció kész verzióját, majd kattintson a **Futtatásra**. Vegye figyelembe, hogy a konfigurált célhely az Excel formátumban létrehozott kimeneti eredményhez van hozzárendelve.
4. Állítsa a **Kötegelt feldolgozás** lehetőséget **Igenre** ahhoz, hogy ezt a jelentést felügyelet nélküli üzemmódban futtassa.
5. Kattintson az **Ismétlődésre** ahhoz, hogy beütemezze a kötegelt végrehajtás szükséges ismétlődését. Az ismétlődés határozza meg, hogy a frissített adatok milyen gyakran kerülnek a Power BI szolgáltatásba.

    [![Elektronikus jelentések paramétereinek párbeszédablaka.](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. A konfigurálás után az ER-jelentés végrehajtási feladatát a **Kötegelt feladatok** lapon találhatja meg (**Rendszerfelügyelet &gt; Lekérdezések &gt; Kötegelt feladatok**).

    [![Kötegelt feladatok lapja.](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. Amikor ez a feladat először fut, a célhely létrehoz egy új Excel-fájlt a konfigurált névvel, a kiválasztott SharePoint-mappában. Minden későbbi alkalommal, amikor ez a feladat fut, a célhely létrehozza ennek az Excel-fájlnak egy új verzióját.

    [![Az Excel-fájl új verziója.](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Power BI-adatkészlet létrehozása az ER-formátum kimeneti eredményeinek felhasználásával
1. Jelentkezzen be a Power BI szolgáltatásba, és nyisson meg egy meglévő Power BI-csoportot (munkaterület), vagy hozzon létre egy új csoportot. Kattintson a **Hozzáadás** elemre a **Fájlok** alatt, az **Adatok importálása vagy csatlakozás adatokhoz** szakaszban, vagy kattintson a pluszjelre (**+**) az **Adatkészletek** mellett a bal oldali ablakban.

    [![Adatkészlet létrehozása.](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. Válassza ki a **SharePoint – Csoportwebhelyek** lehetőséget, majd adja meg az Ön által használt a SharePoint-kiszolgáló elérési útját (`https://ax7partner.litware.com` ebben a példában).
3. Menjen a **/Megosztott dokumentumok/GER-adatok/PowerBI** mappára, és válassza ki azt az Excel-fájlt, amelyet az új Power BI-adatkészlet adatforrásaként létrehozott.

    [![Az Excel-fájl kiválasztása.](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. Kattintson a **Csatlakozásra**, majd kattintson az **Importálás** lehetőségre. Létrejön az új adatkészlet, amely a kiválasztott Excel-fájlon alapul. Az adatkészlet automatikusan hozzáadódik az újonnan létrehozott irányítópulthoz.

    [![Adatkészlet az irányítópulton.](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. Állítsa be úgy a frissítési ütemezést, hogy ez az adatkészlet időszakos frissítést kényszerítsen ki. Az időszakos frissítések lehetővé teszik az ER-jelentés időszakos végrehajtása révén érkező, új üzleti adatok felhasználását, az Excel-fájlnak a SharePoint-kiszolgálón létrehozott új változatai segítségével.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Power BI-jelentés létrehozása az új adatkészlet segítségével
1. Kattintson az **Importálás és exportálás részletei** Power BI-adatkészletre, amelyet létrehozott.
2. Állítsa be a megjelenítést. Például válassza ki a **Kitöltött térkép** megjelenítést, és állítsa be a következőképpen:

    - Rendelje hozzá a **OrszágEredet** adatkészlet-mezőt a térképes megjelenítés **Hely** mezőjéhez.
    - Rendelje hozzá a **Mennyiség** adatkészlet-mezőt a térképes megjelenítés **Színtelítettség** mezőjéhez.
    - Adja hozzá a **Tevékenység** és az **Év** adatkészlet-mezőt a térképes megjelenítés **Szűrők** mezőgyűjteményéhez.

3. Mentse el a Power BI-jelentést **Importálás és exportálás részletezését tartalmazó jelentés** formájában.

    [![Importálás és exportálás részletezését tartalmazó jelentés.](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    Megjegyzés: a térképen az Excel-fájl megtalálható országok/régiók láthatók (Ausztria és Svájc ebben a példában). Ezeknek az országoknak/régióknak színei a számlázott összegek arányát is jelzik.

4. Frissítse az Intrastat-tranzakciók listáját. Az Olaszországból származó exporttranzakció is hozzáadásra kerül.

    [![Intrastat-tranzakciók listája.](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. Várjon, amíg az ER-jelentés következő, ütemezett végrehajtására és a Power BI-adatkészlet következő, ütemezett frissítésére sor nem kerül. Ezután tekintse át a Power BI-jelentést (válassza ki, hogy csak az importálás-tranzakciók jelenjenek meg). A frissített térkép most már mutatja Olaszországot.

    [![Frissített térkép.](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>Hozzáférés a Power BI jelentéshez a Finance modulban
A Power BI integrációjának beállítása. További tudnivalókért lásd: [A Power BI integráció konfigurálása a munkaterületekhez](configure-power-bi-integration.md).

1. Az **Elektronikus jelentések** munkaterületlapon, amely támogatja a Power BI-integrációt (**Szervezet felügyelete** &gt; **Munkaterületek** &gt; **Elektronikus jelentési munkaterület**), kattintson a **Lehetőségek** &gt; **Jelentések katalógusának megnyitása** lehetőségre.
2. Válassza ki az Ön által létrehozott, az **Importálás és exportálás részletei** Power BI-jelentést ahhoz, hogy a jelentést a kijelölt lapon teendőként jelenítse meg.
3. Kattintson a teendőre azon lap megnyitásához, amely megjeleníti az Ön által a Power BI szolgáltatásban megtervezett jelentést.

    [![Importálás és exportálás részletezését tartalmazó jelentés, amelyet a Power BI rendszerében készítettek.](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
