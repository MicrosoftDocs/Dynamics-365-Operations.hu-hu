---
title: Az RCS-ben felhasználandó alkalmazás-metaadatok előkészítése
description: A cikk áttekinti, hogyan lehet alkalmazás metaadatait tartalmazó új Elektronikus jelentéskészítési (ER) konfigurációt létrehozni ER modell-leképezési konfigurációk Regulatory Configuration Service szolgáltatásban való kialakításához.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbc1ca45a39f2a5c3309276f9e2f5d2b7d2ba5f7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684091"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Az RCS-ben felhasználandó alkalmazás-metaadatok előkészítése
[!include [banner](../../includes/banner.md)]

A következő lépések ismertetik, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók hogyan hozhatnak létre olyan új Elektronikus jelentéskészítési konfigurációt, amely tartalmazza az alkalmazás metaadatait az ER modell-leképezési konfigurációk Regulatory Configuration Service (RCS) rendszerben való kialakításához. Ez a konfiguráció olyan minta ER-modell-leképezési konfiguráció kialakításához használatos, amellyel hozzá lehet férni a külkereskedelmi tranzakciókhoz. Ebben a példában a mintavállalatra, a Litware, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket bármilyen vállalatban végrehajthatja. Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit.

## <a name="prerequisites"></a>Előfeltételek
1.    Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre. 
2.    Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit. 
3.    Kattintson a **Metaadat-konfigurációk** elemre. 
4.    Tegyük fel, hogy az RCS használatával olyan ER-megoldást szeretne kialakítani a Finance and Operation alkalmazáshoz, amely a külkereskedelmi üzleti tartományból származó adatokat tartalmazó elektronikus dokumentumokat készít. Ha meg szeretné adni az ER-adatmodell és a szükséges adatok forrása közötti leképezést, akkor az RCS-ben hozzáféréssel kell rendelkeznie a Finance and Operations alkalmazás metaadataihoz. Ennek megfelelően az ER-megoldás tervezése során olyan új ER-metaadat-konfigurációt állítunk be, amely a kiválasztott üzleti tartományok ER-jelentéseinek a létrehozásához pillanatnyilag szükséges összes metaadatot tartalmazza. 

## <a name="add-metadata-configuration"></a>Metaadat-konfiguráció hozzáadása 
1.    A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot. 
2.    A **Név** mezőbe írja be, hogy „Külkereskedelmi metaadatok”. 
3.    Kattintson a **Konfiguráció létrehozása** lehetőségre. 
4.    Kattintson a **Tervező** pontra. 
5.    Kattintson a **Hozzáadás** parancsra. 
  
> [!NOTE]
> Minden metaadatot a teljes pályázathoz, a kiválasztott modellekhez vagy a kiválasztott modulokhoz választhat ki. Ne feledje, hogy ebben az esetben a program automatikusan felveszi a következő metaadatokat: a rekordok, a felsorolások és a kiterjesztett adattípusok táblázatai. Ha további típusú metaadatokra van szüksége, akkor manuálisan kell őket felvennie. 
 
Bizonyos külkereskedelmi tranzakciókkal kapcsolatos metaadatokat az elemek manuális kijelölésével kell kiválasztani. 
  
6.    Kattintson az **Adatforrás hozzáadása** elemre. 
7.    Kattintson a **Táblarekordok** elemre. 
8.    A gyorsszűrő használatával szűrheti a **Név** mezőt az „Intrastat” érték előfordulására. 
9.    Az **Intrastat** táblarekordjának kiválasztása. 
10.    Kattintson az **OK** gombra.
  
A rekordok Intrastat-táblázatára vonatkozó metaadat-információkat adtunk hozzá. 
  
11.    A fastruktúrában bontsa ki a **Táblarekordok: Intrastat**\>**Kapcsolatok** részt. 
12.    A fastruktúrában válassza ki a **Táblarekordok: Intrastat**\>**Relations\IntrastatCommodity (Táblarekordok: EcoResCategory)** részt.     
13.    Kattintson a **Metaadatok hozzáadása** elemre. 
  
> [!NOTE]
> A kiválasztott rekordtábla szükséges kapcsolatainak metaadatait manuálisan kell felvenni. 
  
16.    Kattintson az **Adatforrás hozzáadása** elemre. 
17.    Kattintson a **Felsorolás** elemre. 
18.    A gyorsszűrő használatával szűrje a **Név** mezőt az „IntrastatDirection” értékre. 
19.    Válassza ki az **IntrastatDirection felsorolása** rekordot. 
20.    Kattintson az **OK** gombra. 
21.    Kattintson a **Mentés** gombra.  
22.    Zárja be a lapot. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>A metaadat-konfiguráció piszkozatának befejezése
1.    Kattintson az **Állapot módosítása** elemre. 
2.    Kattintson a **Befejezés** gombra. 
3.    Kattintson az **OK** gombra. 
4.    Válassza ki a befejezett verziót **1**. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>A metaadat-konfiguráció befejezett verziójának exportálása az alkalmazásból XML-fájlként
1.    Kattintson az **Átváltás** elemre. 
2.    Kattintson az **Exportálás XML-fájlként** elemre. 
3.    Kattintson az **OK** gombra. 
    
A létrehozott ER metaadat-konfigurációt olyan XML-fájlként mentette, amely importálható az RCS-be, és használható a külkereskedelmi üzleti tartomány metaadataira vonatkozó adatforrásként. Az információ alapján meg tudjuk határozni az alkalmazás metaadatai és az ER-adatmodell közötti leképezést.
