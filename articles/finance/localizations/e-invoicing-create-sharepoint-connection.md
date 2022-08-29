---
title: SharePoint kapcsolat konfigurálása
description: Ez a cikk bemutatja a kapcsolatot úgy, hogy az elektronikus számlázás hozzáfér a Microsoft-webhelyhez SharePoint.
author: gionoder
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: a2762178686d1f29c457b6de2a9b052fd048484b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283987"
---
# <a name="configure-a-sharepoint-connection"></a>SharePoint kapcsolat konfigurálása

[!include [banner](../includes/banner.md)]

Az Elektronikus számlázás szolgáltatás fájlokat olvas a Microsoft SharePoint mappáiból, és fájlokat tölthet fel a következőbe:SharePoint Annak érdekében, hogy az elektronikus számlázások hozzáférnek egy adott helyhez, meg kell adnia a SharePoint webhely hitelesítő adatait az Elektronikus számlázási szolgáltatás számára. Ezenkívül a hitelesítő adatok biztonságos tárolása érdekében ne közvetlenül adja meg őket. Ehelyett egy Azure-kulcs kulcstárolóban tárolja őket, és adjon meg egy Azure-kulcsú titkos Azure-kulcsot.

## <a name="grant-access-to-a-sharepoint-folder"></a>Hozzáférés megadása mappához SharePoint

1. Alkalmazásregisztráció létrehozása a bérlőben, ahol az RCS (Regulatory Configuration Service) szolgáltatás telepítve van.

    1. Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
    2. Ugrás az **alkalmazásregisztrációkhoz**
    3. Válassza ki az **Új regisztráció** elemet.
    4. Írjon be egy nevet, például **SharePoint elektronikus számlázásra vonatkozó alkalmazást**, és töltse ki a regisztrációt.
    5. Az új alkalmazásregisztráció kiválasztása.
    6. A Hitelesítés **lapon** engedélyezze a Nyilvános **ügyfélfolyamatok engedélyezése beállítást**.
    4. A Tanúsítványok **& lapon** válassza ki **az Új** ügyfél titkos gombra az ügyféltitk létrehozásához.
    5. A létrehozott titkos titkos fájl értékének másolása.

    Kövesse az alábbi irányelveket:

    - Ne ugyanazt az alkalmazásregisztrációt használja különböző szolgáltatásokhoz.
    - Kövesse a jelszóra [vonatkozó irányelveket](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - A jelszavak átváltásának beállítása. A átváltás során hozzon létre új ügyféltitkot az alkalmazásregisztráció számára, frissítse a kulcsot, majd törölje a régi titkos kulcsot.

2. Az alkalmazásregisztrációs **titkosság** **és az alkalmazásazonosító (ügyfél)** azonosítójának mentése két új bejegyzésként az elektronikus számlázási környezet beállításában.
3. Adja hozzá a kulcsot, amit az RCS elektronikus számlázási környezetének beállításainál hozott létre a Key Paraméterei paraméterekkel.
4. Az Azure-portálon adjon hozzáférést a következőnek SharePoint: Ezt a lépést a bérlő rendszergazdájának kell végrehajtania.

    1. Válassza ki a létrehozott alkalmazásregisztrációt.
    2. **Az API-engedélyek lapon** válassza az Engedély **hozzáadása lehetőséget**.
    3. Válassza ki **a Microsoft graph (alkalmazásengedélyek) webhelyeit.Kiválasztva** \> **·**.
    4. Válassza ki a **Támogatás rendszergazdai hozzájárulásának megadását ehhez \<user&nbsp;name\>**.
    5. Ellenőrizze az **Állapot** mezőben, hogy az engedélyek meg vannak-e adni.

        ![Az API-engedélyek lapon megadott engedélyek.](media/configured-permissions.jpg)

    6. Nyissa meg [a Graph Explorer - Microsoft Graph alkalmazást](https://developer.microsoft.com/graph/graph-explorer), és jelentkezzen be.
    7. A bal oldali ablakTábla **Mintalekérdezések** lapján **SharePoint** **SharePoint, a Helyek terület megfelelő helylekérdezések csoportjában válassza ki a telephely bejezését a hely relatív elérési útja alapján.**
    8. Adja meg az állomásnév **\{és\}** **\{a kiszolgáló relatív útvonalának paramétereit \}**. Például adja meg az állomásnevet `<domain>.sharepoint.com`**\{\}**`sites/<siteName>`**\{és a kiszolgáló relatív elérési útját.\}**

        > [!NOTE]
        > Az alapértelmezett webhely esetén hagyja üresen **\{a kiszolgáló relatív elérési út\}** paraméterét.

    9. Válassza a **Lekérdezés futtatása** lehetőséget, majd mentse az eredményt.
    10. Konfigurálja a következő lekérdezést.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        Ebben a lekérdezésben **\{a webhely-azonosító\}** **az** előző lekérdezési válaszból származó azonosítócsomópont értéke.

        Itt a kérelem törzse.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        Ebben a kérelem törzsében **\{\}** **az alkalmazásazonosító az alkalmazás (ügyfél)** azonosítója, **\{\}** **az alkalmazásnév pedig az alkalmazásnév** értéke.

        ![POST lekérdezés.](media/app-id-query.jpg)

    11. Az Engedélyek **módosítása lapon** válassza **az** Engedélyek panelt, **majd válassza a Sites** \> **Sites.FullControl.Minden** \> **hozzájárulás.**
    12. Válassza a Lekérdezés **futtatása lehetőséget**.

Az elektronikus számlázási szolgáltatás hozzáfér a webhelyhez SharePoint.
