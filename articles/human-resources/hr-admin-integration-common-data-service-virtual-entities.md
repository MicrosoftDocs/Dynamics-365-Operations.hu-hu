---
title: Common Data Service-virtuális entitások konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a virtuális entitásokat a Dynamics 365 Human Resources esetén. Meglévő virtuális entitások létrehozása és frissítése, valamint létrehozott és elérhető entitások analizálása.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0d6f79ea569a7a9b0d25e73e8666bf9ba19095d0
ms.sourcegitcommit: a8665c47696028d371cdc4671db1fd8fcf9e1088
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058154"
---
# <a name="configure-common-data-service-virtual-entities"></a>Common Data Service-virtuális entitások konfigurálása

[!include [banner](includes/preview-feature.md)]

A Dynamics 365 Human Resources egy virtuális adatforrás a következőben: Common Data Service. Teljes körű létrehozási, olvasási, frissítési és törlési (CRUD) műveletek végrehajtását teszi lehetővé a következőkből: Common Data Service és Microsoft Power Platform. A virtuális entitások adatait a Common Data Service tárolja, hanem az alkalmazás-adatbázis. 

A HR-entitásokon, Common Data Service segítségével végrehajtandó CRUD-műveletek engedélyezéséhez virtuális entitásokként elérhetővé kell tennie az entitásokat a következőben: Common Data Service. Ezáltal CRUD-műveleteket hajthat végre Common Data Service és Microsoft Power Platform segítségével a HR-ben található adatokon. A műveletek támogatják továbbá a HR teljes üzleti logikájának érvényesülését, hogy az adatok épsége biztosított legyen az adatoknak az entitásokba írásakor.

## <a name="available-virtual-entities-for-human-resources"></a>A HR számára elérhető virtuális entitások

A HR-ben található összes Open Data Protocol (OData) entitás virtuális entitásként elérhető a következőben: Common Data Service. Ezek itt is elérhetők: Power Platform. Mostantól a teljes CRUD-funkcionalitással hozhat létre alkalmazásokat és élményeket közvetlenül a HR-től származó adatokkal – mindezt anélkül, hogy az adatokat a Common Data Service-be kellene másolni vagy azzal szinkronizálni kellene. A Power Apps portálok segítségével külső webhelyeket is létrehozhat, amelyekkel együttműködési forgatókönyvek alakíthatók ki a HR-en belüli üzleti folyamatokhoz.

