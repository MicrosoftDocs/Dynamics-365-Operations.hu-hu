---
title: "Elektronikus jelentéskészítés adatok a Power BI-be történő lehívásához"
description: "Ez a témakör bemutatja, hogyan használható az elektronikus jelentési (ER) konfiguráció arra, hogy adatokat vigyen át a Finance and Operations alkalmazásból a Power BI szolgáltatásokba. A jelen témakörben bemutatott példa Intrastat-tranzakciókat alkalmaz olyan üzleti adatokként, amelyeket át kell adni. A Power BI térképes megjelenítése ezt az Intrastat-tranzakciós adatot használja egy olyan nézet bemutatásához, amellyel egy vállalat importálási/exportálási tevékenységeit lehet elemezni a Power BI-jelentésben."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 6be91dfc02b728ffdf0f9d3baf1d41d3d2c10fea
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="configure-electronic-reporting-to-pull-data-into-power-bi"></a>Elektronikus jelentéskészítés adatok a Power BI-be történő lehívásához

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogyan használható az elektronikus jelentési (ER) konfiguráció arra, hogy adatokat vigyen át a Finance and Operations alkalmazásból a Power BI szolgáltatásokba. A jelen témakörben bemutatott példa Intrastat-tranzakciókat alkalmaz olyan üzleti adatokként, amelyeket át kell adni. A Power BI térképes megjelenítése ezt az Intrastat-tranzakciós adatot használja egy olyan nézet bemutatásához, amellyel egy vállalat importálási/exportálási tevékenységeit lehet elemezni a Power BI-jelentésben.

<a name="overview"></a>Áttekintés
--------

A Microsoft Power BI olyan szoftverek, szolgáltatások, alkalmazások és összekötők gyűjteménye, amelyek együtt dolgoznak azért, hogy a külső forrásokból származó adatokat koherens, vizuálisan élményt nyújtó és interaktív betekintéssé alakítsák. Az elektronikus jelentések (ER) segítségével a Microsoft Dynamics 365 Finance and Operations felhasználói könnyen konfigurálhatnak adatforrásokat és vihetnek át adatok a Finance and Operations alkalmazásból a Power BI alkalmazásnak. Az adatok átvitele fájlokban történik, OpenXML munkalap (Microsoft Excel-munkafüzet) formátumban. Az átvitt fájlok tárolása a Microsoft SharePoint Serveren történik, amely ennek a célnak megfelelően lett konfigurálva. A tárolt fájlokat a Power BI olyan jelentések elkészítésére használja, amelyek tartalmaznak megjelenítőeszközöket (táblázatok, diagramok, térképek stb.). A Power BI jelentések megosztásra kerülnek a Power BI felhasználókkal, hozzáférésük a Power BI irányítópulton és a Finance and Operations oldalakon történik. Ez a témakör az alábbi feladatokat magyarázza el:

-   A Finance and Operations konfigurálása.
-   Az ER-formátum konfigurációjának előkészítése a Finance and Operations adatainak beolvasásához.
-   Az ER-környezet konfigurálása a Power BI-ba történő adatátvitelhez.
-   Az átvitt adatok felhasználása Power BI-jelentés létrehozására.
-   A Power BI-jelentés elérhetővé tétele a Finance and Operations alkalmazásban.

## <a name="prerequisites"></a>Előfeltételek
A jelen témakörben szereplő példa elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

-   Hozzáférés a Finance and Operations alkalmazáshoz a következő szerepkörök egyikével:
    -   Elektronikus jelentések fejlesztője
    -   Elektronikus jelentések funkcióival foglalkozó konzulens
    -   Rendszergazda
-   Hozzáférés a SharePoint-kiszolgálóhoz, amelyet a Finance and Operations alkalmazással való használatra konfiguráltak
-   Hozzáférés a Power BI keretrendszerhez

