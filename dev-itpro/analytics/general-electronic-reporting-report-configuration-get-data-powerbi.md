---
title: "Elektronikus jelentési Dynamics 365 adatokkal kiemelt BI nyújt műveletek beállítása"
description: "Ez a témakör bemutatja, hogyan használható az elektronikus jelentési (ER) konfiguráció arra, hogy adatokat vigyen át a Dynamics 365 for Operations alkalmazásból a Power BI szolgáltatásokba. A jelen témakörben bemutatott példa Intrastat-tranzakciókat alkalmaz olyan üzleti adatokként, amelyeket át kell adni. A Power BI térképes megjelenítése ezt az Intrastat-tranzakciós adatot használja egy olyan nézet bemutatásához, amellyel egy vállalat importálási/exportálási tevékenységeit lehet elemezni a Power BI-jelentésben."
author: kfend
manager: AnnBe
ms.date: 2016-10-31 13 - 22 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ed0192c44b6d7e88120c64e539ebb0ac3b379831
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-electronic-reporting-to-provide-power-bi-with-data-from-dynamics-365-for-operations"></a>Elektronikus jelentési Dynamics 365 adatokkal kiemelt BI nyújt műveletek beállítása

Ez a témakör bemutatja, hogyan használható az elektronikus jelentési (ER) konfiguráció arra, hogy adatokat vigyen át a Dynamics 365 for Operations alkalmazásból a Power BI szolgáltatásokba. A jelen témakörben bemutatott példa Intrastat-tranzakciókat alkalmaz olyan üzleti adatokként, amelyeket át kell adni. A Power BI térképes megjelenítése ezt az Intrastat-tranzakciós adatot használja egy olyan nézet bemutatásához, amellyel egy vállalat importálási/exportálási tevékenységeit lehet elemezni a Power BI-jelentésben.

<a name="overview"></a>Áttekintés
--------

A Microsoft Power BI olyan szoftverek, szolgáltatások, alkalmazások és összekötők gyűjteménye, amelyek együtt dolgoznak azért, hogy a külső forrásokból származó adatokat koherens, vizuálisan élményt nyújtó és interaktív betekintéssé alakítsák. Az elektronikus jelentések (ER) segítségével a Microsoft Dynamics 365 for Operations felhasználói könnyen konfigurálhatnak adatforrásokat és vihetnek át adatok a Dynamics 365 for Operations alkalmazásból a Power BI alkalmazásnak. Az adatok átvitele fájlokban történik, OpenXML munkalap (Microsoft Excel-munkafüzet) formátumban. Az átvitt fájlok tárolása a Microsoft SharePoint Serveren történik, amely ennek a célnak megfelelően lett konfigurálva. A tárolt fájlokat a Power BI olyan jelentések elkészítésére használja, amelyek tartalmaznak megjelenítőeszközöket (táblázatok, diagramok, térképek stb.). A Power BI jelentések megosztásra kerülnek a Power BI felhasználókkal, hozzáférésük a Power BI irányítópulton és a Dynamics 365 for Operations oldalakon történik. Ez a témakör az alábbi feladatokat magyarázza el:

-   A Dynamics 365 for Operations konfigurálása.
-   Az ER-formátum konfigurációjának előkészítése a Dynamics 365 for Operations adatainak beolvasásához.
-   Az ER-környezet konfigurálása a Power BI-ba történő adatátvitelhez.
-   Az átvitt adatok felhasználása Power BI-jelentés létrehozására.
-   A Power BI-jelentés elérhetővé tétele a Dynamics 365 for Operations alkalmazásban.

## <a name="prerequisites"></a>Előfeltételek
A jelen témakörben szereplő példa elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

-   Hozzáférés a Dynamics 365 for Operations alkalmazáshoz a következő szerepkörök egyikével:
    -   Elektronikus jelentések fejlesztője
    -   Elektronikus jelentések funkcióival foglalkozó konzulens
    -   Rendszergazda
-   Hozzáférés a SharePoint-kiszolgálóhoz, amelyet a Dynamics 365 for Operations alkalmazással való használatra konfiguráltak
-   Hozzáférés a Power BI keretrendszerhez