A [Power Apps](https://make.powerapps.com)-ben megtekintheti a környezetben engedélyezett virtuális entitások listáját, valamint elkezdheti a munkát az entitásokon a **Dynamics 365 HR Virtual Entities** megoldásban.

![Dynamics 365 HR virtuális entitások a következőben: Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a>Virtuális entitások kontra természetes entitások

A HR-hez tartozó virtuális entitások nem azonosak a HR számára létrehozott természetes Common Data Service entitásokkal. A HR-hez tartozó természetes entitásokat külön hozzák létre és kezelik a Common Data Service szolgáltatáson belüli közös humántőke-menedzsment megoldásban. A természetes entitások esetén az adatok a Common Data Service szolgáltatásban tárolódnak, és szinkronizálni kell őket a HR alkalmazás-adatbázisával.

> [!NOTE]
> A HR-hez tartozó természetes Common Data Service entitások listájához lásd a [Common Data Service entitásokat](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Beállítás

A következő lépésekkel engedélyezheti a virtuális entitások telepítését a környezetben. 

### <a name="register-the-app-in-microsoft-azure"></a>Regisztrálja az alkalmazást a Microsoft Azure-ban

Először az Azure Portal webhelyen kell regisztrálnia az alkalmazást, hogy a Microsoft Identity platform hitelesítési és engedélyezési szolgáltatásokat nyújthasson az alkalmazás és a felhasználók számára. Az alkalmazások Azure-ban való regisztrálásával kapcsolatos további tudnivalókat lásd: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Nyissa meg a [Microsoft Azure portált](https://portal.azure.com).

2. Az Azure-szolgáltatások listáján válassza ki az **Alkalmazásregisztrációk** elemet.

3. Válassza ki az **Új regisztráció** elemet.

4. A **Név** mezőbe írja be az alkalmazás ismertető nevét. Például **Dynamics 365 Human Resources Virtuális entitások**.

5. Az **Átirányítási URL-cím** mezőben adja meg a saját HR-instancia URL-névterét.

6. Válassza a **Regisztrálás** lehetőséget.

7. A regisztráció befejezését követően az Azure Portal megjeleníti az alkalmazás regisztrációjának **Áttekintés** ablaka, amelyen látható az **alkalmazás (ügyfél) azonosítója**. Ekkor jegyezze fel az **alkalmazás (ügyfél) azonosítóját**. Ezt az információt akkor kell megadnia, amikor a [virtuális entitás adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

8. A bal oldali navigációs ablakban válassza ki a **Tanúsítványok és titkos kódok** elemet.

9. Az oldal **Ügyfél titkai** részén válassza az **Új ügyféltitok** elemet.

10. Adjon meg egy leírást, válassza ki az időtartamot, majd válassza a **Hozzáadás** elemet.

11. Rögzítse a titok értékét. Ezt az információt akkor kell megadnia, amikor a [virtuális entitás adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

    > [!IMPORTANT]
    > A titok értéket ekkor feltétlenül rögzítse. A titok az oldal elhagyása után már többé nem fog megjelenni.

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a>A Dynamics 365 HR Virtual Entity alkalmazás telepítése

Telepítse a Dynamics 365 HR Virtual Entity alkalmazást a saját Power Apps környezetében, hogy a virtuális entitás megoldáscsomagot telepíthesse a Common Data Service szolgáltatáshoz.

1. Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).

2. A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.

3. Az oldal **Erőforrások** részében válassza ki a **Dynamics 365 alkalmazások** elemet.

4. Válassza ki az **Alkalmazás telepítése** műveletet.

5. Válassza ki a **Dynamics 365 HR Virtual Entity** elemet, majd pedig a **Tovább** elemet.

6. Olvassa át, majd pedig kijelöléssel jelezze, hogy elfogadja-e a szolgáltatási feltételeket.

7. Válassza a **Telepítés** parancsot.

A telepítés néhány percet igényel. Befejezéskor folytassa a következő lépésekkel.

![A Dynamics 365 HR Virtual Entity alkalmazás telepítése a Power Platform felügyeleti központból](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a>A virtuális entitás adatforrásának konfigurálása 

A következő lépésben a virtuális entitás adatforrásának a Power Apps környezetben történő konfigurálása történik. 

1. Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).

2. A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.

3. Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.

4. A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az alkalmazásoldal jobb felső sarkában található **Összetett keresés** ikont.

5. Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki a **Finance and Operations virtuális adatforrás konfigurációi** elemet.

6. Válassza az **Eredmények** lehetőséget.

7. Válassza ki a **Microsoft HR-adatforrás** rekordot.

8. Adja meg az adatforrás-konfigurációhoz szükséges adatokat.

   - **Cél URL** : A saját HR-névtér URL-je.
   - **Bérlő azonosítója** : az Azure Active Directory (Azure AD) bérlő azonosítója.
   - **AAD-alkalmazásazonosító** : Az Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott alkalmazásazonosító (ügyfél-azonosító). Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.
   - **AAD-alkalmazástitok** : A Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott ügyféltitok. Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.

9. Válassza ki a **Mentés és bezárás** lehetőséget.

   ![Microsoft HR-adatforrás](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a>Alkalmazásengedélyek kiosztása a HR-ben

Engedélyek kiosztása a HR-ben lévő két Azure AD-alkalmazáshoz:

- A Microsoft Azure portálon a bérlője számára létrehozott alkalmazás
- A Dynamics 365 HR Virtual Entity alkalmazás a Power Apps környezetben telepítve 

1. A HR-modulban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.

2. Válassza ki az **Új** lehetőséget egy új alkalmazásrekord létrehozásához:

    - Az **Ügyfél-azonosító** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás ügyfél-azonosítóját.
    - A **Név** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás nevét.
    - A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.

3. Válassza ki az **Új** lehetőséget egy második alkalmazásrekord létrehozásához:

    - **Ügyfél-azonosító** : f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Név** : Dynamics 365 HR Virtual Entity
    - A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.

## <a name="generate-virtual-entities"></a>Virtuális entitások létrehozása

A telepítés befejezését követően kiválaszthatja, hogy mely virtuális entitásokat szeretné létrehozni és engedélyezni a saját Common Data Service-példányában.

1. A HR-modulban nyissa meg a **Common Data Service (CDS) integrációja** oldalt.

2. Válassza ki a **Virtuális entitások** lapot.

> [!NOTE]
> A **Virtuális entitások engedélyezése** váltógombot a rendszer automatikusan az **Igen** értékre állítja, ha befejezte a szükséges beállításokat. Ha a váltógomb értéke **Nem** , tekintse át a dokumentum előző szakaszaiban ismertetett lépéseket, és győződjön meg arról, hogy minden előfeltétel-beállítást befejezett.

3. Válassza ki a Common Data Service szolgáltatásban létrehozni kívánt entitást vagy entitásokat.

4. Válassza a **Létrehozás/frissítés** lehetőséget.

![Common Data Service-integráció](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a>Entitásgenerálási állapot ellenőrzése

A virtuális entitások a Common Data Service szolgáltatásban aszinkron háttérfolyamatok során jönnek létre. A folyamat frissítései a műveleti központban láthatók. A folyamatra vonatkozó részletek, többek között a hibanaplók, a **Folyamatok automatizálása** oldalon láthatók.

1. Az Emberi Erőforrások modulban nyissa meg **Folyamatok automatizálása** lapot.

2. Válassza ki a **Háttérfolyamatok** lapot.

3. Válassza ki a **Virtuális entitás lekérdezése – aszinkron háttérfolyamat** lehetőséget.

4. Válassza ki a **Legutóbbi eredmények megtekintése** lehetőséget.

A kicsúszó ablaktábla megjeleníti a folyamat legutóbbi végrehajtásának eredményeit. Megtekintheti a folyamat naplóját, többek között a Common Data Service szolgáltatásból visszaküldött hibákat is.

## <a name="see-also"></a>Lásd még

[Mi az a Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Entitások áttekintése](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Entitáskapcsolatok áttekintése](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Külső adatforrásból származó adatokat tartalmazó virtuális entitások létrehozása és szerkesztése](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Mik azok a Power Apps portálok?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Alkalmazások Power Apps-ben való létrehozásának áttekintése](https://docs.microsoft.com/powerapps/maker/)