## <a name="configure-document-management-parameters"></a>Dokumentumkezelés paraméterek konfigurálása
1.  A **Dokumentumkezelés paraméterei** lapon állítsa be a hozzáférést ahhoz a SharePoint-kiszolgálóhoz, amelyet az a vállalat fog használni, amelybe Ön bejelentkezett (ebben a példában a DEMF vállalat).
2.  Ellenőrizze a csatlakozást a SharePoint-kiszolgálóhoz, és győződjön meg róla, hogy rendelkezik hozzáféréssel. [![Dokumentumkezelés paramétereinek lapja](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)
3.  Nyissa meg a konfigurált SharePoint-webhelyet. Hozzon létre egy új mappát, ahol az ER azokat az Excel-fájlokat fogja tárolni, amelynek üzleti adataira a Power BI-jelentéseknek szükségük van a Power BI-adatkészletek forrásaként.
4.  A Finance and Operations alkalmazásban, a **Dokumentumtípusok** lapon hozzon létre egy új dokumentumtípust, amely az imént létrehozott SharePoint-mappa elérésére szolgál. Adja meg a **Fájlt** a **Csoport** mezőben és a **SharePointot** a **Hely** mezőben, majd adja meg a SharePoint-mappa címét. [![Dokumentumtípusok lapja](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása
1.  Az **Elektronikus jelentések** munkaterületen kattintson az **Elektronikus jelentések paraméterei** hivatkozására.
2.  A **Mellékletek** lapon jelölje be a **Fájl** dokumentumtípust az összes mezőnél.
3.  Az **Elektronikus jelentések** munkaterületén aktiválja a megfelelő szolgáltatót; ehhez kattintson a **Beállítás aktívként** lehetőségre. További információkhoz játssza le az **ER-szolgáltató kijelölése** feladat-útmutatót.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>ER-adatmodell használata adatforrásként
A Power BI-jelentésekben használt üzleti adatok forrásának ER-adatmodellnek kell lennie. Ennek az adatmodellnek a feltöltése a ER-konfigurációk tárházából történik. További tudnivalókért lásd: [Elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](download-electronic-reporting-configuration-lcs.md), vagy játssza le az **ER-konfiguráció importálása a Lifecycle Services rendszerből** feladat-útmutatót. Válassza ki az **Intrastatot** azon adatmodellként, amelyet a program a kiválasztott ER-konfigurációk tárházából feltölt. (Ebben a példában a modell 1. verzióját használjuk.) Ezután érheti el az **Intrastat** ER-modell konfigurációját a **Konfigurációk** oldalon. [![Konfigurációs oldal](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Egy ER-formátumú konfiguráció kialakítása
Létre kell hoznia egy olyan új ER-formátum konfigurációt, amely az **Intrastat** adatmodellt használja az üzleti adatok forrásaként. Ennek a formátumkonfigurációnak OpenXML (Excel-fájl) formátumú, elektronikus dokumentumokként kell létrehoznia a kimeneti eredményeket. További információkhoz játssza le az **ER-konfiguráció létrehozása OPENXML formátumú jelentésekhez** feladat-útmutatót. Nevezze el az új konfiguráció **importálási / exportálási tevékenységeknek**, a következő ábrán látható módon. Használja a [ER-érték – importálás és exportálás részletei](https://go.microsoft.com/fwlink/?linkid=845208) Excel-fájlt sablonként, amikor megtervezi az ER formátumát. (A formátumsablonok importálására vonatkozó további tudnivalókkal kapcsolatban játssza le a feladat-útmutatót.) [!["Importálási / exportálási tevékenységek konfigurálása](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png) Az **importálási/exportálási tevékenységek** formátumkonfigurációjának módosításához kövesse ezeket a lépéseket.

1.  Kattintson a **Tervező** pontra.
2.  A **Formátum** lapon adjon nevet a fájlelemnek ehhez a formátumhoz: **Excel kimeneti fájl**. [![Excel kimeneti fájlelem](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)
3.  A **Leképezés** lapon adja meg annak az Excel-fájlnak a nevét, amely létrejön, amikor ezt a formátumot futtatják Konfigurálja az **importálás és exportálás részletei** érték megadásához szükséges, kapcsolódó kifejezést (az .xlsx fájlkiterjesztést a rendszer automatikusan hozzáadja). [![Formátumtervező](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Adjon hozzá egy új adatforrás-elemet ehhez a formátumhoz. (Erre a számbavételre a további adatok kötéséhez van szükség.)
    1.  Adja a következő nevet az adatforrásnak: **direction\_enum**.
    2.  Válassza ki az **Adatmodell számbavételét** az adatforrás típusaként.
    3.  Lásd: **Irány** adatmodell számbavétele.

    [![direction\_enum](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Végezze el az **Intrastat** adatmodell elemeinek és a kialakított formátum elemeinek összekötését, amint azt a következő ábra mutatja. [![A kötés elvégzése](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

A futtatás után az ER-formátum létrehozza a kimeneti eredményeket Excel-formátumban. A rendszer elküldi az Intrastat-tranzakciók részleteit a kimeneti adatokhoz, és különválasztja ezeket olyan tranzakciókká, amelyek vagy importálási tevékenységeket vagy exportálási tevékenységeket írnak le. Kattintson a **Futtatás** elemre ahhoz, hogy kipróbálja az új ER-formátumot az Intrastat-tranzakciók listájával az **Intrastat** lapon (**Adó** &gt; **Nyilatkozatok** &gt; **Külkereskedelem** &gt; **Intrastat**). [![Intrastat oldal](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png) A következő kimeneti eredmény jön létre. A fájl neve **Import and export details.xlsx**, ahogyan a formátum beállításainál megadta. [![Import and export details.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>ER-célhely konfigurálása
Az ER-keretrendszert úgy kell konfigurálnia, hogy az új ER-formátumkonfigurálás kimeneti eredményeit speciális módon küldje el.

-   A kimeneti eredményt a kiválasztott SharePoint-kiszolgáló mappájába kell elküldeni.
-   A formátumkonfiguráció minden egyes végrehajtásakor ugyanannak az Excel-fájlnak egy új verziójának kell létrejönnie.

Az **Elektronikus jelentések** lapon (**Szervezet felügyelete** &gt; **Elektronikus jelentések**) kattintson az **Elektronikus jelentések célhelye** elemre, és adjon meg egy új célhelyet. A **Hivatkozás** mezőben válassza ki azt az **importálási / exportálási tevékenységek** formátumkonfigurációt, amelyet korábban létrehozott. Végezze el a következő lépéseket ahhoz, hogy az új fájl célhely-rekordját hozzáadja a hivatkozáshoz.

1.  A **Név** mezőbe írja be a fájl célhelyének megnevezését.
2.  A **Fájlnév** mezőben válassza ki az **Excel kimeneti fájl** nevet az Excel formátumú összetevőhöz.

Kattintson az új célhely rekordjának **Beállítások** gombjára. Ezután a **Célhely beállításai** párbeszédpanelben végezze el az alábbi lépéseket.

1.  A **Power BI** lapon az **Engedélyezett** lehetőséget állítsa **Igenre**.
2.  A **SharePoint** mezőben válassza ki azt a **Megosztott** dokumentumtípust, amelyet korábban létrehozott.

## <a name="schedule-execution-of-the-configured-er-format"></a>A beállított ER-formátum végrehajtási ütemezése
A **Konfigurációk** oldalon (**Szervezet felügyelete** &gt; **Elektronikus jelentések** &gt; **Konfigurációk**), a konfigurációs fában, válassza ki azt az **importálási / exportálási tevékenységekre** vonatkozó konfigurációt, amelyet korábban létrehozott. Az 1.1 verzió állapotát módosítsa **Vázlatról** **Készre** , hogy ez a formátum használható legyen. [![Konfigurációs oldal](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png) Válassza ki az **importálási / exportálási tevékenységekre** vonatkozó konfiguráció kész verzióját, majd kattintson a **Futtatás** elemre. Vegye figyelembe, hogy a konfigurált célhely az Excel formátumban létrehozott kimeneti eredményhez van hozzárendelve. Állítsa a **Kötegelt feldolgozás** lehetőséget **Igenre** ahhoz, hogy ezt a jelentést felügyelet nélküli üzemmódban futtassa. Kattintson az **Ismétlődésre** ahhoz, hogy beütemezze a kötegelt végrehajtás szükséges ismétlődését. Az ismétlődés határozza meg, hogy a frissített adatok milyen gyakran kerülnek a Finance and Operations alkalmazásból a Power BI-ba. [![Elektronikus jelentések paramétereinek párbeszédablaka](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png) A konfigurálás után az ER-jelentés végrehajtási feladatát a **Kötegelt feladatok** lapon találhatja meg (**Rendszerfelügyelet &gt; Lekérdezések &gt; Kötegelt feladatok**). [![Kötegelt feladatok lapja](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png) Amikor ez a feladat először fut, a célhely létrehoz egy új Excel-fájlt a konfigurált névvel, a kiválasztott SharePoint-mappában. Minden későbbi alkalommal, amikor ez a feladat fut, a célhely létrehozza ennek az Excel-fájlnak egy új verzióját. [![Az Excel-fájl új verziója](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Power BI-adatkészlet létrehozása az ER-formátum kimeneti eredményeinek felhasználásával
Jelentkezzen be a Power BI-ba, és nyisson meg egy meglévő Power BI-csoportot (munkaterület), vagy hozzon létre egy új csoportot. Kattintson a **Hozzáadás** elemre a **Fájlok** alatt, az **Adatok importálása vagy csatlakozás adatokhoz** szakaszban, vagy kattintson a pluszjelre (**+**) az **Adatkészletek** mellett a bal oldali ablakban. [![Adatkészlet létrehozása](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png) Válassza ki a **SharePoint - Csoportwebhelyek lehetőséget**, majd adja meg az Ön által használt a SharePoint-kiszolgáló elérési útját (**https://ax7partner.litware.com** ebben a példában). Ezután menjen a **/Megosztott dokumentumok/GER-adatok/PowerBI** mappára, és válassza ki azt az Excel-fájlt, amelyet az új Power BI-adatkészlet adatforrásaként létrehozott. [![Az Excel-fájl kiválasztása](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png) Kattintson a **Csatlakozás**, majd az **Importálás** elemre. Létrejön az új adatkészlet, amely a kiválasztott Excel-fájlon alapul. Az adatkészlet automatikusan hozzáadódik az újonnan létrehozott irányítópulthoz. [![Adatkészlet az irányítópulton](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png) Állítsa be úgy a frissítési ütemezést, hogy ez az adatkészlet időszakos frissítést kényszerítsen ki. Az időszakos frissítések lehetővé teszik a Finance and Operations alkalmazásból érkező, új üzleti adatok felhasználását az ER-jelentés időszakos végrehajtása révén, az Excel-fájlnak a SharePoint-kiszolgálón létrehozott új változatai segítségével.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Power BI-jelentés létrehozása az új adatkészlet segítségével
Ahhoz, hogy új Power BI-jelentést hozzon létre, kattintson az **importálás és exportálás részleteit** tartalmazó Power BI-adatkészletre, amelyet létrehozott. Ezután állítsa be a megjelenítést. Például válassza ki a **Kitöltött térkép** megjelenítést, és állítsa be a következőképpen:

-   Rendelje hozzá a **OrszágEredet** adatkészlet-mezőt a térképes megjelenítés **Hely** mezőjéhez.
-   Rendelje hozzá a **Mennyiség** adatkészlet-mezőt a térképes megjelenítés **Színtelítettség** mezőjéhez.
-   Adja hozzá a **Tevékenység** és az **Év** adatkészlet-mezőt a térképes megjelenítés **Szűrők** mezőgyűjteményéhez.

Mentse el a Power BI-jelentést **importálás és exportálás részletezését tartalmazó jelentésként**. [![Importálás és exportálás részletezését tartalmazó jelentés](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png) Figyelje meg, hogy a térképen az Excel-fájlban megtalálható országok/régiók láthatók (Ausztria és Svájc ebben a példában). Ezeknek az országoknak/régióknak színei a számlázott összegek arányát is jelzik. Frissítse az Intrastat-tranzakciók listáját. Az Olaszországból származó exporttranzakció is hozzáadásra kerül. [![Intrastat-tranzakciók listája](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png) Várjon, amíg az ER-jelentés következő, ütemezett végrehajtására és a Power BI-adatkészlet következő, ütemezett frissítésére sor nem kerül. Ezután tekintse át a Power BI-jelentést (válassza ki, hogy csak az importálás-tranzakciók jelenjenek meg). A frissített térkép most már mutatja Olaszországot. [![Frissített térkép](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance-and-operations"></a>A Power BI-jelentés elérhetővé tétele a Finance and Operations alkalmazásban.
Állítsa be az integrálást a Finance and Operations és a Power BI között. További tudnivalókért lásd: [A Power BI konfigurálása a munkaterületekhez való integráláshoz](configure-power-bi-integration.md). Az **Elektronikus jelentések** azon a munkaterületlapján, amely támogatja a Power BI integrációt (**Szervezet felügyelete** &gt; **Munkaterületek** &gt; **Elektronikus jelentési munkaterület**), kattintson a **Lehetőségek** &gt; **Jelentések katalógusának megnyitása** lehetőségre. Válassza ki az Ön által létrehozott, az **Importálás és exportálás részleteire** vonatkozó Power BI-jelentést ahhoz, hogy a jelentést a kijelölt lapon teendőként jelenítse meg. Kattintson a teendőre a Finance and Operations azon lapjának megnyitásához, amely megjeleníti az Ön által a Power BI-ban megtervezett jelentést. [![Importálás és exportálás részletezését tartalmazó jelentés](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Lásd még
--------

[Elektronikus jelentéskészítés céljai](electronic-reporting-destinations.md)

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)




