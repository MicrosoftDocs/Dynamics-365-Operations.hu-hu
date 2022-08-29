---
title: A CPOS konfigurálása egyéni alkalmazás Azure AD használatára
description: Ez a cikk bemutatja, hogyan kell konfigurálni a Felhő POS (CPOS) alkalmazást az egyéni Azure Active Directory (Azure AD) alkalmazások használatára.
author: boycez
ms.date: 08/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: baa0c3da25308345037b5dd1b4c5907d6213e7f7
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2022
ms.locfileid: "9223819"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>A CPOS konfigurálása egyéni alkalmazás Azure AD használatára

[!include [banner](includes/banner.md)]

Alapértelmezés szerint a Cloud POS (CPOS) Microsoft Dynamics 365 Commerce egy regisztrált, első fél által közzétett Microsoft-alkalmazásra (in () mutat Azure Active Directory Azure AD. Ennek megfelelően a CPOS-t anélkül is használhatja, hogy módosításokat volna szükséges volna tenni a Azure AD. Előfordulhat azonban, hogy egy ön által vezérelt egyéni alkalmazásra szeretné irányítani a Azure AD CPOS-példányt. Ez a cikk bemutatja, hogyan kell konfigurálni a CPOS-t az egyéni alkalmazások Azure AD használatára.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Egyéni Retail Server alkalmazás beállítása a következőben: Azure AD

Az alábbi lépések szerint hozhat létre és konfigurálhatja az Azure AD egyéni Retail Server alkalmazásokat.

1. Jelentkezzen be a rendszergazdai [Azure Active Directory központba](https://aad.portal.azure.com) bármely felhasználói Azure AD fiók használatával. A felhasználói fióknak nem kell rendszergazdai jogosultságokkal rendelkeznie.
1. Válassza **Azure Active Directory**.
1. Válassza **ki az alkalmazásregisztrációkat**, **majd válassza az Új regisztráció** lehetőséget az Alkalmazás **regisztrálása párbeszédpanel** megnyitásához.
1. Állítsa be a következő mezőket:

    - **Név** – adja meg az alkalmazás egyéni nevét. Például adja meg az **Egyéni kiskereskedelmi kiszolgálót**.
    - **Számlatípusok támogatása** – válassza az alapértelmezett beállítást: **Csak az ebben a szervezeti könyvtárban található számlák (csak Microsoft - Egyetlen bérlő)**.
    - **URI** átirányítása – a mező kitöltése nem kötelező. Hagyja üresen.
    - **Szolgáltatásfa azonosítója** – ez a mező nem kötelező. Hagyja üresen.
    
1. Válassza a **Regisztrálás** lehetőséget. Megjelenik az újonnan regisztrált alkalmazás konfigurációs lapja.
1. Az Áttekintés **– \> Alapszakaszon** válassza **az Alkalmazásazonosító URI hozzáadása lehetőséget,** majd válassza a Beállítás **az** alkalmazásazonosító URI **mellett lehetőséget**. Jegyezze fel a javasolt értéket, **majd** az érték elfogadásához kattintson a Mentés gombra. 
1. Válassza **a Hatókör hozzáadása lehetőséget**, majd állítsa be a következő mezőket:

    - **Hatókör neve** – adja meg a hatókör egyéni nevét. Beírhatja például a **Legacy.Access.Full et**.
    - **Hozzájáruló felhasználó** – adja meg, hogy a rendszergazdák és a felhasználók is adhatnak-e hozzájárulást a szervezet biztonsági házirendje alapján.
    - **Rendszergazdai hozzájárulás megjelenítendő neve** – adjon meg egy megjelenítendő nevet. Például adja meg az **Access Retail Server kiszolgálót**.
    - **Rendszergazdai hozzájárulás leírása** – adjon meg egy leírást. Például adja meg a Hozzáférést **a Retail Server API-khoz**.

1. Válassza a **Hatókör hozzáadása lehetőséget** a hatókör-létrehozási folyamat befejezéséhez.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Egyéni CPOS-alkalmazás beállítása a következőben: Azure AD

Az alábbi lépések szerint hozhat létre és konfigurálhatja az Azure AD egyéni CPOS-alkalmazást.

1. Jelentkezzen be a rendszergazdai [Azure Active Directory központba](https://aad.portal.azure.com) bármely felhasználói Azure AD fiók használatával. A felhasználói fióknak nem kell rendszergazdai jogosultságokkal rendelkeznie.
1. Válassza **Azure Active Directory**.
1. Válassza **ki az alkalmazásregisztrációkat**, **majd válassza az Új regisztráció** lehetőséget az Alkalmazás **regisztrálása párbeszédpanel** megnyitásához.
1. Állítsa be a következő mezőket:

    - **Név** – adja meg az alkalmazás nevét. Például adja meg az **Egyéni Felhő POS terminált**.
    - **Számlatípusok támogatása** – válassza az alapértelmezett beállítást: **Csak az ebben a szervezeti könyvtárban található számlák (csak Microsoft - Egyetlen bérlő)**.
    - **URI** átirányítása – válassza **ki az egyoldalas alkalmazást (SPA)** a legördülő listából, majd adja meg a CPOS URI-t.
    - **Szolgáltatásfa azonosítója** – ez a mező nem kötelező. Hagyja üresen.

1. Válassza a **Regisztrálás** lehetőséget. Megjelenik az újonnan regisztrált alkalmazás konfigurációs lapja.
1. Állítsa **igazra** **az oauth2AllowIdTokenImplicitFlow** **és az oauth2AllowImplicitFlow** paramétert **a** Jegyzékfájl szakaszban, **majd válassza a Mentés lehetőséget.**
1. Két jogcím **hozzáadásához** hajtsa végre a Token konfigurációs szakaszában:

    - Válassza a **Nem kötelező igény hozzáadása lehetőséget**. Állítsa azonosítóra **a Tokentípus** mezőt **·**, majd válassza ki a **tokenigényt**. Válassza a **Hozzáadás** lehetőséget.
    - Válassza a **Nem kötelező igény hozzáadása lehetőséget**. Állítsa a **Jogkivonattípus mezőt** Access **beállításra**, majd válassza ki a **tokenigényt**. Válassza a **Hozzáadás** lehetőséget.

1. **Az API-engedélyek szakaszban** válassza az Engedély **hozzáadása lehetőséget**.
1. Keresse meg **a Saját szervezet által** használt API-k lapján azt a Retail Server alkalmazást, amely az egyéni Retail Server [alkalmazás beállítása szakaszban létre van hozva Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Ezután válassza az Engedélyek **hozzáadása lehetőséget**.
1. Az Áttekintés **szakaszban** jegyezze **fel az Alkalmazás (ügyfél) azonosítója mező** értékét.

## <a name="update-the-cpos-configuration-file"></a>A CPOS konfigurációs fájl frissítése

Nyissa meg a CPOS config.json fájlt, és készítse el a következő frissítéseket.

1. **Az AADClientId** **kulcsérték cseréje arra az egyéni CPOS-alkalmazásra (ügyfél-azonosítóra),** amely az Egyéni CPOS [Azure AD](#set-up-a-custom-cpos-app-in-azure-ad) alkalmazás beállítása szakaszban létrehozott.
1. Lecserélheti **az AADRetailServerResourceId** **kulcs értékét az egyéni Retail Server** alkalmazás URI-értékére [, amely az Egyéni Kiskereskedelmi Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad) kiszolgáló alkalmazás beállítása szakaszban létrehozott.

A CPOS mindkét paramétert használja, Azure AD amikor egy biztonsági token megszerzésére vonatkozó kéréseket küld.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>A Commerce Headquarters identitásszolgáltató-beállításainak frissítése

Ezután frissítenie kell az identitás-szolgáltatók beállításait a Commerce Headquarters szolgáltatásban.

1. A Commerce Headquartersben nyissa meg **a Commerce Megosztott kereskedelmi paraméterek lapot**.
1. Az Identitás-szolgáltatók **·** **lap** Identitás-szolgáltatók szakaszában válassza ki azt a sort, amelybe be van állítva a Típus mező, **·** **Azure Active Directory** **és a Kibocsátó** mező a Azure AD bérlőre mutat. Ez a beállítás azt jelenti, hogy a bérlőnek megfelelő azonosítószolgáltatóhoz kapcsolódó adatokat tartalmazó gyermek rácsokkal fog Azure AD dolgozni.
1. A Függő **felek szakaszban** válassza a Hozzáadás **lehetőséget** sor hozzáadásához.
1. Állítsa be a következő mezőket:

    - **ClientId** – adja meg **annak az egyéni CPOS-alkalmazásnak az alkalmazás-(ügyfél-)** azonosítóját, amely az Egyéni CPOS-alkalmazás [Azure AD](#set-up-a-custom-cpos-app-in-azure-ad) beállítása szakaszban létrehozott.
    - **Típus** – a nyilvános beállítás **kiválasztása**.
    - **UserType** – a dolgozó **kiválasztása**.

1. Válassza ki a hozzáadott sort. A **Függő** **felek** szakasz alatti kiszolgálói erőforrás-erőforrásokat kezelő szakasz megjeleníti azokat a Retail Server **alkalmazás-alkalmazás-adatbázisokat, amelyek elérhetőek a Függő felek rácsban kiválasztott** alkalmazás által.
1. A Kiszolgálói **erőforrás-hozzárendelések szakaszban** válassza a Hozzáadás **lehetőséget** sor hozzáadásához.
1. A Kiszolgálói **erőforrás azonosítója** mezőben adja meg annak az egyéni Retail Server **alkalmazásnak** az alkalmazásazonosító URI-értékét [, Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad) amely az Egyéni Kiskereskedelmi kiszolgáló alkalmazás beállítása szakaszban létrehozott.

    > [!IMPORTANT]
    > Az előző lépésekben említett valamennyi mező megkülönbözteti a kis- és a nagybetűket. A megadott értékeknek pontosan meg Azure AD kell egyezniük a rendszergazdai központban beállított értékekkel.

1. Menjen a **Retail and Commerce IT \> Distribution ütemezéshez**, **és futtassa a 1110-es** (**globális** konfiguráció) feladatot.

Ezzel a saját alkalmazásával aktiválhatja a CPOS-eszközöket Azure AD.

## <a name="additional-resources"></a>További erőforrások

[Pénztári eszköz aktiválása](dev-itpro/retail-device-activation.md)

[A Retail aktiválási fiókjainak kezelése és az eszközök ellenőrzése](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
