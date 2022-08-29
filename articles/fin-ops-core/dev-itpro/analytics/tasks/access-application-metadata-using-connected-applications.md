---
title: Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával
description: A cikk lépései azt ismertetik, hogyan tervezhet egy felhasználó új, a metaadatok használatával elektronikus jelentési modell leképezését a Szabályozó konfiguráció szolgáltatás felhasználója.
author: kfend
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: 1a935b96e247978fc2b2f9449d403c92bff35f17
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267872"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával

[!include [banner](../../includes/banner.md)]

Az alábbi lépések azt ismertetik, hogyan tervezhet meg egy új elektronikusjelentés-modellleképezést egy RCS-felhasználó a Rendszergazda vagy elektronikus jelentéskészítő fejlesztő szerepkörben, a pénzügyek és műveletek metaadatai alapján. Alkalmazás-metaadatokhoz való hozzáférés online RCS összekapcsolt alkalmazások használatával történik A minta ER-modell-hozzárendelést a külföldi kereskedelmi tranzakciók elérése érdekében konfigurálja a program. Ezeket a lépéseket az RCS szolgáltatásban csak akkor lehet végrehajtani, ha előbb a cikk lépéseit, [a konfigurációs szolgáltatókat létrehozza és aktívként megjelöli](er-configuration-provider-mark-it-active-2016-11.md). Ha nem fejeződött be a cikk lépései, [az alkalmazás metaadatainak elérése az ER](access-application-metadata-er-configuration.md) konfiguráció használatával, töltse [le az elektronikus jelentési](https://download.microsoft.com/download/0/4/e/04e13839-e423-442b-a6c2-dd35b1045c2d/Dynamics%20365%20for%20Finance%20and%20Operations%208.1%20Electronic%20reporting%20task%20guides.zip) példákat, és mentse a következő ER-konfigurációkat: Külkereskedelmi metaadatok.xml; Külkereskedelmi modell.xml; Külkereskedelmi mapping.xml, majd az eljárás lépéseit kell végrehajtani.

## <a name="prerequisites"></a>Előfeltételek
1. Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra. 
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit. 

## <a name="get-required-er-configurations"></a>Szükséges elektronikus jelentéskészítés-konfigurációk lekérése
1. Kattintson a **Jelentéskészítés konfigurációi** lehetőségre. 
2. Ha már végrehajtotta az [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](access-application-metadata-er-configuration.md) eljárásban megadott lépéseket, akkor az aktuális RCS-példány már rendelkezik az összes szükséges ER konfigurációval (külkereskedelmi metaadatok, modell-hozzárendelési konfigurációk). Az alfeladat többi műveletét kihagyhatja. 
3. Kattintson az **Átváltás** elemre. 
4. Kattintson a **Betöltés XML-fájlból** lehetőségre. 
5. A **Tallózás** használatával válassza ki a **Foreign trade metadata.xml** fájlt. 
6. Kattintson az **OK** gombra. 
7. Kattintson az **Átváltás** elemre. 
8. Kattintson a **Betöltés XML-fájlból** lehetőségre. 
9. A **Tallózás** használatával válassza ki a **Foreign trade model.xml** fájlt. 
10. Kattintson az **OK** gombra. 
11. Kattintson az **Átváltás** elemre. 
12. Kattintson a **Betöltés XML-fájlból** lehetőségre. 
13. A **Tallózás** használatával válassza ki a **Foreign trade mapping.xml** fájlt. 
14. Kattintson az **OK** gombra. 

## <a name="register-a-connected-application"></a>Egy összekapcsolt alkalmazás regisztrálása
1. Zárja be a lapot. 
2. Zárja be a lapot. 
3. Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra. 
4. Kattintson az **Összekapcsolt alkalmazások** elemre. 
5. Győződjön meg róla, hogy a konfigurált alkalmazás Azure alapú és elérhető az aktuális RCS-felhasználó számára. Azt is meg kell adni, hogy az aktuális RCS felhasználó hozzáférjen a kiválasztott alkalmazáshoz, és az alkalmazás felhasználóként regisztrálva van az alkalmazás metaadatainak elérése érdekében. 
6. Kattintson az **Új** elemre. 
7. A **Név** mezőbe írja be a „MyConnectedApp” szöveget. 
8. Az **Alkalmazás** mezőbe írja be a: https:// mycompany.operations.dynamics.com. 
9. A **Bérlő** mezőbe írja be a következőt: „mycompany.onmicrosoft.com”. 
10. Kattintson a **Mentés** gombra. 
11. Ha ellenőrzi a kapcsolatot a konfigurált alkalmazással, akkor a **Csatlakozás a távoli alkalmazáshoz** lapon kattintson a **Kattintson ide a kijelölt távoli alkalmazáshoz való kapcsolódáshoz** elemre. 
12. Kattintson a **Kapcsolat ellenőrzése** elemre. 
13. Kattintson a **Bezárás** gombra. 
14. Amikor a kapcsolat ellenőrzése sikeres volt, a program frissíti a verziószámot és a bérlő adatait a konfigurált alkalmazáshoz az aktuális rácsban. 

## <a name="review-existing-model-mapping-configuration"></a>Meglévő modell leképezés konfiguráció áttekintése
1. Zárja be a lapot. 
2. Kattintson a **Jelentéskészítés konfigurációi** lehetőségre. 
3. A fában bontsa ki a **Foreign trade model** elemet. 
4. A fán válassza ki a **Foreign trade model\Foreign trade mapping** elemet. 
5. Bontsa ki az **Előfeltételek** szakaszt. 

    > [!NOTE]
    > Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik. A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik. 

6. Kattintson a **Tervező** pontra. 
7. Kattintson a **Tervező** pontra. 
8. A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations„\Tábla rekordjai** csomópont. 
9. Kattintson a **Gyökér hozzáadása** gombra. 
10. A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket. 

    > [!NOTE]
    > Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik. A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik. 

11. Kattintson a **Mégse** gombra. 
12. Zárja be a lapot. 
13. Zárja be a lapot. 

## <a name="assign-connected-application-to-model-mapping"></a>Csatlakoztatott alkalmazás társítása a modell-hozzárendeléshez 
1. Kattintson a **Szerkesztés** lehetőségre. 
2. Válassza ki a **MyConnectedApp** alkalmazást. 

    > [!NOTE]
    > Ez a leképezés jelenleg a kiválasztott összekapcsolt alkalmazás metaadataira vonatkozik. Amikor ugyanaz a leképezés a metaadatok konfigurációját és a kapcsolódó alkalmazást egyszerre hivatkozza, a program a csatlakoztatott alkalmazás metaadatait fogja használni. 

3. Kattintson a **Tervező** pontra. 
4. Kattintson a **Tervező** pontra. 
5. A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations„\Tábla rekordjai** csomópont. 
6. Kattintson a **Gyökér hozzáadása** gombra. 
7. A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket. 

    > [!NOTE]
    > Már több, mint két alkalmazástábla szerepelt, mivel ez a leképezés a társított alkalmazás összes metaadatát felhasználja. 

8. Kattintson a **Mégse** gombra. 
9. Kattintson az **Érvényesítés** gombra. 

    > [!NOTE]
    > Az adatmodell elemeit az adatforrások olyan cikkeihez társítottuk sikeresen, amelyek leírása az ehhez a leképezéshez hozzárendelt összekapcsolt alkalmazás metaadatainak részleteivel történik. 

10. Zárja be a lapot. 
11. Zárja be a lapot. 

Ha egy másik verziójú alkalmazás metaadatainak használatával szeretné értékelni ezt a modellt, akkor regisztráljon egy másik összekapcsolt alkalmazást, rendelje hozzá a modell hozzárendeléséhez, és ellenőrizze az új metaadatokkal összevetve.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

