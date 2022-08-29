---
title: Az ER-alapú megoldások teljesítményének javítása a futásidőben behívott táblamezők számának csökkentésével
description: Ez a cikk bemutatja, hogy hogyan javíthatja a teljesítményt a futásidőben bekért táblamezők számának csökkentésével.
author: kfend
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.custom: ''
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: 5c9481f1021a5dba6e1d4020bbf85a10bd551ac0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278826"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Az ER-alapú megoldások teljesítményének javítása a futásidőben behívott táblamezők számának csökkentésével

[!include[banner](../includes/banner.md)]

Az elektronikus jelentéskészítő [(ER](general-electronic-reporting.md)) [formátumokat meg lehet tervezni,](er-overview-components.md#format-components-for-outgoing-electronic-documents) amelyek különböző formátumokban generálják a kimenő dokumentumokat. Dokumentum generálása esetén az ER-formátum hívja meg a megfelelő ER [modellleképezésben beállított adatforrásokat](er-overview-components.md#model-mapping-component). A rekordlekéréshez szükséges alkalmazástáblákhoz, lekérdezésekhez és entitásokhoz való hozzáférés beállításához a táblarekord-típus ER-adatforrásait *használhatja*. Alapértelmezés szerint a Tábla rekordtípus egyik *adatforrása* a kért rekordok összes mezőjének értékét olvassa be. Konfigurálhatja azonban ezt az adatforrást úgy, hogy csak a futó ER-formátumhoz szükséges mezőértékeket használja. Ez a konfiguráció segít csökkenteni az adatkeresést és további rekord-gyorsítótárazást végző alkalmazáskiszolgáló memóriafelhasználását.

Ha többet szeretne tudni arról, hogyan *lehet* korlátozni a Tábla rekordtípus adatforrás-beolvasási mezőinek listáját, akkor ezt a példát kell bemutatja ebben a cikkben.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Példa: csökkentse a futásidőben bekért táblamezők számát.

A következő eljárások be mutatják, hogyan konfigurálhat egy ER-modellleképezést a rendszergazdai vagy elektronikus jelentéskészítő szerepkörű felhasználók úgy, hogy csak az ER-formátum futtatásához szükséges mezőket kapják meg az alkalmazáskiszolgáló memóriafelhasználásának csökkentése érdekében.

Ezeket az eljárásokat az **USMF** vállalatnál Microsoft Dynamics, a 365 Pénzügyben lehet végrehajtani. Nincs szükség kódolásra.

A példához **az alábbi szerepkörök egyikével kell hozzáférnie az USMF** vállalathoz:

- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Ebben a példában a [Litware](general-electronic-reporting.md#Configuration)**, Zrt. mintavállalat er-konfigurációit** fogja használni. Győződjön meg róla **, hogy a Litware, Zrt.** (`http://www.litware.com`) mintavállalat konfigurációs szolgáltatója szerepel az ER keretrendszerben, és hogy Aktívként **van-e megjelölve**. Ha ez a konfigurációs szolgáltató nem szerepel a listán, **vagy** ha nem Aktív jelölésű, kövesse a Konfigurációszolgáltató létrehozása lépést, [és jelölje meg aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást be kell fejeznie, mielőtt az ER keretrendszert használva módosítja a megadott ER-megoldás adatforrását.

### <a name="import-the-sample-er-configurations"></a>Minta ER-konfigurációk importálása

Ha még [nem fejeződött be az új ER-megoldás megtervezése abban a példában, amely egyéni jelentéscikket nyomtat, töltse le és tárolja helyben a](er-quick-start1-new-solution.md) megadott ER-megoldás következő konfigurációihoz használható XML-fájlokat.

| Tartalom leírása            | Fájlnév |
|--------------------------------|-----------|
| ER-adatmodell konfigurációja    | [Kérdőívek model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| ER-modell leképzési konfigurációja | [Kérdőív-hozzárendelés.verzió.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| ER-formátum konfigurációja        | [Kérdőívek format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Ezután a következő lépések szerint töltheti fel a megadott ER-megoldás konfigurációit a Pénzügy példányba.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. Importálja a **Konfigurációk lapon** az ER adatmodell konfigurációját.

    1. Válassza az **Exchange** elemet, majd válassza az **XML-fájlból történő betöltést**.
    2. Válassza **a Tallózás** lehetőséget, keresse meg és válassza **ki a Kérdőívek modell.version.1.xml** fájlt, majd kattintson az **OK gombra**.

4. Az ER modellleképezés konfigurációjának importálása.

    1. Válassza az **Exchange** elemet, majd válassza az **XML-fájlból történő betöltést**.
    2. Válassza **a Tallózás** lehetőséget, keresse meg és válassza **ki a Kérdőívek leképezése.1.1.xml fájlt**, majd kattintson az **OK gombra**.

5. Az ER-formátum konfigurációjának importálása.

    1. Válassza az **Exchange** elemet, majd válassza az **XML-fájlból történő betöltést**.
    2. Válassza **a Tallózás** lehetőséget, keresse meg és válassza **ki a Kérdőívek formátumát.1.1.xml fájl**, majd kattintson az **OK gombra**.

6. A konfigurációs fában bontsa ki a **Kérdőívek modellt**.
7. Tekintse át a konfigurációs fában importált ER-konfigurációk listáját.

    ![Az importált ER-konfigurációk listájának áttekintése a Konfigurációk lapon.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>A megadott ER modell megfeleltetésének áttekintése

1. A Konfigurációk **lapon** válassza ki a Kérdőívek **megfeleltetése lehetőséget**.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. A Modell és **adatforrás megfeleltetése lapon** válassza a Tervező **lehetőséget**.
4. A Modellleképezés tervezőlapján **, a munkaablakon a** Csoport nézet **gombra kattintva kapcsolja be a** Csoport nézetet **.**
5. Bontsa ki **a** Kérdőív adatokat az Adatmodell **ablakban**.

    Figyelje meg, hogy **a kérdőív** adatforrás úgy van beállítva, hogy hozzáférjen az alkalmazástáblához`KMCollection`.

6. Az Adatforrások **ablakban bontsa ki a** Táblarekordok **kérdőívmezőit** \> **·** \> **.**

    Figyelje meg, hogy az `KMCollection`**alkalmazástábla** hány mezőjét teszi elérhetővé a Tábla rekordtípus Kérdőív *adatforrása*.

    ![A megadott modellleképezések áttekintése a modellleképezés tervezőlapján, ha a Csoport nézet be van kapcsolva.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. A műveletpanelen a Csoport **nézet** **beállításhoz** ismét válassza ki a Csoport nézetet, **·** \> **majd** válassza a Csak a leképezve megjelenítése lehetőséget.

    Ne feledje, `KMCollection` hogy az alkalmazástábla néhány mezője használatos a Kérdőív rekordlista **kitöltésére** az ER adatmodellben:

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![A megadott modellleképezések áttekintése a modellleképezés tervezőlapján, ha a Csoport nézet ki van kapcsolva.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Az ER teljesítmény-nyomkövetésének bekapcsolása

Hajtsa végre az ER-teljesítménykövetés [bekapcsolt](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) folyamatának lépéseit az ER-felhasználók paramétereinek beállításéhez, amelyek lehetővé teszik az ER-összetevők végrehajtásának nyomon követését.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>A megadott ER-formátum futtatása a megadott modellleképezéssel

Kövesse az ER-től [származó](er-quick-start1-new-solution.md#RunFormatFromER) tervezett formátum futtatásához szükséges lépéseket, ha egyetlen kérdőívhez a Konfigurációk lapon megadott **ER-formátumot futtatja**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Az első futtatás végrehajtási nyomkövetésének áttekintése

1. Ugrás a Szervezet felügyelete **–** \> **Elektronikus jelentési \> konfigurációkhoz.**
2. A Konfigurációk **lapon bontsa** ki **a Kérdőívek modellt**, és válassza a **Kérdőívek megfeleltetése lehetőséget**.

    > [!NOTE]
    > A Verziók gyorsábra **részletei** azt jelzik, hogy a kérdőív-hozzárendelési konfiguráció vázlatverzióját **választotta** ki. Ennek megfelelően módosíthatja ennek a modellleképezésnek a tartalmát.

3. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
4. A Modell és **adatforrás megfeleltetése lapon** válassza a Tervező **lehetőséget**.
5. A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.
6. A Teljesítménykövetés **eredményének** beállításai párbeszédpanelen válassza ki a legutóbbi futtatáskor létrehozott nyomkövetést.

    ![A nyomkövetés kiválasztása a Teljesítménykövetés eredményének beállításai párbeszédpanelen.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Válassza ki az **OK** lehetőséget. 
8. A Részletek **gyorstára** segítségével **szűrje** ki a Kérdőív adatforrásra mutató **kérdőív** elérési útját.
9. Tekintse át a kérdőív adatforrásának **hívása** során generált adatbázis-lekérdezés részleteit.

    Ne figyelje meg, hogy futásidőben `KMCollection` történt az alkalmazástábla **összes** mezőjének beolvasása a kérdőív adatforrásának hívása során.

    ![Az adatbázis-lekérdezés részleteinek áttekintése a modellleképezés tervezőlapján.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>A megadott ER modellleképezés módosítása

1. A Modellleképezés tervezőlap **Adatforrások** ablakában **válassza ki a Kérdőív adatforrást** **.**
2. Az Adatforrások **ablakban** válassza a Szerkesztés **lehetőséget**.
3. Az Adatforrás **tulajdonságai párbeszédpanelEn jelölje be a Mezők kijelölése lehetőséget a hivatkozott alkalmazástábla azon mezőinek megadásához,** **·**`KMCollection` amelyek beolvasása futásidőben történik a szerkeszthető kérdőív adatforrásának **hívása során.**

    ![Ha el szeretné kezdeni az alkalmazástáblából beolvasásra használt mezők listáját a szerkeszthető adatforrás használatával, válassza a Mezők kiválasztása lehetőséget az Adatforrás tulajdonságai párbeszédpanel Kiválasztás lehetőségének beállításához.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. A Mezők **kiválasztása lapon** válassza az Automatikus **kitöltés lehetőséget**.

    A **program** automatikusan kitölti a Kiválasztott mezők listáját a modellleképezés előre konfigurált műveletei alapján. A hivatkozott tábla minden olyan mezője és kapcsolata megjelenik a listában, amely a modellleképezés bármely kötésében, képletében vagy adatforrásában szerepel.

    ![Azon mezők listájának konfigurálása, amelyek a Mezők kiválasztása lapon található alkalmazástáblából lesznek beolvasásra.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Válassza a **Mentés** lehetőséget, és zárja be a Mezők kijelölése **lapot**.
6. Az **OK** gombra választva tárolni tudja az adatforrás beállításaiban végrehajtott módosításokat.
7. A műveletpanelen válassza az Összes **megjelenítése lehetőséget**.

    Ne figyelje meg, hogy **a** kérdőív adatforrása most megjeleníti a szöveget **\<Fields are filtered\>**. Ez a szöveg azt jelzi, hogy az adatforrás korlátozott számú mező beolvasására van konfigurálva a hivatkozott alkalmazástáblából.

    ![A frissített modellleképezés áttekintése a modellleképezés tervezőlapján.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. A **szerkeszthető** modellleképezésen végrehajtott módosítások tárolására a Mentés lehetőséget választva.

    > [!NOTE]
    > Futásidőben az ER elemzi a hozzáadott kapcsolatokat, és hozzáad minden, az adatbázisban használt mezőt az adatbázis-lekérdezéshez, még akkor is, ha ezek a mezők nem voltak kifejezetten hozzáadva a tervezési időben bekért mezők listájához.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>A megadott ER-formátum futtatása a frissített modellleképezés használatával

Kövesse az ER-től [származó](er-quick-start1-new-solution.md#RunFormatFromER) tervezett formátum futtatásához szükséges lépéseket, ha egyetlen kérdőívhez a Konfigurációk lapon megadott **ER-formátumot futtatja**.

### <a name="review-the-execution-trace-of-the-second-run"></a>A második futtatás végrehajtási nyomkövetésének áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lapon bontsa** ki **a Kérdőívek modellt**, és válassza a **Kérdőívek megfeleltetése lehetőséget**.
3. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
4. A Modell és **adatforrás megfeleltetése lapon** válassza a Tervező **lehetőséget**.
5. A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.
6. A Teljesítménykövetés **eredményének** beállításai párbeszédpanelen válassza ki a legutóbbi futtatáskor létrehozott nyomkövetést.
7. Válassza ki az **OK** lehetőséget.
8. A Részletek **gyorstára** segítségével **szűrje** ki a Kérdőív adatforrásra mutató **kérdőív** elérési útját.
9. Tekintse át a kérdőív adatforrásának **hívása** során generált adatbázis-lekérdezés részleteit.

    Ne figyelje meg`KMCollection`, hogy a kérdőív adatforrásának hívatásakor csak az adatforrás kitöltéséhez szükséges mezőket beolvasása történt meg futásidőben az **alkalmazástáblából**.

    > [!NOTE]
    > Egyes mezőket, például a partícióazonosítót, az adatterület-azonosítót és a rekordazonosítót a Pénzügyi alkalmazás Adatkezelési keretrendszere automatikusan hozzáad.

    ![Az adatbázis-lekérdezés részleteinek áttekintése a frissített modellleképezésre a Modellleképezés tervezőlapján.](./media/er-reduce-fetched-fields-number-query2.png)

Ezzel a módszerrel csökkentheti a bekért rekordok számát, amikor az ER modell-hozzárendelés és ER-formátum használatával csökkentenie kell a memóriafelhasználást.

## <a name="limitations"></a>Korlátozások

Ha korlátozza a *Tábla* rekordtípus adatforrásának beolvasására használt mezők számát, nem használhatja azokat az alkalmazástáblákat, amelyekre az adatforrás hivatkozik, mivel az alkalmazás metaadatai nem biztosítanak adatokat az ilyen metódusok hívásához szükséges táblamezőkről.

## <a name="usage-notes"></a>Használati megjegyzések

**Bár az Automatikus kitöltés** parancs automatikusan hozzáad mezőket, a korábban hozzáadott mezőket nem törli automatikusan akkor sem, ha már nincsenek használva a szerkeszthető modellleképezés kötésekben, képletekben és adatforrásban.

Az Automatikus **kitöltés** beállítás kiválasztásakor az ER elemzi a kötéseket, a képleteket, valamint azokat az adatforrásokat, amelyekre a szerkeszthető modell leképezése történt a megnyitáskor szerkesztésre. Ha módosítja a szerkeszthető modellleképezés kötését, képletét és adatforrását, **és az Automatikus kitöltés** parancsot szeretné használni, zárja be a modellleképezés-tervezőt, majd nyissa meg újra a modellleképezés szerkesztéséhez. 

## <a name="additional-resources"></a>További erőforrások

- [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md)
- [Hibaelhárítás az ER-konfigurációk teljesítményével kapcsolatban](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
