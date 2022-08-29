---
title: Alapadat-keresés engedélyezése adószámítási konfigurációhoz
description: Ez a cikk bemutatja, hogy hogyan lehet beállítani és engedélyezni az adószámítási alapadat-keresési funkciót.
author: kai-cloud
ms.date: 07/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f9d882340171173e5e503f8b5e3aa856e8544b0
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306203"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Alapadat-keresés engedélyezése adószámítási konfigurációhoz 

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet beállítani és engedélyezni az adószámítási alapadat-keresési funkciót. Az adószámítási konfigurációban a jogi személy, **·** **·** **a szállítókód, a cikk-kód és a szállítási időszak mezőiben legördülő lista használható értékek kiválasztására.** **·** Ezek az értékek a 365-ös Microsoft Dynamics pénzügyi környezetből, az adatforrás Microsoft Dataverse használatával jönnek.

> [!NOTE] 
> Az adószámítási alapadat-keresési funkció nem kötelező funkció. A következő lépéseket kihagyhatja, **ha letiltja az adószolgáltatás Dataverse** adatforrás-támogatási szolgáltatását az RCS (Regulatory Configuration Service) szolgáltatásban. Ebben az esetben azonban az adószámítási konfigurációban nem lesz elérhető a legördülő lista.

Ha engedélyezni szeretné a legördülő listát az Adószámítás funkcióverzió-konfigurációjában, kövesse az alábbi lépéseket.

