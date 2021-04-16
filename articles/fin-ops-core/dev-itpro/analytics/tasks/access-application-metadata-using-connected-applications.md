---
title: Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával
description: Az ebben a témakörben leírt lépések azt mutatják be, hogy a Regulatory Configuration Service felhasználói hogyan tervezhetik meg egy új elektronikus jelentési modell hozzárendelését a metaadatok használatával.
author: NickSelin
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b113f0db1d44dc5fbda30e10d62ff939550f299
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748693"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy a Regulatory Configuration Service (RCS) Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhetnek új Elektronikus jelentés (ER) modell hozzárendelést a Finance and Operations alkalmazás metaadatainak használatával. Alkalmazás-metaadatokhoz való hozzáférés online RCS összekapcsolt alkalmazások használatával történik A minta ER-modell-hozzárendelést a külföldi kereskedelmi tranzakciók elérése érdekében konfigurálja a program. Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit az RCS-ben. Ha nem végezte el a témakör lépéseit [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](access-application-metadata-er-configuration.md), nyissa meg az [Elektronikus jelentéskészítési példák lapot](https://go.microsoft.com/fwlink/?linkid=862266) a következő ER-konfigurációk letöltéséhez és mentéséhez: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, majd hajtsa végre az eljárás lépéseit.

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