---
title: Egyetlen modellgyökérhez tartozó több származtatott leképezés kezelése
description: Ez a témakör bemutatja, hogyan lehet kezelni az egy modellgyökérhez konfigurált több származtatott leképezést.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595de6292b81ca78bf08a66f61850c3b5a537396
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354391"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Egyetlen modellgyökérhez tartozó több származtatott leképezés kezelése

[!include [banner](../includes/banner.md)]

Az [Elektronikus jelentéskészítés (ER)](general-electronic-reporting.md) adatainak [modell](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőjét minden konfigurált ER [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevő használja kimenő dokumentumok előállításához adatforrásként. Ha egyetlen üzleti tartományt kell leírni, konfigurálnia kell egy olyan adatmodell-összetevőt, amely számos gyökérdefiníciót tartalmaz. 

Minden gyökérdefiníció segít az adott tartomány adatait az adott jelentési céloknak leginkább megfelelő módon ábrázolni. Minden gyökérdefinícióhoz konfigurálhat egy ER [modell-leképezési](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt az adatmodell Microsoft Dynamics 365 Finance-specifikus implementációjaként. Ily módon leírható, hogyan lesz kitöltve az adatmodell futásidőben.

Az ER modell-leképezés összetevői az ER-adatmodell [konfigurációiban](general-electronic-reporting.md#Configuration) és az ER-modell hozzárendelési konfigurációiban találhatók. Egyetlen ER-konfiguráció több leképezési összetevőt tartalmazhat, amelyek mindegyike egyetlen gyökérdefinícióhoz van beállítva. Alternatív megoldásként egyetlen ER-konfiguráció csak egy olyan leképezési összetevőt tartalmazhat, amely egyetlen gyökérdefinícióhoz van beállítva.

Számos konfigurációszolgáltató kínálhat ER-modell-leképezési konfigurációkat ugyanahhoz az ER-adatmodellhez. Ezek a modell-leképezési konfigurációk tartalmazhatnak eltérő gyökérdefiníciókhoz tartozó leképezési összetevőket. Egy modell-leképezést használhat az egyik gyökérdefinícióhoz, amelyet az egyik [szolgáltató](general-electronic-reporting.md#Provider) kínál, és a másik gyökérdefinícióhoz használhat egy másik szolgáltató által kínált modell-leképezést.

A jelen témakörben található eljárások bemutatják, hogyan kezelheti egy ER-adatmodell több ER-modell-leképezési konfigurációját, amikor ugyanahhoz a gyökérdefinícióhoz konfigurált, különböző modell-leképezéseket tartalmaznak. 

A témakör eljárásainak végrehajtásához a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel kell rendelkeznie.

A USMF vállalatban valamennyi következő eljárást végrehajthatja. Nincs szükség kódolásra.

## <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Elektronikus jelentések fejlesztője szerepkörű felhasználóként [konfigurálnia kell a minimálisan szükséges ER-paraméterek készletét](er-quick-start2-customize-report.md#ConfigureFramework), mielőtt üzleti dokumentumok előállításához kezdené használni az ER-keretrendszert.

## <a name="import-the-standard-er-format-configurations"></a>A szabvány ER-formátumkonfigurációk importálása

Ha a szabvány ER-konfigurációkat a Finance jelenlegi példányához szeretné hozzáadni, importálnia kell azokat az adott példányhoz konfigurált ER-adattárból. Az [ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából](er-download-configurations-global-repo.md) szakasz lépéseit követve importálhatja a következő ER-formátumkonfigurációkat:

- **Szabadszöveges számla (Excel)**, 220.106-os verzió
- **Projektszámla (Excel)**, 226.27-es verzió

## <a name="review-the-imported-er-configurations"></a>Importált ER-konfigurációk áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Számlamodell** elemet.

    ![A Konfigurációk oldalon importált konfigurációk áttekintése.](./media/er-multiple-model-mappings-image1.png)

4. Tekintse át a **Szabadszöveges számla (Excel)** formátumot:

    1. A bal oldali ablak konfigurációs fáján válassza ki a **Szabadszöveges számla (Excel)** lehetőséget.
    2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
    3. A **Formátumtervező** oldal **Leképezések** lapján az adatforrások listájában válassza a **Modell** lehetőséget.
    4. Válassza ki a **Nézet** lehetőséget.
    
       Az aktuális ER-formátum a **Számlamodell** **InvoiceCustomer** gyökérdefiníciójának használatára van beállítva. Amikor ezt a formátumot futtatja, és a **Modell** adatforrást hívja a rendszer, az **InvoiceCustomer** gyökérdefinícióhoz beállított modell-leképezést használja a rendszer az alkalmazásadatok eléréséhez és az adatmodell kitöltéséhez.

        ![A modell-adatforrás áttekintése az Űrlaptervező oldalon.](./media/er-multiple-model-mappings-image2.png)

    6. Zárja be a **Formátumtervező** lapot.

5. Tekintse át a **Számlamodell-leképezési** konfiguráció tartalmát:

    1. A bal oldali ablak konfigurációs fáján válassza ki a **Számlamodell-leképezés** lehetőséget.
    2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
    3. A **Modell leképezése adatforráshoz** oldalon figyelje meg, hogy az aktuális ER-modell-leképezés konfigurációja több modell-leképezési összetevőt is tartalmaz:

        + A **Vevői számla** modell-leképezés a **Számlamodell** **InvoiceCustomer** gyökérdefiníciójához van konfigurálva. Ezért a **Szabadszöveges számla (Excel)** ER-formátum futtatásakor ki lehet választani az erre az ER-konfigurációra vonatkozó **Vevői számla** modell-leképezést az alkalmazásadatok eléréséhez és az adatmodell kitöltéséhez.
        + A **Projektszámla** modell-leképezés a **Számlamodell** **InvoiceProject** gyökérdefiníciójához van konfigurálva. Ezért a **Projektszámla (Excel)** ER-formátum futtatásakor ki lehet választani az erre az ER-konfigurációra vonatkozó **Projektszámla** modell-leképezést az alkalmazásadatok eléréséhez és az adatmodell kitöltéséhez.

        ![A Modell leképezése adatforráshoz oldalon található Számlamodell-leképezés.](./media/er-multiple-model-mappings-image3.png)

    4. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.
    5. A **Verziók** gyorslapon válassza a **Törlés** lehetőséget az ER-konfiguráció 240.175-ös vagy annál újabb verziói mindegyikének törléséhez.

6. Tekintse át a **Projektszámlamodell-leképezés (RPD)** konfiguráció tartalmát:

    1. A bal oldali ablak konfigurációs fáján válassza ki a **Projektszámlamodell-leképezés (RDP)** lehetőséget.
    2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
    3. A **Modell hozzárendelése adatforráshoz** oldalon figyelje meg, hogy az aktuális ER-modell-leképezési konfiguráció tartalmazza az **InvoiceProject** modell-leképezést, és hogy ez a modell-leképezés a **Számlamodell** **InvoiceProject** gyökérdefiníciójára van konfigurálva. A **Projektszámla (Excel)** ER-formátum futtatásakor válassza ki az erre az ER-konfigurációra vonatkozó **InvoiceProject** modell-leképezést az alkalmazásadatok eléréséhez és az adatmodell kitöltéséhez.

        ![A Modell leképezése adatforráshoz oldalon található Projektszámlamodell-leképezés.](./media/er-multiple-model-mappings-image4.png)

    4. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.
    5. A **Verziók** gyorslapon válassza a **Törlés** lehetőséget az ER-konfiguráció 226.35-ös vagy annál újabb verziói mindegyikének törléséhez.

## <a name="customize-the-imported-er-configurations"></a>Importált ER-konfigurációk testreszabása

Ez a szakasz bemutatja a Microsoft által biztosított modellleképezések [testreszabását](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration). A testreszabás szükséges lehet például az egyéni logika megvalósításához vagy a hiányzó kötések hozzáadásához.

### <a name="customize-the-invoice-model-mapping-configuration"></a>A Számlamodell-leképezési konfiguráció testreszabása

1. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában válassza a **Számlamodell-leképezés** elemet.
2. A Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
3. A **Konfiguráció létrehozása** legördülő párbeszédpanel **Új** mezőjében válassza a **Származtatás innen: Számlamodell leképezése, Microsoft** lehetőséget.
4. A **Név** mezőben írja be a **Számlamodell-leképezés (Litware)** szöveget.
5. Válassza a **Konfiguráció létrehozása** lehetőséget.
6. [Jelölje meg](er-quick-start2-customize-report.md#MarkFormatRunnable) a származtatott leképezések [vázlat](general-electronic-reporting.md#component-versioning) verzióit futásidőben használhatóként:

    1. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
    2. A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.
    3. Ha szükséges, a **Szerkesztés** gombbal a lapot szerkeszthetőre állíthatja.
    4. A konfigurációs fában jelenleg kiválasztott **Számlamodell-leképezés (Litware)** konfiguráció esetében állítsa a **Vázlat futtatása** beállítást **Igen** értékre.

7. A Művelet panelen válassza a **Tervező** lehetőséget a konfiguráció modell-leképezésének ellenőrzéshez.

    ![A Modell leképezése adatforráshoz oldalon található számlamodell-leképezések ellenőrzése.](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > A tervezőben megnyithatja ennek az ER-konfigurációnak bármely ER-modell-leképezési összetevőjét, hogy konfigurálja az egyéni logikát. A további tudnivalókat lásd: [A modell-leképezési konfiguráció testreszabása](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.

Most már rendelkezik **Számlamodell-leképezés** és **Számlamodell-leképezés (Litware)** konfigurációval, amelyek mindegyikének van egy **InvoiceCustomer** gyökérdefinícióhoz beállított modell-leképezése. Explicit módon rendelje hozzá az egyik modell-leképezést alapértelmezett modell-leképezésként bármely ER-formátumhoz, például az **InvoiceCustomer** gyökérdefinícióval rendelkező modelladatforrást tartalmazó **Szabadszöveges számla (Excel)** formátumhoz. Ellenkező esetben az ER-formátumok futtatása, szerkesztése vagy érvényesítése esetén a rendszer a következő kivétellel figyelmezteti, hogy nincs kifejezetten hozzárendelt alapértelmezett modell-leképezés:
 
> Egynél több modell-leképezés létezik a konfigurációkban (\<configuration names separated by commas\>) található „\<model name\> (\<root descriptor\>)” adatmodellhez. Állítsa be az egyik konfigurációt alapértelmezettként.

![A formátum megnyitása szerkesztésre a Konfigurációk oldalon.](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>A Projektszámlamodell-leképezés (RDP) konfiguráció testreszabása

1. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában válassza a **Projektszámlamodell-leképezés (RDP)** elemet.
2. A Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
3. A **Konfiguráció létrehozása** párbeszédpanel **Új** mezőjében válassza a **Származtatás innen: Projektszámlamodell-leképezés (RDP), Microsoft** lehetőséget.
4. A **Név** mezőben írja be a **Projektszámlamodell-leképezés (Litware)** szöveget.
5. Válassza a **Konfiguráció létrehozása** lehetőséget.
6. A konfigurációs fában jelenleg kiválasztott **Projektszámlamodell-leképezés (Litware)** konfiguráció esetében állítsa a **Vázlat futtatása** beállítást **Igen** értékre.
7. A Művelet panelen válassza a **Tervező** lehetőséget a konfiguráció modell-leképezésének ellenőrzéshez.

    ![A Modell leképezése adatforráshoz oldalon található személyre szabott projektszámlamodell-leképezések ellenőrzése.](./media/er-multiple-model-mappings-image7.png)

8. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.

Most már rendelkezik **Számlamodell-leképezés**, **Projektszámlamodell-leképezés (RDP)** és **Projektszámlamodell-leképezés (Litware)** konfigurációkkal. Ezen konfigurációk mindegyikének van egy **InvoiceProject** gyökérdefinícióhoz beállított modell-leképezése. Kifejezetten rendeljen hozzá az egyik modell-leképezést alapértelmezett modell-leképezésként, amelyet bármelyik ER-formátum használhat. Használja például a **Projektszámla (Excel)** formátumot, amely az **InvoiceProject** gyökérdefinícióval rendelkező modelladatforrást tartalmaz. Ellenkező esetben az ER-formátumok futtatása vagy szerkesztése esetén a rendszer egy kivétellel figyelmezteti, hogy nincs kifejezetten hozzárendelt alapértelmezett modell-leképezés.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Válassza ki a származtatott Számlamodell-leképezés (Litware) konfigurációt az alapértelmezett modell-leképezéseket tartalmazó konfigurációként

1. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában válassza a **Számlamodell-leképezés (Litware)** elemet.
2. Állítsa az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre.

    ![A modell-leképezés beállítása alapértelmezett modell-leképezésként a Konfigurációk oldalon.](./media/er-multiple-model-mappings-image8.png)

    Emiatt a beállítás miatt a **Vevői számla másolata** modell-leképezés kerül használatram amikor a **Szabadszöveges számla (Excel)** modellt futtatja, illetve annak szerkesztése vagy ellenőrzése esetén. A **Számlamodell-leképezés** konfiguráció **Vevői számla** modell-leképezését a rendszer figyelmen kívül hagyja.

    Most már megnyithatja a **Szabadszöveges számla (Excel)** formátumot áttekintésre a formátumtervezőben.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Válassza ki a származtatott Projektszámlamodell-leképezés (Litware) konfigurációt az alapértelmezett modell-leképezéseket tartalmazó konfigurációként

1. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában válassza a **Projektszámlamodell-leképezés (Litware)** elemet.
2. Állítsa az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre.

    Ebben az esetben, ellentétben az előző szakaszban a **Számlamodell-leképezés (Litware)** konfigurációval kapcsolatban ismertetett esettel, nem kezdheti el használni a **InvoiceProject példány** modell-leképezést a **Projektszámlamodell-leképezés (Litware)** konfigurációból. Jelenleg két olyan konfiguráció van megjelölve alapértelmezett konfigurációként, amely modellleképezést tartalmaz az **InvoiceProject** gyökérdefinícióhoz. Ezért a használathoz azonos prioritást élveznek. A probléma megoldásához kövesse az eljárás további lépéseit.

3. A bal oldali ablak konfigurációs fáján válassza ki a **Számlamodell-leképezés (Litware)** lehetőséget.
4. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
5. A **Modell leképezése adatforráshoz** oldalon válassza a **Szerkesztés** lehetőséget a lap szükség szerinti szerkeszthetővé tételéhez.
6. Válassza ki a **Projektszámla másolata** modell-leképezést, majd jelölje be hozzá a **Törölve** jelölőnégyzetet.

    ![A modell-leképezés beállítása virtuálisan töröltként a Modell leképezése adatforráshoz oldalon.](./media/er-multiple-model-mappings-image9.png)

    E beállítás miatt a rendszer úgy kezeli a **Számlamodell-leképezés (Litware)** konfigurációt, mintha nem rendelkezne modell-leképezéssel az **InvoiceProject** gyökérdefinícióhoz. Alapértelmezés szerint a rendszer az **InvoiceProject másolat** modell-leképezést adja ki. Alapértelmezésként az ezt a modell-leképezést tartalmazó **Projektszámlamodell-leképezés (Litware)** kerül alapértelmezet konfigurációként megjelölésre. Mivel ez az alapértelmezett beállítás, magasabb prioritást élvez, mint a **Projektszámlamodell-leképezés (RDP)** konfigurációból származó **InvoiceProject** modell-leképezés.

## <a name="other-considerations"></a>További szempontok

A **Projektszámlamodell-leképezés (Litware)** konfiguráció **InvoiceProject másolat** modell-leképezését a **ReportDataProvider** adatforrás használatára tervezték. Az adatforrás a **PsaProjInvoiceDP** alkalmazásosztályra hivatkozó *Objektum* típus része. Ez az osztály a Nyomtatáskezelési keretrendszer projektszámla SQL Server Reporting Services (SSRS) jelentésének adatszolgáltatójaként van megvalósítva. Válassza ki ezt az adatforrást ER [integrációs pontként](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents). A Nyomtatáskezelési jelentések aktuális ER-megvalósítása figyelembe veszi ezt a beállítást. További részleteket az **ERPrintMgmtDataProviderReport** alkalmazásosztály forráskódja tartalmaz. Futásidőben a **ReportDataProvider** adatforrás hozzárendelése a modell-leképezési integrációs pontként arra kényszeríti a Finance alkalmazást, hogy magasabb prioritással kezelje ezt a leképezési összetevőt, mint a **Projektszámlamodell-leképezés (RDP) konfiguráció** **InvoiceProject** leképezési összetevője.

## <a name="see-also"></a>Lásd még

- [ER modell-leképezés kezelése külön ER-konfigurációkban](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Országkörnyezet-függő ER-modell-leképezések konfigurálása](er-country-dependent-model-mapping.md)
- [Elektronikus jelentéstételi keretrendszer API-módosításai](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]