1. [Integráció Microsoft Power Platform engedélyezése és a környezet Dataverse megnyitása.](#enable)
2. [A pénzügyek és a műveletek virtuális entitások telepítése.](#install)
3. [Azure Active Directory Pályázat regisztrálása Azure AD.](#register)
4. [Adja meg az alkalmazás engedélyeit a Pénzügyi és üzemeltetési alkalmazásokban.](#grant)
5. [A virtuális entitás adatforrásának konfigurálása](#configure)
6. [Virtuális Dataverse entitások engedélyezése](#virtual)
7. [A kapcsolódó adószámítási alkalmazás beállítása.](#set-up)
8. [A modellleképezés konfigurációjának Dataverse importálása és beállítása.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a> Integráció Microsoft Power Platform engedélyezése és a környezet Dataverse megnyitása

Ha a Microsoft Power Platform Lifecycle Services (LCS) szolgáltatásban új pénzügyi és műveleti alkalmazásokat hoz létre, engedélyezni lehet a Microsoft Dynamics pénzügyi és műveleti alkalmazások integrációját. További informáciért lásd: [Microsoft Power Platform integráció – Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Ha végzett, egy környezet neve megjelenik az Microsoft Power Platform **Power Platform Integráció szakaszban**.

1. Az LCS-kben, a pénzügyi és műveleti környezetben **Power Platform**, az Integráció szakaszban keresse meg és jegyezze fel a **kapcsolódó** környezet környezeti névértékét.

    [![A környezet neve.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. A Környezetek [Power Platform lapon](https://admin.powerplatform.microsoft.com/environments)**válassza** ki azt a környezetet, **amely** megfelel annak a környezetnévnek, amelyről megjegyzést készített.
3. A Részletek **lapon** keresse meg a **környezet URL-címét** Dataverse. Jegyezze fel ezt az értéket, mert a [7. lépésben szüksége lesz rá. A kapcsolódó adószámítási alkalmazás beállítása](#set-up).
4. Győződjön meg róla, hogy a Dataverse környezetet meg tudja nyitni a böngészőben **a Környezet URL-cím értékének kiválasztásával**.

    [![Dataverse környezeti oldal.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > A környezet Dataverse nyitva tartás a böngészőben. Az 5. lépésben [szükség lesz rá. A virtuális entitás adatforrásának konfigurálása](#configure)

További információ az integráció [engedélyezése.Microsoft Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md)

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a> A pénzügyek és a műveletek virtuális entitások telepítése

A Dataverse pénzügyi és műveleti virtuális entitások megoldását virtuális entitások megoldását virtuális entitás megoldásból Microsoft AppSource kell telepíteni.

1. Megkeresi AppSource a [Pénzügy és műveletek virtuális entitást.](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity)
2. Válassza a **Most kap lehetőséget**.
3. A Környezet **kiválasztása mezőben** adja **meg** a Környezet neve értéket, amelyről korábban megjegyzést készített.
4. Jelölje be a jelölőnégyzeteket, majd válassza a Telepítés **lehetőséget**.

A telepítés befejeztével **megkeresheti**[Power Platform](https://admin.powerplatform.microsoft.com/) a Pénzügy és műveletek virtuális entitás alkalmazást a rendszergazdai központban, **az Erőforrások** \> **Dynamics 365-alkalmazások alatt.**

A további tudnivalókat lásd [a Virtuális entitás megoldásának beszerzése.](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution)

## <a name="register-an-azure-ad-application"></a><a name='register'></a> Pályázat regisztrálása Azure AD

A pályázatot ugyanazon a Azure AD bérlőn kell regisztrálnia, mint a pénzügyi és az üzemeltetési alkalmazásokat, hogy hívhatja őket Dataverse.

1. Az Azure-portálon menjen az [alkalmazásregisztrációkhoz](https://portal.azure.com)**Azure Active Directory.\>**
2. Válassza az **Új regisztráció** lehetőséget, és adja meg a következő adatokat:

    - **Név** – adjon meg egy egyedi nevet.
    - **Számlatípus** – adja meg bármelyik **könyvtárat Azure AD** (egy-bérlő vagy többbéres).
    - **URI átirányítása** – hagyja üresen ezt a mezőt.

3. Válassza a **Regisztrálás** lehetőséget.
4. Jegyezze fel az **Alkalmazás (ügyfél) azonosító** értékét, mert később szüksége lesz rá.

    [![Azure AD Alkalmazásazonosító (ügyfél)](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Szimmetrikus kulcs létrehozása az alkalmazáshoz.
6. Az új pályázatban válassza ki a **Tanúsítványok & jelölőnégyzetet**.
7. Válassza ki az **Új titkos ügyfélkód** lehetőséget.
8. Adjon meg egy leírást, válasszon egy lejárati dátumot, majd válassza a Mentés **lehetőséget**. Létrejön és megjelenik egy kulcs. Az érték másolása későbbi használatra.

További információ a Pályázat regisztrálása [oldalon Azure AD található](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a> Alkalmazásengedélyek megadása a Pénzügyi és üzemeltetési alkalmazásokban

Dataverse A Azure AD aki a létrehozott alkalmazást használja a pénzügyi és műveleti alkalmazások hívásához. Ebből következően az alkalmazást a pénzügyi és műveleti alkalmazásoknak kell megbízhatónak lennie, és olyan felhasználói fiókhoz kell társítva lennie, amely rendelkezik a megfelelő jogokkal. A pénzügyek és műveletek alkalmazásokban létre kell hoznia egy olyan speciális szolgáltatási felhasználót, aki **csak** a Azure AD virtuális entitás funkcióihoz rendelkezik jogokkal. Ennek a szolgáltatásfelhasználónak nem lehet más jogosultsága. A lépés befejezése után minden alkalmazás, amely a létrehozott alkalmazás titkos titka, hívni tudja a pénzügyi és műveleti alkalmazások környezetét, Azure AD és hozzáférhet a virtuális entitás funkcióihoz.

1. Környezetében menjen a **Rendszerfelügyeleti** \> **felhasználók felhasználóihoz.** \> **·**
2. Új **felhasználó hozzáadásához** válassza az Új lehetőséget, és adja meg a következő adatokat:

    - **Felhasználói azonosító** – a **dataverseintegration vagy** egy másik érték beírása.
    - **Felhasználónév** – adatsértő **integráció vagy** más érték beírása.
    - **Szolgáltató** – a mező nem AAD **beállítását adja meg**.
    - **E-mail** – dataverseintegration **vagy** más érték beírása. (Az értéknek nem kell érvényes e-mail fióknak lennie.)

3. Rendelje hozzá **Dataverse a felhasználóhoz a virtuális entitásintegrációs** alkalmazás biztonsági szerepkörét.
4. Az összes többi szerepkör, többek között a Rendszerfelhasználó **eltávolítása**
5. A regisztráláshoz **menjen a Rendszerfelügyeletet** \> **telepítő** \> **Azure Active Directory** alkalmazásokhoz.Dataverse 
6. Adjon meg egy sort, **majd** az Ügyfél azonosítója mezőben adja **meg azt az alkalmazásazonosítót (** ügyfélazonosítót), amelyről korábban megjegyzést készített.
7. A **Név** mezőben adjon meg egy nevet. Beírhatja például az integrációt **Dataverse**.
8. A Felhasználói **azonosító mezőbe** írja be a korábban létrehozott felhasználói azonosítót.

A további tudnivalókat lásd [a Grant alkalmazásengedélyek a Pénzügy és műveletek alkalmazásokban](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>A virtuális entitás adatforrásának konfigurálása

A csatlakozáshoz meg kell Dataverse adnia a Pénzügyi és műveletek alkalmazáspéldányt.

1. A Dataverse környezetnek ettől még az 1. lépéstől [meg kell nyitva lennie a böngészőben. Integráció Microsoft Power Platform engedélyezése és a környezet Dataverse megnyitása](#enable). Válassza a beállítások gombot (fogaskerekek szimbóluma) a jobb felső részén, majd válassza a Speciális **beállítások lehetőséget**.

    [![Speciális beállítások megnyitása a környezetben Dataverse .](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. Válassza a **Beállítások** legördülő menü Adminisztráció **parancsát**.

    [![Adminisztráció.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Virtuális **entitás adatforrásának kiválasztása**.

    [![Virtuális entitás adatforrása.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Válassza ki a Pénzügy és **műveletek nevű adatforrást**.

    [![A Pénzügy és műveletek adatforrása.](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Adja meg a korábbi lépések következő adatait:

    - **Cél URL-címe** – adja meg azt az URL-címet, ahol hozzáférhet a pénzügyi és műveleti alkalmazásokhoz.
    - **OAuth URL-cím** – adja meg `https://login.windows.net/`.
    - **Bérlő azonosítója** – a bérlő megadása. Ez az érték lehet a vállalati e-mail tartományneve (például contoso.com).
    - **AAD-alkalmazásazonosító** – adja meg **a korábban létrehozott alkalmazásazonosító (ügyfél)** értékét.
    - **AAD application secret** – adja meg a korábban létrehozott titkos adatokat.
    - **AAD erőforrás** – adja meg **00000015-0000-0000-c000-000000000000**. Ez az érték a Azure AD pénzügyi és a műveletalkalmazásokat képviselő alkalmazás. Mindig ugyanannak az értéknek kell lennie.

6. Mentse el a módosításokat.
7. Az Adminisztráció lapra való **visszatéréshez** zárja be a lapot, ahol elkezdi [a 6. lépést. Virtuális Dataverse entitások engedélyezése](#virtual)

    [![Az entitás bezárása szerkesztésre](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

További tájékoztatás: [A virtuális entitás adatforrásának konfigurálása](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a> Virtuális Dataverse entitások engedélyezése

Az adószámítási **konfiguráció** csak akkor tudja igénybe venni őket, ha a pénzügyi és a műveletalkalmazások virtuális entitásai láthatóak.

> [!NOTE]
> Ezt a lépést kihagyhatja, [ha csak egy kattintással engedélyezi az Adószámítással kapcsolatos virtuális entitásokat a 8. lépésben. A kapcsolódó adószámítási alkalmazás beállítása](#import). Ugyanakkor javasoljuk, hogy manuálisan engedélyezzen legalább egy virtuális entitást annak jelzésére, hogy kapcsolat van-e a pénzügyi és a műveletalkalmazások között, Dataverse és az adott környezet már be van létre van hozva.

1. Környezetében Dataverse az Adminisztráció **lapon** válassza ki a szűrőgombot (tölcsér szimbólumát) a jobb felső sarokban.

    [![Szűrőgomb](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. A Speciális **keresés ablak** **Keresés** mezőjében válassza az **Elérhető pénzügyi és műveletentitások lehetőséget.**
3. Adja hozzá a következő szabályt: **Név** – **Tartalmazza** – **CompanyInfoEntity**. Ezután válassza az **eredményeket**.

    [![Speciális keresés ablak](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. Válassza a **CompanyInfoEntity** lehetőséget a keresési eredmények között, jelölje be **a Látható** jelölőnégyzetet, majd kattintson a Mentés **gombra**.

    [![Az entitás láthatóságának beállítása](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Ismételje meg az előző lépéseket az adószámítás konfigurációjában hivatkozott következő entitásokkal:

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCodeEntity
    - InventWarehouseEntity

    > [!NOTE]
    > Csak az entitás első 5000 Dataverse rekordját lehet beolvasni, és elérhetővé tenni az adószámítási konfiguráció legördülő listájában.

További tudnivalókért lásd: [A Microsoft Dataverse Virtuális entitások engedélyezése](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a> A kapcsolódó adószámítási alkalmazás beállítása

1. Menjen az **Elektronikus jelentéskészítés** pontra, **majd a Kapcsolódó hivatkozások szakaszban** válassza **a Kapcsolódó alkalmazások lehetőséget**.

    [![Kapcsolódó alkalmazások](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

2. Rekord **hozzáadásához válassza az Új** lehetőséget, és adja meg a következő adatokat.

    - **Név** – írjon be egy nevet.
    - **Típus** – válassza a lehetőséget **Dataverse**.
    - **Alkalmazás** – adja meg a Dataverse **környezete URL-címét**, amelyet az [1. lépésben jegyeztek fel. Integráció Microsoft Power Platform engedélyezése és a környezet Dataverse megnyitása](#enable).
    - **Bérlő** – adja meg a bérlőt.
    - **Egyéni URL-cím** – adja meg az Dataverse URL-címet, és fűzi **hozzá az /API/data/v9.1 adatokat**.

3. Válassza **a Kapcsolat ellenőrzése** lehetőséget, majd a párbeszédpanelen kattintson **ide a kiválasztott távoli alkalmazáshoz való csatlakozáshoz**.

    [![A kapcsolat ellenőrzése](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
4. Győződjön meg róla, hogy a "Sikeres" üzenetet kapja. üzenet, amely a kapcsolat sikeres létrejöttét jelzi.

    [![Sikeres üzenet.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)
    
5. Az RCS szolgáltatásban nyissa meg **a Szolgáltatáskezelés** munkaterületet, és engedélyezze a következő funkciókat:

    - Globalizációs funkciók
    - Elektronikus jelentés Dataverse-adatforrások támogatása
    - Adószolgáltatás Dataverse-adatforrásainak támogatása

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a> A modellleképezés konfigurációjának importálása Dataverse és beállítása

A Microsoft alapértelmezett modell-hozzárendelési konfigurációkat biztosít a pénzügyi és műveletalkalmazások és az adószámítási alkalmazások entitásai számára.

1. Az RCS rendszerekben menjen az Elektronikus **jelentéskészítéshez**.
2. A Konfiguráció-szolgáltatók **szakasz** **Microsoft-szolgáltató** csempeén válassza ki a **tárházakat**.

    [![Tárolók.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Válassza ki **a globális konfiguráció tárházrekordját**, majd a Megnyitás **lehetőséget**.
4. Az Adóadatok **modell adószámítása** \> **adatmodellben** válassza ki a modellleképezés **Dataverse konfigurációját.**
5. A Verziók **gyorsban** válassza ki azt a verziót, amely megfelel a pénzügyi és műveletalkalmazások verziójának, **majd válassza az Importálás lehetőséget**.

    [![A modellleképezés Dataverse konfigurációjának importálása](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > A **Dataverse modellleképezés** konfigurációja csak a legmagasabb importált verzión van hatályos. Ezért nem importálhatja olyan **Dataverse** modellleképezés-konfigurációt, amely magasabb, mint a megvalósítandó adószámítási konfiguráció verziója. Ha például az adószámítás 40.50.225 verzióját tervezi implementálja, akkor csak a modellleképezés konfigurációjának 40.50.13-as **Dataverse verzióját importálja**. Nem importálhatja a 40.54.14-es verziót. Ellenkező esetben az adatmodellek nem egyezőek a konfigurációban.

6. Menjen vissza az Elektronikus **jelentéskészítés** lapra, és válassza az **Adókonfigurációk csempe** lehetőséget.
7. Válassza ki az importált modellleképezés **Dataverse** konfigurációját, majd válassza a Szerkesztés **lehetőséget**.
8. Állítsa az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre.
9. A **Csatlakoztatott alkalmazás mezőben** válassza ki [a 7. lépésben beállított csatlakoztatott alkalmazást. A kapcsolódó adószámítási alkalmazás beállítása](#set-up).
10. A Virtuális tábla **láthatóságának** **beállítása** Igen beállítással az összes adószámítással kapcsolatos virtuális entitást láthatóra állíthatja.

Most már befejezte az alapadat-keresési funkció beállításait. Az adószámítási funkció verziójában engedélyezni kell az olyan mezők legördülő listáját, mint például a jogi személy, **a** szállítókód, **·** **a** cikkkód és a szállítási feltételek a Dynamics 365 Pénzügy **eszközben**.**·**

[![Jogi személy legördülő listája.](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
