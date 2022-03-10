---
title: Ismétlődő adatexportálási alkalmazás létrehozása
description: Ez a témakör leírja, hogyan hozhat létre egy olyan Microsoft Azure logikai alkalmazást, amely ismétlődő ütemezéssel exportálja az adatokat a Microsoft Dynamics 365 Human Resources rendszerből.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 368eee6bb182f363f47467a5c5ad8208a57db7ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069782"
---
# <a name="create-a-recurring-data-export-app"></a>Ismétlődő adatexportálási alkalmazás létrehozása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör leírja, hogyan hozhat létre egy olyan Microsoft Azure logikai alkalmazást, amely ismétlődő ütemezéssel exportálja az adatokat a Microsoft Dynamics 365 Human Resources rendszerből. Az oktatóanyag kihasználja a Human Resources DMF-csomagjának REST alkalmazásprogramozási felületét (API) az adatok exportálásához. Az adatok exportálása után a logikai alkalmazás az exportált adatcsomagot a Microsoft OneDrive for Business mappába menti.

## <a name="business-scenario"></a>Üzleti eset

A Microsoft Dynamics 365 integrációkkal kapcsolatos tipikus üzleti forgatókönyv esetében az adatokat ismétlődő ütemezéshez kell exportálni egy alsóbb rétegbeli rendszerbe. Ez az oktatóanyag bemutatja, hogy hogyan lehet exportálni az összes dolgozói rekordot a Microsoft Dynamics 365 Human Resources rendszerből, és menteni a dolgozók listáját egy OneDrive for Business mappába.

> [!TIP]
> Az ebben az oktatóanyagban exportált konkrét adatok, valamint az exportált adatok célja csupán példák. Ezeket egyszerűen megváltoztathatja az üzleti szükségletek kielégítése érdekében.

## <a name="technologies-used"></a>Használt technológiák

