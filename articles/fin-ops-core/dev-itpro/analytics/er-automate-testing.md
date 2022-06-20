---
title: Elektronikus jelentéskészítéssel folytatott tesztelés automatizálása
description: Ez a cikk bemutatja, hogy hogyan automatizálhatja a funkciók tesztelését az Elektronikus jelentés (ER) keretrendszer kiindulási szolgáltatásával.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: df2baa988bb634db11d819dd84ef73eaa560bab9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892769"
---
# <a name="automate-testing-with-electronic-reporting"></a>Elektronikus jelentéskészítéssel folytatott tesztelés automatizálása

[!include[banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan automatizálhatja egyes funkciók tesztelését az Elektronikus jelentés (ER) keretrendszer használatával. Az ebben a példában látható példa bemutatja, hogyan lehet automatizálni a szállítói kifizetések feldolgozásának tesztelését.

Az alkalmazás a pénzeszközök és a megfelelő dokumentumok előállítására használja az ER-keretrendszert a szállítói kifizetések feldolgozásakor. Az ER-keretrendszer egy adatmodellből, modell-hozzárendelésből és olyan összetevőkből áll, amelyek támogatják a különböző típusú kifizetési típusokat, valamint a különböző formátumú dokumentumok létrehozását. Ezek az összetevők letölthetők a Microsoft Dynamics Lifecycle Services (LCS) modulból, és importálhatók a példányba.

Testreszabhatja az egyes Microsoft-összetevőket is, és használhatja a saját egyéni összetevője alapjaként. Egyéni verzió létrehozásával végrehajthatók a meghatározott szükségleteket támogató módosítások. Beállíthatja például, hogy az ER adatmodellje és a modell-hozzárendelés a felhasználó által megadott adatokhoz hozzáférjen, vagy ha módosítani kívánja a létrejövő dokumentumok elrendezését, akkor módosíthatja az ER formátumát.

A testreszabott ER-formátumok használhatók a szállítói kifizetéseket létrehozó kifizetési fájlok feldolgozására, valamint az ellenőrzési jelentések feldolgozására is. Az ER-összetevő esetében támogatott a verziókövetés. Ennek megfelelően a Microsoft képes a szállítói kifizetések feldolgozására szolgáló ER-megoldások frissített verzióinak biztosítására, és a frissített verziót automatikusan egyesíteni lehet a testreszabott összetevővel új alap megadásával. Az új alapra helyezett verziót azonban tesztelni kell, hogy biztosan a várakozásnak megfelelően működjön.

Az ER adatmodellek és ER modell-hozzárendelések számos olyan ER-formátum esetében gyakoriak, amelyek a különböző típusú kifizetések feldolgozására és az ország- és régióspecifikus kifizetési dokumentumok létrehozására használatosak. Emiatt rendkívül kívánatos automatizálni a felhasználó-elfogadás és az integráció tesztelését, hogy automatikusan végre legyen hajtva több vállalatnál, de az egyes vállalatok ország-/régióbeli környezetét veszi figyelembe, különböző adatkészleteket alkalmaz, és így tovább.

A konfiguráció-szolgáltatótól kapott formátumon alapuló egyéni verzió létrehozásával kapcsolatos további tudnivalókat lásd [ER – A formátum frissítése ezen formátum új alapverziójának elfogadásával](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Alapfogalmak

A működési kiemelt felhasználók felhasználóelfogadási és integráció teszteket írhatnak anélkül, hogy forráskódot kellene írniuk.

- A kiindulási ER-funkció segítségével lehet összehasonlítani a létrejövő dokumentumokat a fő példányokkal. További információkért lásd: [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md).
- A Feladatrögzítővel rögzítheti a teszteseteket, és belefoglalhatja az alapterv értékelését. További tájékoztatás: [Feladatrögzítő erőforrásai](../user-interface/task-recorder.md).
- A szükséges tesztesetekhez tartozó teszteset csoportosítása. További tájékoztatás: [felhasználói elfogadási tesztek létrehozása és automatizálása](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Használja az Üzletifolyamat-modellezőt (BPM) az LCS-ben a könyvtárak létrehozásához a felhasználói elfogadási tesztekhez.
    - Hozzon létre BPM tesztkönyvtárakat egy tesztterv és tesztkészletek létrehozásához a Microsoft Azure DevOps Services (Azure DevOps) alkalmazásban.

A funkcionális kiemelt felhasználók futtathatják a felhasználói elfogadási és integráció teszteket.

- A Regression Suite Automation Tool (RSAT) használatával futtathatja a kívánt tesztcsomag teszteseteit.
- Jelentse a teszt eredményeit az Azure DevOps felé, és használja ezt a szolgáltatást az eredmények kivizsgálására.

## <a name="prerequisites"></a>Előfeltételek

A cikk feladatainak végrehajtásához be kell fejeződnie a következő előfeltételeknek:

- A tesztautomatizálást támogató topológia alkalmazása. A **rendszeradminisztrátori** szerepkörhöz hozzáféréssel kell rendelkeznie az ehhez a topológiához tartozó példányhoz. Ennek a topológiának tartalmaznia kell az ebben a példában használt demóadatokat. A további tudnivalókért lásd: [A folyamatos build- és tesztautomatizálást támogató környezet telepítése és használata](../perf-test/continuous-build-test-automation.md).
- A felhasználói elfogadási és az integrációs tesztek automatikus futtatásához telepítenie kell az RSAT-t a használt topológiában, és a megfelelő módon konfigurálnia kell. A RSAT telepítésévelés konfigurálásával, illetve a Finance and Operations alkalmazások és az Azure DevOps megoldással való együttműködés konfigurálásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Ügyeljen az eszköz használatára vonatkozó előfeltételekre. A következő ábrán egy példa látható az RSAT-beállításokra. A kék téglalap belefoglalja azokat a paramétereket, amelyek a Azure DevOps hozzáférést határozzák meg. A zöld téglalap a példányhoz való hozzáférést meghatározó paramétereket foglalja magában.

    ![RSAT-beállítások.](media/GER-Configure.png "Az RSAT-beállítások párbeszédpaneljének képernyőképe")

- A megfelelő végrehajtási szekvencia biztosításához a tesztesetek készletekbe rendezéséhez, hogy a teszt-végrehajtási naplók begyűjthetők legyenek a további jelentésekhez és vizsgálatokhoz, a telepített topológiából hozzáférést kell biztosítani az Azure DevOps megoldáshoz.
- A példában olvasható példához javasoljuk, [hogy töltse le az ER-használatot AZ RSAT-tesztekhez](https://go.microsoft.com/fwlink/?linkid=874684). Ez a zip-fájl a következő feladat-útmutatókat tartalmazza:

    | Tartalom                                           | Fájlnév és hely |
    |---------------------------------------------------|------------------------|
    | Minta feladatrögzítés a teszt adatainak előkészítéséhez | Prepare\\Recording.xml |
    | Minta feladatrögzítés a szállítói fizetés feldolgozásához   | Process\\Recording.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>A Kötelezettségek modul előkészítése a szállítói kifizetések feldolgozására

1. Jelentkezzen be a példányába.
2. A következő ER-konfigurációk letöltése az LCS-ből. Az utasításokért lásd: [ER - A konfiguráció importálása a Lifecycle Services szolgáltatásból](./tasks/er-import-configuration-lifecycle-services.md)

    - **Fizetések modell** elektronikus jelentéskészítés modellkonfiguráció
    - **Fizetési modell hozzárendelése 1611** ER modell leképezésének konfigurációja
    - **BACS (UK)** ER formátumkonfiguráció

    ![Elektronikus jelentéskészítési konfigurációk.](media/GER-Configurations.png "Képernyőkép – az elektronikus jelentéskészítés Konfigurációk oldala")

3. Válassza ki a **GBSI** bemutatóadat-vállalatot, amelynek ország/régió környezete van Nagy-Britanniában.
4. Kötelezettségek paramétereinek konfigurálása:

    1. Nyissa meg a következőt: **Kötelezettségek \> Kifizetés beállítása \> Fizetési módok**.
    2. Válassza ki a kifizetések **Elektronikus** módszerét.
    3. A kiválasztott fizetési mód konfigurálása annak érdekében, hogy a program a **BACS (UK)** által korábban letöltött ER-formátumot használja a szállítói kifizetések feldolgozására.

        1. Adja meg a **Fájlformátumok** gyorslap **Általános elektronikus export formátum** beállítását **Igen** értékre.
        2. Az **Exportformátum konfigurációja** mezőben válassza a következőt: **BACS (UK)**.

    ![Fizetési módok oldala.](media/GER-APParameters.png "A fizetési módok lapjának képernyőképe")

    > [!NOTE]
    > Ha rendelkezik a testreszabások támogatásához létrehozott ER-formátum származtatott változatával, akkor ezt a konfigurációt az **Elektronikus** fizetési mód alapján is kiválaszthatja.

5. Hozzon létre egy példa szállítói kifizetést:

    1. Ugorjon a **Kötelezettségek \> Fizetési beállítás \> Fizetési napló** pontra.
    2. Győződjön meg róla, hogy nincs feladva a kifizetési napló.

        ![Fizetési napló oldala.](media/GER-APJournal.png "A fizetési napló lapjának képernyőképe")

    3. Válassza ki a **Sorokat**, és adja meg a következő adatokat tartalmazó sort.

        | Mező               | Példa érték   |
        |---------------------|-----------------|
        | Szállító neve         | GB\_SI\_000001  |
        | Tartozik               | 1,000.00        |
        | Pénznem            | GBP             |
        | Ellenszámla típusa | Bank            |
        | Ellenszámla      | GBSI MŰV.       |
        | Fizetési mód   | Elektronikus      |

    ![Szállítói kifizetések oldala.](media/GER-APJournalLines.png "A szállítói kifizetések lapjának képernyőképe")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Az ER-keretrendszer előkészítése a szállítói kifizetések feldolgozásának tesztelésére

### <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása

1. Lépjen a **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Elektronikus jelentéskészítési paraméterek** menüpontba.
2. A **Mellékletek** lap **Kiindulási** mezőjében válassza ki a **Fájlt**, amelyet a dokumentumkezelési (DM) keretrendszer használ a kiindulási funkcióhoz a DM-rel kapcsolatos dokumentumok megtartására DM-mellékletekként.

    ![Elektronikus jelentéskészítés paraméterei lap.](media/GER-ERParameters.png "Az elektronikus jelentéskészítési paraméterek oldal képernyőképe")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>A szállítói kifizetésekhez kapcsolódó dokumentumok kiindulási másolatainak létrehozása

1. Ugorjon a **Kötelezettségek \> Fizetési beállítás \> Fizetési napló** pontra.
2. **Sorok** kiválasztása.
3. **Kifizetések létrehozása** kiválasztása.
4. Válassza ki a kifizetések **Elektronikus** módszerét.
5. **GBSI OPER** bankszámla kijelölése.
6. Állítsa az **Ellenőrzési jelentés nyomtatása** opciót **Igen** értékre.
7. A létrejövő kimenet zip-fájlként tölthető le.
8. A letöltött fájl megnyitása.
9. Bontsa ki a következő fájlokat a letöltött fáljból:

    - **Fájl** - kifizetési fájl szöveges formátumban
    - **ERVendOutPaymControlReport** - ellenőrzési jelentés, XLSX formátumú

    ![Kibontott fájlok.](media/GER-APJournalProcessed.png "Képernyőkép a kibontott fájlnevekről a Windows Intézőben")

### <a name="turn-on-the-er-baseline-feature"></a>Az ER kiindulási funkció bekapcsolása

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A Művelet panel **Konfigurációk** lapján válassza a **Felhasználói paraméterek** menüpontot.
3. A **Futtatás hibakeresési módban** beállítása legyen **Igen**.

A **Futtatás hibakeresési módban** paraméter bekapcsolásával a következő műveleteket hajtathatja végre kötelező jelleggel az ER-keretrendszerrel a kimenő dokumentumokat létrehozó ER-formátumok végrehajtása után:

1. Annak meghatározása, hogy van-e kiindulási konfiguráció beállítva a teljesített ER-formátum bármelyik összetevőjéhez.
2. Annak a meghatározása, hogy az egyes konfigurált alaptervek az aktuális feltételek között érvényesek-e (a vállalat bejelentkezett vállalatának, fájlnevének és fájlnév-kiterjesztésének vállalati kódja stb.).
3. A következő műveleteket kell végrehajtani a megfelelő alaptervek esetében:

    1. A megfelelő alaptervvel összehasonlítani azt a kimenetet, amelyet a program az ER-formátumának végrehajtásakor generál.
    2. Az összehasonlítás eredményének tárolása az ER-konfigurációk hibakeresési naplójában.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>A szállítói kifizetések feldolgozásához használt ER-alaptervek konfigurálása

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. **Alaptervek** kiválasztása.
3. Válassza az **Új** lehetőséget.
4. A **Referencia** mezőben válassza a következőt: **BACS (UK)**.
5. **Mellékletek** kiválasztása.
6. Új alapterv hozzáadása a szállítói kifizetési fájlhoz:

    1. Válassza az **Új** lehetőséget.
    2. A **Típus** mezőben válassza ki azt a **Fájl** DM-dokumentumtípust, amelyet az ER-paraméterei között a kiindulási eltérések tárolására állított be.
    3. Tallózással válassza ki a helyileg mentett **Fájl** kifizetési fájlformátumot szöveges formátumban.
    4. A **Leírás** mezőbe írja be **Kifizetési TXT-fájl**.

7. Új alapterv hozzáadása a szállítói kifizetéshez tartozó ellenőrzési jelentéshez:

    1. Válassza az **Új** lehetőséget.
    2. A **Típus** mezőben válassza ki azt a **Fájl** DM-dokumentumtípust, amelyet az ER-paraméterei között a kiindulási eltérések tárolására állított be.
    3. Tallózással válassza ki a helyileg mentett **ERVendOutPaymControlReport** ellenőrzésijelentés-fájlt XLSX formátumban.
    4. A **Leírás** mezőbe írja be **Kifizetési XLSX ellenőrzési jelentés**.

    ![Alapterv a szállítói kifizetési fájlhoz és ellenőrzési jelentéshez.](media/GER-BaselineAttachments.png "Képernyőkép a konfigurációk lapról a kiválasztott kifizetési XLSX ellenőrzési jelentéssel")

8. Zárja be a lapot.
9. Az **Alaptervek** gyorslapon válassza az **Új** parancsot a kifizetési fájl kiindulásának konfigurálásához:

    1. A sorhoz tartozó **Kiindulási beállítás a kifizetési fájlhoz** neve.
    2. A **Fájlösszetevő neve** mezőben válassza ki **Fájl** lehetőséget, hogy ezt az alaptervet kelljen alkalmazni az ER-formátum kimenetére, amely a BACS (Egyesült Királyság) szöveges formátumban hozza létre a kifizetési fájlt.
    3. Válassza ki a **Vállalatok** mezőben a **GBSI** lehetőséget, amelyre alkalmazni szeretné ezt az alaptervet, ha ha a GBSI vállalatban futtatja a **BACS (UK)** ER-formátumát.
    4. A **Fájlnév-maszk** mezőbe írja be a **\*. TXT** elemet, hogy ezt az alaptervet csak az olyan **fájl** formátum-összetevő kimeneteire alkalmazza, amelyek a **.txt** fájlnévkiterjesztéssel rendelkeznek.
    5. Az **Alapterv** mezőben válassza a **Kifizetési TXT-fájlt**, hogy ez az alaptervet használja a létrejövő kimenethez történő összehasonlításhoz.

10. Válassza az **Új** parancsot az ellenőrzési jelentés alapterv konfigurálásához:

    1. A sorhoz tartozó **Kiindulási beállítás az Ellenőrzési jelentéshez** neve.
    2. A **Fájlösszetevő neve** mezőben válassza ki **ERVendOutPaymControlReport** lehetőséget, hogy ezt az alaptervet kelljen alkalmazni az ER-formátum kimenetére, amely a BACS (Egyesült Királyság) szöveges formátumban hozza létre az ellenőrzési jelentést.
    3. Válassza ki a **Vállalatok** mezőben a **GBSI** lehetőséget, amelyre alkalmazni szeretné ezt az alaptervet, ha ha a GBSI vállalatban futtatja a **BACS (UK)** ER-formátumát.
    4. A **Fájlnév-maszk** mezőbe írja be a **\*. XLSX** elemet, hogy ezt az alaptervet csak az olyan **ERVendOutPaymControlReport** formátum-összetevő kimeneteire alkalmazza, amelyek a **.xslx** fájlnévkiterjesztéssel rendelkeznek.
    5. Az **Alapterv** mezőben válassza a **Kifizetési XLSX ellenőrzési jelentést**, hogy ez az alaptervet használja a létrejövő kimenethez történő összehasonlításhoz.

    ![Alaptervek gyorslap a Konfigurációk oldalon.](media/GER-BaselineRules.png "Képernyőkép – Alaptervek gyorslap a Konfigurációk oldalon")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Tesztek rögzítése a szállítói kifizetések feldolgozásának ellenőrzéséhez

Funkcionális kiemelt felhasználóként a saját lépéseket rögzítheti a szállítói kifizetések feldolgozásának teszteléséhez. Javasoljuk, hogy játsszon (és szükség szerint szerkessze) a **Prepare\\Recording.xml** korábban letöltött feladatrögzítést. Ez a rögzítés az összes vizsgálati adat helyes állapotának beállítására szolgál. Ezt a lépést kötelező megadni, mert a teszt többször is elvégezhető, és minden tesztnek azonos állapotban lévő adatokat kell használnia.

### <a name="reset-user-settings"></a>Felhasználói beállítások alaphelyzetbe állítása

1. Nyissa meg az Alapértelmezett irányítópultot.
2. Válassza ki a **Beállítások** gombot (a fogaskerék szimbólum).
3. Válassza a **Felhasználói beállítások** elemet.
4. Válassza a **Használati adatok** elemet.
5. **Alaphelyzet** kiválasztása.
6. Válassza az **Igen** lehetőséget a használati adatok alaphelyzetbe állításának jóváhagyásához.
7. Zárja be a lapot.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>A tesztelési adatok előkészítéséhez szükséges lépések rögzítése

1. Válassza ki a **Beállítások** gombot (a fogaskerék szimbólum).
2. **Feladatrögzítő** kiválasztása.
3. Válassza a **Rögzített anyag lejátszása** elemet.
4. Válassza a **Megnyitás erről a PC-ről** elemet.
5. Válassza a **Tallózás** lehetőséget, majd válassza a helyben mentett **Prepare\\Recording.xml** fájlt.
6. Válassza az **Indítás** lehetőséget.
7. Válassza ki folyamatosan a **Következő függőben lévő lejátszási lépés** elemet addig, amíg a rögzítés minden lépését le nem játszották.

A feladatrögzítés a következő műveleteket hajtja végre:

1. A feldolgozott kifizetési sor állapotának **Nincs** értékre állítása.

    ![3–4. lépés a feladatok rögzítésére.](media/GER-Recording1Review1.png "A 3 – 4. lépés a feladatok rögzítésére vonatkozóan képernyőkép")

2. Kapcsolja be a **Futtatás hibakeresési módban** ER felhasználói paramétert.

    ![9–10. lépés a feladatok rögzítésére.](media/GER-Recording1Review2.png "A 9 – 10. lépés a feladatok rögzítésére vonatkozóan képernyőkép")

3. A feladott fájloknak és az alapterv összehasonlításának eredményeit tartalmazó ER hibakeresési napló karbantartása.

    ![13–15. lépés a feladatok rögzítésére.](media/GER-Recording1Review3.png "A 13 – 15. lépés a feladatok rögzítésére vonatkozóan képernyőkép")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Lépések rögzítése a szállítói kifizetések feldolgozásának teszteléséhez

Javasoljuk, hogy játsszon (és szükség szerint szerkessze) a **Process\\Recording.xml** korábban letöltött feladatrögzítést. Ez a rögzítés a szállítói kifizetések feldolgozására és a létrejövő dokumentumok és a megfelelő alaptervek összehasonlítási eredményeinek ellenőrzésére szolgál.

1. Válassza ki a **Beállítások** gombot (a fogaskerék szimbólum).
2. **Feladatrögzítő** kiválasztása.
3. Válassza a **Rögzített anyag lejátszása** elemet.
4. Válassza a **Megnyitás erről a PC-ről** elemet.
5. Válassza a **Tallózás** lehetőséget, majd válassza a helyben mentett **Process\\Recording.xml** fájlt.
6. Válassza az **Indítás** lehetőséget.
7. Válassza ki folyamatosan a **Következő függőben lévő lejátszási lépés** elemet addig, amíg a rögzítés minden lépését le nem játszották.

A feladatrögzítés a következő műveleteket hajtja végre:

1. Szállítói kifizetések feldolgozásának megkezdése.
2. Válassza ki a megfelelő futásidejű paramétereket, és kapcsolja be az ellenőrzési jelentés létrehozását.

    ![3–8. lépés a feladatok rögzítésére.](media/GER-Recording2Review1.png "A 3 – 8. lépés a feladatok rögzítésére vonatkozóan képernyőkép")

3. A létrehozott kimenetek és a megfelelő alaptervek összehasonlításának eredményeinek rögzítéséhez hozzáférés az ER hibakeresési naplóhoz.

    Az ER hibakeresési naplóban az összehasonlítás eredményei megjelennek a **Létrehozott szöveg** mezőben. A **Formátum összetevője** és a **Formátum elérési útja, amely naplóbejegyzést generát** mezők arra a fájl-összetevőre utalnak, amelyhez a létrejövő kimenetet összehasonlították az alaptervvel.

    ![Bejegyzések az Elektronikus jelentéskészítés futtatási naplói oldalon.](media/GER-ERDebugLog.png "Az elektronikus jelentéskészítési futtatási naplók oldal bejegyzéseinek képernyőképe")

4. Az aktuális kimenetnek az alaptervhez történő összehasonlítását a Feladatrögzítő **Érvényesítés** lehetőségének használatával, és az **Aktuális érték** kiválasztásával lehet rögzíteni.

    ![Az Ellenőrzés beállítás használata az aktuális értékkel való összehasonlításra.](media/GER-TRRecordValidation.png "Képernyőkép: Az Ellenőrzés beállítás használata az aktuális értékkel való összehasonlításra")

    A következő ábra bemutatja, hogy a rögzített ellenőrzési lépések hogy néznek ki a feladatrögzítésben.

    ![13. és 15. lépés a feladatok rögzítésére.](media/GER-Recording2Review2.png "A 13. és 15. lépés a feladatok rögzítésére vonatkozóan képernyőkép")

## <a name="add-the-recorded-tests-to-azure-devops"></a>A rögzített tesztek hozzáadása ehhez: Azure DevOps

1. Az Azure DevOps környezet megnyitása.
2. Válassza ki azt a projektet, amelyet az RSAT paramétereiben határozott meg az [eszköz konfigurálása](#prerequisites) során.
3. Válassza ki azt a teszttervet, amelyet az RSAT paramétereiben határozott meg az [eszköz konfigurálása](#prerequisites) során.
4. Új teszteset létrehozása a kiválasztott teszttervhez:

    1. A teszteset neve legyen ez: **Szállító elektronikus fizetése feldolgozásának teszteléséhez szükséges adatok előkészítése**.
    2. Csatolja a korábban letöltött **Recording.xml** fájlt a **Prepare** mappából.

5. Új teszteset létrehozása a kiválasztott teszttervhez:

    1. A teszteset neve legyen ez: **Szállítói kifizetések feldolgozásának tesztelése a BACS (UK) ER-formátum használatával**.
    2. Csatolja a korábban letöltött **Recording.xml** fájlt a **Process** mappából.

    ![Új tesztesetek a kiválasztott teszttervhez.](media/GER-RSAT-DevOps-Tests-Passed.png "Képernyőkép: Új tesztesetek a kiválasztott teszttervhez")

> [!NOTE]
> Ügyeljen a hozzáadott tesztek helyes végrehajtási sorrendjére.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>RSAT-előkészítése a rögzített tesztek futtatásához

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>A tesztek betöltése a következőből: Azure DevOps, ide: RSAT

1. Nyissa meg a helyi RSAT alkalmazást az aktuális topológiában.
2. Válassza ki a **Terhelést** a jelenleg az Azure DevOps-ban található tesztek betöltéséhez az RSAT-be.

    ![A RSAT rendszerbe betöltött tesztek.](media/GER-RSAT-RSAT-Tests-Loaded.png "A RSAT rendszerbe betöltött tesztek képernyőképe")

### <a name="create-automation-and-parameters-files"></a>Automatizálási és paraméterfájlok létrehozása

1. Az RSAT-ben válassza ki a teszteket, amelyeket betöltött innen: Azure DevOps.
2. Válassza az **Új** lehetőséget az RSAT automatizálási és paraméterfájlok létrehozásához.

    ![RSAT automatizálási és paraméterfájlok létrehozva az RSAT-ban.](media/GER-RSAT-RSAT-Tests-Initiated.png "Képernyőkép: RSAT automatizálási és paraméterfájlok létrehozva az RSAT-ban")

### <a name="modify-the-parameters-files"></a>A paraméterfájlok módosítása

1. Az RSAT-ban válassza ezt a tesztesetet: **Szállító elektronikus fizetése feldolgozásának teszteléséhez szükséges adatok előkészítése**.
2. Válassza ki a **Szerkesztés** opciót.
3. A megnyíló Microsoft Excel munkafüzetben, az **Általános** munkalapon módosítsa a vállalati kódot a **GBSI** értékre, mert ez a vállalat fog a teszt-végrehajtásra szolgálni.
4. Az RSAT-ban válassza ki ezt a tesztesetet: **Szállítói kifizetések feldolgozásának tesztelése a BACS (UK) ER-formátum használatával**.
5. Válassza ki a **Szerkesztés** opciót.
6. A megnyitott Excel-munkafüzetben, az **Általános** munkalapon módosítsa a vállalati kódot erre: **GBSI**.
7. Az **ERFormatMappingRunLogTable** munkalapon figyelje meg, hogy az A:3 és a C:3 cellák tartalmazzák az ER hibakeresési naplójának azon mezőinek szövegét, amelyek a kimenetnek az alaptervhez történő összehasonlításának eredményeinek ellenőrzésére szolgálnak. A program ezeket a szövegeket használja a teszt végrehajtása során létrejövő ER hibakeresési napló rekordok értékelésére.

    ![ERFormatMappingRunLogTable-munkalap.](media/GER-RSAT-RSAT-ExcelParameters.png "A ERFormatMappingRunLogTable munkalap képernyőképe")

## <a name="run-the-tests-and-analyze-the-results"></a>A tesztek futtatása és az eredmények elemzése

### <a name="run-the-tests-in-rsat"></a>A tesztek futtatása az RSAT-ben

1. Az RSAT-ben válassza ki a betöltött teszteket.
2. Válassza a **Futtatás** parancsot.

Figyelje meg, hogy a teszteseteit a program webböngészővel automatikusan futtatja az alkalmazásban.

### <a name="analyze-the-results-of-test-execution"></a>A tesztvégrehajtásának eredményeinek elemzése

A teszt végrehajtásának eredményeit az RSAT tárolja. Figyelje meg, hogy mindkét teszt átment ereménnyel zárult.

![A RSAT-ben átadott tesztek.](media/GER-RSAT-RSAT-Tests-Passed.png "A RSAT-ben átadott tesztek képernyőképe")

Figyelje meg, hogy a teszt végrehajtásának eredményeit az Azure DevOps is megkapja, így további elemzést végezhet.

![A teszt végrehajtásának eredményei az Azure DevOps szolgáltatásban](media/GER-RSAT-DevOps-Tests-Added.png "A tesztvégrehajtás eredményeinek képernyőképe az Azure DevOps-ban")

### <a name="simulate-a-situation-where-tests-fail"></a>Olyan helyzet szimulálása, amikor a teszt eredménye sikertelen

A tesztkészlet eredményének bukásnak kell lennie, ha a létrejövő kimenetek közül legalább egy nem egyezik meg a megfelelő alaptervvel. Ennek a helyzetnek a elérése érdekében használhatja a **BACS (UK)** formátumának származtatott változatát, amely olyan kifizetési fájlt fog generálni, amely a megfelelő alaptervtől különböző tartalmú. Ennek a helyzetnek a szimulálása érdekében ugyanaz a **BACS (UK)** formátum használható, de a fizetési összeget módosítsa a feldolgozott kifizetési sorban.

1. Nyissa meg az alkalmazást, és válassza a **Kötelezettségek \> Kifizetések \> Kifizetési napló** elemet.
2. **Sorok** kiválasztása.
3. Válassza ki a kifizetési sort, majd válassza a **Kifizetési állapota \> Nincs** elemet.
4. A **Terhelés** mezőben módosítsa az értéket erről: **1 000,00**, erre: **2 000,00**.
5. A változtatások mentéséhez válassza a **Mentés** elemet.

### <a name="run-the-tests-in-rsat"></a>A tesztek futtatása az RSAT-ben

1. Az RSAT-ben válassza ki a betöltött teszteket.
2. Válassza a **Futtatás** parancsot.

Figyelje meg, hogy a teszteseteit a program webböngészővel automatikusan futtatja az alkalmazásban.

### <a name="analyze-the-results-of-test-execution"></a>A tesztvégrehajtásának eredményeinek elemzése

A teszt végrehajtásának eredményeit az RSAT tárolja. Figyelje meg, hogy a második teszt nem sikerült a második végrehajtás során.

![Sikertelen teszteredmények az RSAT-ban.](media/GER-RSAT-RSAT-Tests-Failed.png "A sikertelen teszteredményeinek képernyőképe az RSAT-ban")

Figyelje meg, hogy a teszt végrehajtásának eredményeit az Azure DevOps is megkapja, így további elemzést végezhet.

![Sikertelen teszteredmények az Azure DevOps-ban](media/GER-RSAT-DevOps-Tests-Failed.png "A sikertelen teszteredményeinek képernyőképe az Azure DevOps-ban")

Minden teszt állapotát elérheti. A végrehajtási naplót is megnyithatja, hogy elemezze az összes sikertelenség okát. A következő ábrán a végrehajtási napló azt mutatja, hogy a hiba a létrejövő kifizetési fájl és annak alapterve között fennálló tartalmi eltérés miatt történt.

![Végrehajtási napló a hibaelemzéshez az Azure DevOps-ban](media/GER-RSAT-DevOps-Tests-Failed-Log.png "A hiba elemzéséhez szükséges végrehajtási napló képernyőképe az Azure DevOps-ban")

Éppen ezért, ahogy láttuk, minden ER-formátum működése automatikusan kiértékelhető az RSAT használatával tesztplatformként, és Feladatrögzítő alapú tesztek alkalmazásával, amelyek az ER kiindulási funkciót használják.

## <a name="additional-resources"></a>További erőforrások

- [Feladatrögzítő erőforrásai](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Felhasználói tesztelés létrehozása és automatizálása](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [A folyamatos build- és tesztautomatizálást támogató környezetek telepítése és használata](../perf-test/continuous-build-test-automation.md)
- [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md)
- [ER – A formátum frissítése ezen formátum új alapverziójának elfogadásával](tasks/er-upgrade-format.md)
- [ER - A konfiguráció importálása a Lifecycle Services szolgáltatásból](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]