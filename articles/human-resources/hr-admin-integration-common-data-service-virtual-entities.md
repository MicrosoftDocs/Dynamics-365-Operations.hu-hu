---
title: A Dataverse virtuális tábláinak konfigurálása
description: Ez a témakör bemutatja, hogyan kell konfigurálni, létrehozni, frissíteni a meglévő virtuális táblákat, valamint elemezni a generált és a rendelkezésre álló táblákat a Dynamics 365 Human Resources számára.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9e26a2fb65564cb4a1d2f9ba4b0d621177207545
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414664"
---
# <a name="configure-dataverse-virtual-tables"></a>A Dataverse virtuális tábláinak konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A Dynamics 365 Human Resources egy virtuális adatforrás a következőben: Microsoft Dataverse. Teljes körű létrehozási, olvasási, frissítési és törlési (CRUD) műveletek végrehajtását teszi lehetővé a következőkből: Dataverse és Microsoft Power Platform. A virtuális táblák adatait a Dataverse tárolja, hanem az alkalmazás-adatbázis.

A HR-entitásokon, Dataverse segítségével végrehajtandó CRUD-műveletek engedélyezéséhez virtuális táblákként elérhetővé kell tennie az entitásokat a következőben: Dataverse. Ezáltal CRUD-műveleteket hajthat végre Dataverse és Microsoft Power Platform segítségével a HR-ben található adatokon. A műveletek támogatják továbbá a HR teljes üzleti logikájának érvényesülését, hogy az adatok épsége biztosított legyen az adatoknak az entitásokba írásakor.

> [!NOTE]
> A Human Resources entitások Dataverse-tábláknak felelnek meg. A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>A Human Resources számára elérhető virtuális táblák

A HR-ben található összes Open Data Protocol (OData) entitások virtuális táblákként elérhetők a Dataverse rendszerben. Ezek itt is elérhetők: Power Platform. Mostantól a teljes CRUD-funkcionalitással hozhat létre alkalmazásokat és élményeket közvetlenül a HR-től származó adatokkal – mindezt anélkül, hogy az adatokat a Dataverse-be kellene másolni vagy azzal szinkronizálni kellene. A Power Apps portálok segítségével külső webhelyeket is létrehozhat, amelyekkel együttműködési forgatókönyvek alakíthatók ki a HR-en belüli üzleti folyamatokhoz.