Ez az oktatóanyag a következő technológiákat használja:

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – Az exportálandó dolgozók alapadatforrása.
- **[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – az ismétlődő export vezénylését és ütemezését biztosító technológia.

    - **[Csatlakozók](/azure/connectors/apis-list)** – a logikai alkalmazás a szükséges végpontokhoz való csatlakoztatásához használt technológia.

        - [HTTP Azure AD](/connectors/webcontents/) csatlakozóval
        - [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness) csatlakozó

- **[DMF-csomag REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – az exportálás elindításához és a folyamat nyomon követéséhez használt technológia.
- **[OneDrive for Business](https://onedrive.live.com/about/business/)** – az exportált dolgozók célhelye.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené a feladatot ebben az oktatóanyagban, a következő elemekkel kell rendelkeznie:

- Olyan Human Resources-környezet, amely rendszergazdai engedélyekkel rendelkezik a környezetben
- Egy [Azure-előfizetés](https://azure.microsoft.com/free/) a logikai alkalmazás tárolásához

## <a name="the-exercise"></a>A feladat

A feladat végén talál egy logikai alkalmazást, amely kapcsolódik a Human Resources-környezetéhez és a OneDrive for Business fiókjához. A logikai alkalmazás egy adatcsomagot exportál a Human Resources-alkalmazásból, várja meg, hogy befejeződjön az exportálás, töltse le az exportált adatcsomagot, majd mentse az adatcsomagot a megadott OneDrive for Business mappába.

A befejeződött logikai alkalmazás a következő ábrához fog hasonlítani.

![Logikai alkalmazás áttekintése.](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>1. lépés: adatexportálási projekt létrehozása a Human Resources alkalmazásban

Olyan adatexportálási projekt létrehozása a Human Resources alkalmazásban, amely exportálja a dolgozókat. Nevezze el a projektet a következőre: **Dolgozók exportálása**, és győződjön meg arról, hogy az **Adatcsomag létrehozása** beállítás **Igen** értéken legyen. Adjon hozzá a projekthez egyetlen entitást (**Dolgozó**), majd válassza ki azt a formátumot, amelyben exportálni szeretne. (Az oktatóanyag Microsoft Excel-formátumot használ.)

![Dolgozói adatok projekt exportálása.](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Jegyezze meg az adatexportálási projekt nevét. Erre akkor lesz szükség, amikor a következő lépésben létrehozza a logikai alkalmazást.

### <a name="step-2-create-the-logic-app"></a>2. lépés: a logikai alkalmazás létrehozása

A feladat nagy része a logikai alkalmazás létrehozása lesz.

1. Hozzon létre egy logikai alkalmazást az Azure-portálon.

    ![Logikai alkalmazás létrehozása lap.](media/integration-logic-app-creation-1.png)

2. A Logic Apps Designer programban kezdje a munkát egy üres logikai alkalmazással.
3. Adjon hozzá egy [Ismétlődésütemezési indítót](/azure/connectors/connectors-native-recurrence) a logikai alkalmazás 24 óránként történő futtatásához (vagy az Ön által kiválasztott ütemezéshez).

    ![Ismétlődés párbeszédpanel.](media/integration-logic-app-recurrence-step.png)

4. Hívja az [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API-t az adatcsomag exportálásának ütemezése érdekében.

    1. A HTTP-ből válassza a **HTTP-kérelem hívása** műveletet az Azure AD-csatlakozó használatával.

        - **Alaperőforrás URL**: a Human Resources környezetének URL-címe (Ne tartalmazza az elérési útra/névtérre vonatkozó adatokat.)
        - **Azure AD Erőforrás URI-je:** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > A Human Resources-szolgáltatás még nem rendelkezik olyan csatlakozóval, amely megjeleníti a DMF-csomag REST összes API-ját (például **ExportToPackage**) alkotó API-kat. Ehelyett az API-kat a nyers HTTPS-kérésekkel kell hívnia a HTTP-n keresztül és az Azure AD-csatlakozó segítségével. Ez a csatlakozó az Azure Active Directory-t (Azure AD) használja a hitelesítésre és a Human Resources alkalmazáshoz való engedélyezéshez.

        ![HTTP Azure AD-csatlakozóval.](media/integration-logic-app-http-aad-connector-step.png)

    2. Jelentkezzen be a Human Resources környezetébe a HTTP-n keresztül az Azure AD-csatlakozó segítségével.
    3. Állítson be egy HTTP **POST**-kérelmet az **ExportToPackage** DMF REST API hívásához.

        - **Metódus**: POST
        - **A kérelem URL-címe:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **A kérelem törzse:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![HTTP-kérelem műveletének meghívása.](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > Előfordulhat, hogy az egyes lépéseket úgy szeretné átnevezni, hogy az az alapértelmezett nevénél érthetőbb legyen, **HTTP-kérelem meghívása**. Ezt a lépést például átnevezheti a következőre: **ExportToPackage**.

5. [Változó inicializálása](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) az **ExportToPackage** kérelem végrehajtási állapotának tárolásához.

    ![Változó művelet inicializálása.](media/integration-logic-app-initialize-variable-step.png)

6. Várjon, amíg az adatexport végrehajtási állapota **Sikeres** nem lesz.

    1. Adjon hozzá egy [Érvényesség vége-ciklus](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) műveletet, amely addig ismétlődik, amíg az **ExecutionStatus**-változó értéke **Sikeres** nem lesz.
    2. Adjon hozzá egy **Késleltetési** műveletet, amely az exportálás aktuális végrehajtási állapotához kapcsolódó lekérdezések előtt öt másodpercig várakozik.

        ![Érvényesség vége-ciklus tárolója.](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Állítsa be limitszámot **15** -ös értékre, és az exportálás befejezéséhez várjon legfeljebb 75 másodpercig (15 ismétlés x 5 másodperc). Ha az exportálás több időt vesz igénybe, szükség szerint módosítsa a limiteket.        

    3. Adjon hozzá egy **HTTP-kérelem meghívása** műveletet a [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API hívásához, majd állítsa át az **ExecutionStatus**-változót a **GetExecutionSummaryStatus** válaszának eredményére.

        > Ez a minta nem végez hibaellenőrzést. A **GetExecutionSummaryStatus** API visszaküldheti a sikertelen terminálállapotokat (azaz a **Sikeres** állapoton kívüli más állapotokat). További részletek az [API-val kapcsolatos dokumentáció](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) részben találhatók.

        - **Metódus**: POST
        - **A kérelem URL-címe:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **A kérelem törzse:** body('Invoke\_\_HTTP\_request')?[value']

            > [!NOTE]
            > Előfordulhat, hogy meg kell adnia **A kérelem törzse** értékét kódnézetben vagy a tervező funkciószerkesztőjében.

        ![Egy HTTP-kérelem meghívása 2 művelet.](media/integration-logic-app-get-execution-status-step.png)

        ![Változó művelet beállítása.](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > A **Változó beállítása** művelet értéke (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) nem fog megegyezni a **HTTP-kérelem 2 meghívása** törzsértékkel, habár a tervező ugyanolyan módon fogja mutatni az értékeket.

7. Az exportált csomag letöltési URL-jének beolvasása.

    - **HTTP-kérelem meghívása** művelet hozzáadása a [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API hívásához.

        - **Metódus**: POST
        - **A kérelem URL-címe:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **A kérelem törzse:** {"executionId": Body ("GetExportedPackageURL")?["value"]}

        ![GetExportedPackageURL-művelet.](media/integration-logic-app-get-exported-package-step.png)

8. Az exportált csomag letöltése.

    - Adjon hozzá egy HTTP **GET**-kérelmet ( beépített [HTTP-csatlakozó művelet](/azure/connectors/connectors-native-http)) az előző lépésben visszaküldött URL-címen szereplő csomag letöltéséhez.

        - **Metódus**: GET
        - **URI:** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > Előfordulhat, hogy meg kell adnia az **URI** értékét kódnézetben vagy a tervező funkciószerkesztőjében.

        ![HTTP GET-művelet.](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > A kérelemhez nem szükséges további hitelesítés, mert a **GetExportedPackageUrl** API-t visszaküldő URL-cím tartalmaz egy megosztott hozzáférési aláírási tokent, amely hozzáférést biztosít a fájl letöltéséhez.

9. Mentse a letöltött csomagot a [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness) csatlakozó segítségével.

    - Adjon hozzá egy OneDrive for Business [Fájl létrehozása](/connectors/onedriveforbusinessconnector/#create-file) műveletet.
    - Szükség szerint kapcsolódjon a OneDrive for Business fiókhoz.

        - **Mappa elérési útja:** egy Ön által kiválasztott mappa
        - **Fájlnév:** dolgozó\_csomag.zip
        - **Fájl tartalma:** az előző lépés törzse (dinamikus tartalom)

        ![Fájl létrehozása művelet.](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>3. lépés: a logikai alkalmazás tesztelése

A logikai alkalmazás teszteléséhez válassza a **Futtatás** gombot a tervezőben. Látni fogja, hogy a logikai alkalmazás futtatásának lépései megkezdődnek. 30-40 másodperccel később a logikai alkalmazásnak be kell fejeznie a futtatást, és a OneDrive for Business mappának tartalmaznia kell egy új, az exportált dolgozókat tartalmazó csomagot.

Ha bármilyen lépésnél hibát jelez, jelölje ki a sikertelen lépést a tervezőben, és vizsgálja meg a **Bemenetek** és **Kimenetek** mezőket. Hibakereséshez és a hibák javítása érdekében módosítsa a lépést.

A következő ábra bemutatja, hogy néz ki a Logic Apps Designer, amikor a logikai alkalmazás minden lépését sikeresen futtatták.

![Logikai alkalmazás sikeres futtatása.](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Összegzés

Ebben az oktatóanyagban megtanulta, hogyan kell használni a logikai alkalmazást a Human Resources adatainak exportálására, és hogyan kell menteni az exportált adatokat a OneDrive for Business mappába. Az oktatóanyag lépései az üzleti igényeknek megfelelően módosíthatók.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