## <a name="configure-document-management-parameters"></a>Dokumentumkezelés paraméterek konfigurálása
1.  A **Dokumentumkezelés paraméterei** lapon állítsa be a hozzáférést ahhoz a SharePoint-kiszolgálóhoz, amelyet az a vállalat fog használni, amelybe Ön bejelentkezett (ebben a példában a DEMF vállalat).
2.  Ellenőrizze a csatlakozást a SharePoint-kiszolgálóhoz, és győződjön meg róla, hogy rendelkezik hozzáféréssel. [![Dokumentum kezelési paraméterek lap](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)
3.  Nyissa meg a konfigurált SharePoint-webhelyet. Hozzon létre egy új mappát, ahol az ER azokat az Excel-fájlokat fogja tárolni, amelynek üzleti adataira a Power BI-jelentéseknek szükségük van a Power BI-adatkészletek forrásaként.
4.  A Dynamics 365 for Operations alkalmazásban, a **Dokumentumtípusok** lapon hozzon létre egy új dokumentumtípust, amely az imént létrehozott SharePoint-mappa elérésére szolgál. Adja meg a **Fájlt** a **Csoport** mezőben és a **SharePointot** a **Hely** mezőben, majd adja meg a SharePoint-mappa címét. [![Dokumentum-típusok oldalon](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása
1.  Az **Elektronikus jelentések** munkaterületen kattintson az **Elektronikus jelentések paraméterei** hivatkozására.
2.  A **Mellékletek** lapon jelölje be a **Fájl** dokumentumtípust az összes mezőnél.
3.  Az **Elektronikus jelentések** munkaterületén aktiválja a megfelelő szolgáltatót; ehhez kattintson a **Beállítás aktívként** lehetőségre. További információkhoz játssza le az **ER-szolgáltató kijelölése** feladat-útmutatót.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>ER-adatmodell használata adatforrásként
A Power BI-jelentésekben használt üzleti adatok forrásának ER-adatmodellnek kell lennie. Ennek az adatmodellnek a feltöltése a ER-konfigurációk tárházából történik. További tudnivalókért lásd: [Elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](download-electronic-reporting-configuration-lcs.md), vagy játssza le az **ER-konfiguráció importálása a Lifecycle Services rendszerből** feladat-útmutatót. Válassza ki az **Intrastatot **azon adatmodellként, amelyet a program a kiválasztott ER-konfigurációk tárházából feltölt. (Ebben a példában a modell 1-es verziójú szolgál.) Érheti el a **Intrastat** ER-modell beállítása a a **konfigurációk** oldalon. [![Beállítások lap](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Egy ER-formátumú konfiguráció kialakítása
Létre kell hoznia egy olyan új ER-formátum konfigurációt, amely az **Intrastat** adatmodellt használja az üzleti adatok forrásaként. Ennek a formátumkonfigurációnak OpenXML (Excel-fájl) formátumú, elektronikus dokumentumokként kell létrehoznia a kimeneti eredményeket. További információkhoz játssza le az **ER-konfiguráció létrehozása OPENXML formátumú jelentésekhez** feladat-útmutatót. Nevezze el az új konfiguráció **importálási / exportálási tevékenységeknek**, a következő ábrán látható módon. Használja a [ER-érték – importálás és exportálás részletei](https://go.microsoft.com/fwlink/?linkid=845208) Excel-fájlt sablonként, amikor megtervezi az ER formátumát. (Formátum sablon importálása tájékozódhat a feladat útmutató lejátszás.) [![Import / export konfigurációs tevékenységek](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png) módosítása a **Import / export tevékenységek** konfigurációs formázásához hajtsa végre az alábbi lépéseket.

1.  Kattintson a **Tervező** pontra.
2.  A **Formátum** lapon adjon nevet a fájlelemnek ehhez a formátumhoz: **Excel kimeneti fájl**. [![Excel kimeneti fájl elem](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)
3.  A **Leképezés** lapon adja meg annak az Excel-fájlnak a nevét, amely létrejön, amikor ezt a formátumot futtatják Konfigurálja az **importálás és exportálás részletei** érték megadásához szükséges, kapcsolódó kifejezést (az .xlsx fájlkiterjesztést a rendszer automatikusan hozzáadja). [![Format designer](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Adjon hozzá egy új adatforrás-elemet ehhez a formátumhoz. (Erre a számbavételre a további adatok kötéséhez van szükség.)
    1.  Az adatforrás neve **irány\_számbavételi**.
    2.  Válassza ki az **Adatmodell számbavételét** az adatforrás típusaként.
    3.  Lásd: **Irány** adatmodell számbavétele.

    [![irány\_számbavételi](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Végezze el az **Intrastat** adatmodell elemeinek és a kialakított formátum elemeinek összekötését, amint azt a következő ábra mutatja. [![A kötés befejezése](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

A futtatás után az ER-formátum létrehozza a kimeneti eredményeket Excel-formátumban. A rendszer elküldi az Intrastat-tranzakciók részleteit a kimeneti adatokhoz, és különválasztja ezeket olyan tranzakciókká, amelyek vagy importálási tevékenységeket vagy exportálási tevékenységeket írnak le. Kattintson a **futtatni** tesztelése az új ER-formátumú Intrastat-tranzakciók listája a a **Intrastat** lap (**adó**&gt;**nyilatkozatok**&gt;**külkereskedelmi**&gt;**Intrastat**). [![Intrastat lap](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png) az alábbi kimeneti eredmény jön létre. A fájl neve **Import and export details.xlsx**, ahogyan a formátum beállításainál megadta. [![A behozatali és kiviteli details.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>ER-célhely konfigurálása
Az ER-keretrendszert úgy kell konfigurálnia, hogy az új ER-formátumkonfigurálás kimeneti eredményeit speciális módon küldje el.

-   A kimeneti eredményt a kiválasztott SharePoint-kiszolgáló mappájába kell elküldeni.
-   A formátumkonfiguráció minden egyes végrehajtásakor ugyanannak az Excel-fájlnak egy új verziójának kell létrejönnie.

A a **elektronikus jelentés** lap (**szervezet felügyelete**&gt;**elektronikus jelentés**), kattintson a **elektronikus jelentési cél** elemet, és adjon meg egy új célt. A **Hivatkozás** mezőben válassza ki azt az **importálási / exportálási tevékenységek** formátumkonfigurációt, amelyet korábban létrehozott. Végezze el a következő lépéseket ahhoz, hogy az új fájl célhely-rekordját hozzáadja a hivatkozáshoz.

1.  A **Név** mezőbe írja be a fájl célhelyének megnevezését.
2.  A **Fájlnév** mezőben válassza ki az **Excel kimeneti fájl** nevet az Excel formátumú összetevőhöz.

Kattintson az új célhely rekordjának **Beállítások** gombjára. Ezután a **Célhely beállításai** párbeszédpanelben végezze el az alábbi lépéseket.

1.  A **Power BI** lapon az **Engedélyezett** lehetőséget állítsa **Igenre**.
2.  A **SharePoint** mezőben válassza ki azt a **Megosztott** dokumentumtípust, amelyet korábban létrehozott.

## <a name="schedule-execution-of-the-configured-er-format"></a>A beállított ER-formátum végrehajtási ütemezése
A a **konfigurációk** lap (**szervezet felügyelete**&gt;**elektronikus jelentés**&gt;**konfigurációk**), a konfigurációk fában, válassza ki a **Import / export tevékenységek** korábban létrehozott konfigurációs. Az 1.1 verzió állapotát módosítsa **Vázlatról** **Készre** , hogy ez a formátum használható legyen. [![Konfigurációk lap](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png) válassza ki a teljes verziót a **Import / export tevékenységek** konfigurációs, és kattintson **futtatni**. Vegye figyelembe, hogy a konfigurált célhely az Excel formátumban létrehozott kimeneti eredményhez van hozzárendelve. Állítsa a **Kötegelt feldolgozás** lehetőséget **Igenre** ahhoz, hogy ezt a jelentést felügyelet nélküli üzemmódban futtassa. Kattintson az **Ismétlődésre** ahhoz, hogy beütemezze a kötegelt végrehajtás szükséges ismétlődését. Az ismétlődés határozza meg, hogy a frissített adatok milyen gyakran kerülnek a Dynamics 365 for Operations alkalmazásból a Power BI-ba. [![Elektronikus jelentés paraméterei párbeszédpanel](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png) után úgy van beállítva, megtalálhatja a ER jelentés végrehajtási feladat a **kötegelt** lap (**rendszerfelügyelet &gt;lekérdezések &gt;kötegelt**). [![Kötegelt feladatok lap](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png) Ez a feldolgozás első futtatásakor a cél új fájlt hoz létre az Excel a kijelölt SharePoint-mappa konfigurált nevét tartalmazó. Minden későbbi alkalommal, amikor ez a feladat fut, a célhely létrehozza ennek az Excel-fájlnak egy új verzióját. [![Az Excel fájl új verzióját](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Power BI-adatkészlet létrehozása az ER-formátum kimeneti eredményeinek felhasználásával
Jelentkezzen be a Power BI-ba, és nyisson meg egy meglévő Power BI-csoportot (munkaterület), vagy hozzon létre egy új csoportot. Vagy kattintson **hozzáadása** alatt **fájlok** a a **importálása vagy csatlakozás adatokhoz** szakasz, vagy kattintson a plusz jelre (**+**) mellett **adathalmazok** a bal oldali ablaktáblában. [![A DataSet adatkészlet létrehozása](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png) válassza ki a **SharePoint-csoportwebhelyek** lehetőséget, és adja meg az elérési utat, amelyen a SharePoint Server (**https://ax7partner.spoppe.com** ebben a példában). Ezután menjen a **/Megosztott dokumentumok/GER-adatok/PowerBI** mappára, és válassza ki azt az Excel-fájlt, amelyet az új Power BI-adatkészlet adatforrásaként létrehozott. [![Az Excel fájl kijelölése](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png) kattintson a **csatlakozás**, és kattintson a **Import**. Létrejön az új adatkészlet, amely a kiválasztott Excel-fájlon alapul. Az adatkészlet automatikusan hozzáadódik az újonnan létrehozott irányítópulthoz. [![Az irányítópult a DataSet](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png) a DataSet időszakos frissítés kényszerítése a frissítési ütemterv beállítása. Az időszakos frissítések lehetővé teszik a Dynamics 365 for Operations alkalmazásból érkező, új üzleti adatok felhasználását az ER-jelentés időszakos végrehajtása révén, az Excel-fájlnak a SharePoint-kiszolgálón létrehozott új változatai segítségével.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Power BI-jelentés létrehozása az új adatkészlet segítségével
Ahhoz, hogy új Power BI-jelentést hozzon létre, kattintson az **importálás és exportálás részleteit** tartalmazó Power BI-adatkészletre, amelyet létrehozott. Ezután állítsa be a megjelenítést. Például válassza ki a **Kitöltött térkép** megjelenítést, és állítsa be a következőképpen:

-   Rendelje hozzá a **OrszágEredet** adatkészlet-mezőt a térképes megjelenítés **Hely** mezőjéhez.
-   Rendelje hozzá a **Mennyiség** adatkészlet-mezőt a térképes megjelenítés **Színtelítettség** mezőjéhez.
-   Adja hozzá a **Tevékenység** és az **Év** adatkészlet-mezőt a térképes megjelenítés **Szűrők** mezőgyűjteményéhez.

Mentse el a Power BI-jelentést **importálás és exportálás részletezését tartalmazó jelentésként**. [![Importálás és exportálás részletek jelentés](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png) ne feledje, hogy a térképen látható az országok/régiók szerepelnek az Excel-fájlt (Ausztria és Svájc ebben a példában). Ezeknek az országoknak/régióknak színei a számlázott összegek arányát is jelzik. Frissítse az Intrastat-tranzakciók listáját. Az Olaszországból származó exporttranzakció is hozzáadásra kerül. [![Intrastat-tranzakciók listája](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png) ER jelentés következő ütemezett végrehajtása és a következő időzített frissítés az energiagazdálkodási BI adathalmaz várja. Ezután tekintse át a Power BI-jelentést (válassza ki, hogy csak az importálás-tranzakciók jelenjenek meg). A frissített térkép most már mutatja Olaszországot. [![Frissített térkép](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-dynamics-365-for-operations"></a>A Power BI-jelentés elérése a Dynamics 365 for Operations alkalmazásban
Állítsa be az integrálást a Dynamics 365 for Operations és a Power BI között. További tudnivalókért lásd: [A Power BI konfigurálása a munkaterületekhez való integráláshoz](configure-power-bi-integration.md). A a **elektronikus jelentés** munkaterület lap, amely támogatja az energiagazdálkodási BI-integráció (**szervezet felügyelete**&gt;**munkaterületek**&gt;**elektronikus jelentési munkaterület**), kattintson a **beállítások**&gt;**megnyitott jelentés katalógus**. Válassza ki az Ön által létrehozott, az **Importálás és exportálás részleteire** vonatkozó Power BI-jelentést ahhoz, hogy a jelentést a kijelölt lapon teendőként jelenítse meg. Kattintson a teendőre a Dynamics 365 for Operations azon lapjának megnyitásához, amely megjeleníti az Ön által a Power BI-ban megtervezett jelentést. [![Importálás és exportálás részletek jelentés](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Lásd még
--------

[Elektronikus jelentéskészítés céljai](electronic-reporting-destinations.md)

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)