A [Power Apps](https://make.powerapps.com)-ben megtekintheti a környezetben engedélyezett virtuális táblák listáját, valamint elkezdheti a munkát az táblákon a **Dynamics 365 HR Virtual Tables** megoldásban.

![Dynamics 365 HR Virtual Tables a Power Apps rendszerben.](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Virtuális táblák és natív táblák

A HR-hez tartozó virtuális táblák nem azonosak a HR számára létrehozott natív Dataverse-táblákkal. 

A HR-hez tartozó natív táblákat külön hozzák létre és kezelik a Dataverse szolgáltatáson belüli közös humántőke-menedzsment megoldásban. A natív táblák esetén az adatok tárolása a Dataverse szolgáltatásban történik, és szinkronizálni kell őket a HR alkalmazás-adatbázisával.

> [!NOTE]
> A HR-hez tartozó natív Dataverse-táblák listájához lásd: [Dataverse-táblák](./hr-developer-entities.md).

## <a name="setup"></a>Beállítás

A következő lépésekkel engedélyezheti a virtuális táblák telepítését a környezetben.

### <a name="enable-virtual-tables-in-human-resources"></a>Virtuális táblák engedélyezése a Human Resources alkalmazásban

Először engedélyeznie kell a virtuális táblákat a **Szolgáltatáskezelés** munkaterületen.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. Válassza ki a **Funkció kezelése** csempét.

3. Válassza a **Virtuális táblák támogatása a HR számára a Dataverse rendszerben** elemet, majd az **Engedélyezés** lehetőséget.

A funkciók aktiválásával és letiltásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.

### <a name="register-the-app-in-microsoft-azure"></a>Regisztrálja az alkalmazást a Microsoft Azure-ban

Először az Azure Portal webhelyen kell regisztrálnia a Human Resources példányt, hogy a Microsoft identitásplatform hitelesítési és engedélyezési szolgáltatásokat nyújthasson az alkalmazás és a felhasználók számára. Az alkalmazások Azure-ban való regisztrálásával kapcsolatos további tudnivalókat lásd: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](/azure/active-directory/develop/quickstart-register-app).

1. Nyissa meg a [Microsoft Azure portált](https://portal.azure.com).

2. Az Azure-szolgáltatások listáján válassza ki az **Alkalmazásregisztrációk** elemet.

3. Válassza ki az **Új regisztráció** elemet.

4. A **Név** mezőbe írja be az alkalmazás ismertető nevét. Például **Dynamics 365 Human Resources Virtuális táblák**.

5. Az **Átirányítási URL-cím** mezőben adja meg a saját HR-instancia URL-névterét.

6. Válassza a **Regisztrálás** lehetőséget.

7. A regisztráció befejezését követően az Azure Portal megjeleníti az alkalmazás regisztrációjának **Áttekintés** ablaka, amelyen látható az **alkalmazás (ügyfél) azonosítója**. Ekkor jegyezze fel az **alkalmazás (ügyfél) azonosítóját**. Ezt az információt akkor kell megadnia, amikor a [virtuális tábla adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. A bal oldali navigációs ablakban válassza ki a **Tanúsítványok és titkos kódok** elemet.

9. Az oldal **Ügyfél titkai** részén válassza az **Új ügyféltitok** elemet.

10. Adjon meg egy leírást, válassza ki az időtartamot, majd válassza a **Hozzáadás** elemet.

11. A titkos érték rekordja a tábla **Érték** tulajdonságából. Ezt az információt akkor kell megadnia, amikor a [virtuális tábla adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > A titok értéket ekkor feltétlenül rögzítse. A titok az oldal elhagyása után már többé nem fog megjelenni.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>A Dynamics 365 HR Virtual Table alkalmazás telepítése

Telepítse a Dynamics 365 HR Virtual Table alkalmazást a saját Power Apps környezetében, hogy a virtuális tábla megoldáscsomagot telepíthesse a Dataverse szolgáltatáshoz.

1. A HR-modulban nyissa meg a **Microsoft Dataverse integrációja** oldalt.

2. Válassza ki a **Virtuális táblák** lapot.

3. Válassza a **Virtuális táblaalkalmazás telepítése** lehetőséget.

### <a name="configure-the-virtual-table-data-source"></a>A virtuális tábla adatforrásának konfigurálása

A következő lépésben a virtuális tábla adatforrásának a Power Apps környezetben történő konfigurálása történik.

1. Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).

2. A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.

3. Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.

4. A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az alkalmazásoldal jobb felső sarkában található **Összetett keresés** ikont.

5. Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki a **Finance and Operations virtuális adatforrás konfigurációi** elemet.

   > [!NOTE]
   > Az előző beállítási lépés virtuális tábla alkalmazás telepítése néhány percig is eltarthat. Ha a **Finance and Operations virtuális adatforrás konfigurációi** nem érhetők el a listában, várjon egy percet, és frissítse a listát.

6. Válassza az **Eredmények** lehetőséget.

7. Válassza ki a **Microsoft HR-adatforrás** rekordot.

8. Adja meg az adatforrás-konfigurációhoz szükséges adatokat:

   - **Cél URL**: A saját HR-névtér URL-je. A cél URL formátuma:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Példa:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Ügyeljen arra, hogy az URL-cím végén a „**/**” karakter is szerepeljen a hibák elkerülése érdekében.

     >[!NOTE]
     >A Cél URL határozza meg azt a humánerőforrás-környezetet, amelyre a virtuális táblák az adatokért mutatnak. Ha tesztkörnyezetet hoz létre a termelési környezet másolatának létrehozásával, frissítse ezt az értéket az új tesztkörnyezet névtér-URL-ére. Ez biztosítja, hogy a virtuális táblák a tesztkörnyezet adataihoz kapcsolódnak, és nem továbbra is a termelési környezetre mutatnak.

   - **Bérlő azonosítója**: az Azure Active Directory (Azure AD) bérlő azonosítója.

   - **AAD-alkalmazásazonosító**: Az Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott alkalmazásazonosító (ügyfél-azonosító). Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.

   - **AAD-alkalmazástitok**: A Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott ügyféltitok. Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.

   ![Microsoft HR-adatforrás.](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Válassza ki a **Mentés és bezárás** lehetőséget.

### <a name="grant-app-permissions-in-human-resources"></a>Alkalmazásengedélyek kiosztása a HR-ben

Engedélyek kiosztása a HR-ben lévő két Azure AD-alkalmazáshoz:

- A Microsoft Azure portálon a bérlője számára létrehozott alkalmazás
- A Dynamics 365 HR Virtual Table alkalmazás a Power Apps környezetben telepítve 

1. A HR-modulban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.

2. Válassza ki az **Új** lehetőséget egy új alkalmazásrekord létrehozásához:

    - Az **Ügyfél-azonosító** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás ügyfél-azonosítóját.
    - A **Név** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás nevét.
    - A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.

3. Válassza ki az **Új** lehetőséget egy második alkalmazásrekord létrehozásához:

    - **Ügyfél-azonosító**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Név**: Dynamics 365 HR Virtual Table
    - A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.

## <a name="generate-virtual-tables"></a>Virtuális táblák létrehozása

A telepítés befejezését követően kiválaszthatja, hogy mely virtuális táblákat szeretné létrehozni és engedélyezni a saját Dataverse-példányában.

1. A HR-modulban nyissa meg a **Microsoft Dataverse integrációja** oldalt.

2. Válassza ki a **Virtuális táblák** lapot.

> [!NOTE]
> A **Virtuális táblák engedélyezése** váltógombot a rendszer automatikusan az **Igen** értékre állítja, ha befejezte a szükséges beállításokat. Ha a váltógomb értéke **Nem**, tekintse át a dokumentum előző szakaszaiban ismertetett lépéseket, és győződjön meg arról, hogy minden előfeltétel-beállítást befejezett.

3. Válassza ki a Dataverse szolgáltatásban létrehozni kívánt táblát vagy táblákat.

4. Válassza a **Létrehozás/frissítés** lehetőséget.

![Dataverse-integráció.](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Táblagenerálási állapot ellenőrzése

A virtuális táblák a Dataverse szolgáltatásban aszinkron háttérfolyamatok során jönnek létre. A folyamat frissítései a műveleti központban láthatók. A folyamatra vonatkozó részletek, többek között a hibanaplók, a **Folyamatok automatizálása** oldalon láthatók.

1. Az Emberi Erőforrások modulban nyissa meg **Folyamatok automatizálása** lapot.

2. Válassza ki a **Háttérfolyamatok** lapot.

3. Válassza ki a **Virtuális tábla lekérdezése – aszinkron háttérfolyamat** lehetőséget.

4. Válassza ki a **Legutóbbi eredmények megtekintése** lehetőséget.

A kicsúszó ablaktábla megjeleníti a folyamat legutóbbi végrehajtásának eredményeit. Megtekintheti a folyamat naplóját, többek között a Dataverse szolgáltatásból visszaküldött hibákat is.

## <a name="see-also"></a>Lásd még

[Mi az a Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Táblák a Dataverse-rendszerben](/powerapps/maker/common-data-service/entity-overview)<br>
[Táblakapcsolatok áttekintése](/powerapps/maker/common-data-service/relationships-overview)<br>
[Külső adatforrásból származó adatokat tartalmazó virtuális táblák létrehozása és szerkesztése](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Mik azok a Power Apps portálok?](/powerapps/maker/portals/overview)<br>
[Alkalmazások Power Apps-ben való létrehozásának áttekintése](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
