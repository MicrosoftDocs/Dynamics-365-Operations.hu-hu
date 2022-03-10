---
title: Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával
description: Az ebben a témakörben leírtak azt mutatják be, hogy a Regulatory Configuration Service felhasználói hogyan tervezhetik meg egy új elektronikus jelentési modell hozzárendelését a metaadatok használatával.
author: NickSelin
ms.date: 06/28/2019
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
ms.openlocfilehash: 6ad175f81edcf6b21927d85927c42a3398a0286b4a766e06c88a61952384f75e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754342"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy a Regulatory Configuration Service (RCS) Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhetnek új Elektronikus jelentés (ER) modell hozzárendelést az alkalmazás metaadatainak használatával. Az alkalmazás metaadatainak egy olyan ER-metaadat konfigurációval érhető el, amely minta metaadatkészletet tartalmaz, amelyek a külföldi kereskedelmi tranzakciók eléréséhez használható. Az alábbi lépések végrehajtásához az RCS-ben először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) eljárás cikk lépéseit. Ezután végezze el a következő témakör lépéseit: [RCS-ben felhasználandó alkalmazás-metaadatok előkészítése](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Előfeltételek
1. Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra. 
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit. 

## <a name="import-metadata-configuration"></a>Metaadat-konfiguráció importálása 
1. Kattintson a **Metaadat-konfigurációk** elemre. 
2. Importálja az alkalmazáshoz tartozó metaadatokat tartalmazó ER-metaadat konfigurációt, valamint a külkereskedelmi üzlethez tartozó elektronikus dokumentumokat létrehozó konfigurációs konfigurációt. Az ER metaadat-konfiguráció XML-fájlként lett exportálva, miközben az [RCS-ben felhasználandó alkalmazás-metaadatok előkészítése](prepare-application-metadata-rcs.md) eljárás lépései befejeződtek. 
3. Kattintson az **Átváltás** elemre. 
4. Kattintson a **Betöltés XML-fájlból** lehetőségre. 
5. A **Tallózás** használatával válassza ki a „Foreign trade metadata.xml” fájlt. 
6. Kattintson az **OK** gombra. 
7. Zárja be a lapot. 

## <a name="create-data-model-configuration"></a>Adatmodell-konfiguráció létrehozása
1. Kattintson a **Jelentéskészítés konfigurációi** lehetőségre. 
2. A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot. 
3. A **Név** mezőbe írja be, hogy „Külkereskedelmi metaadatok”. 
4. Kattintson a **Konfiguráció létrehozása** lehetőségre. 
5. Kattintson a **Tervező** pontra. 
6. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
7. A **Név** mezőbe írja be a következőt: „Gyökér”. 
8. Kattintson a **Hozzáadás** parancsra. 
9. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
10.    A **Név** mezőbe írja be a „Tranzakció” szöveget. 
11.    A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget. 
12.    Kattintson a **Hozzáadás** parancsra. 
13.    Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
14.    A **Név** mezőbe írja be az „Árucikk-kód” szöveget. 
15.    A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget. 
16.    Kattintson a **Hozzáadás** parancsra. 
17.    Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
18.    A **Név** mezőbe írja be a következőt: „Számlázott összeg”. 
19.    A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget. 
20.    Kattintson a **Hozzáadás** parancsra. 
21.    Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
22.    A **Név** mezőbe írja be a következőt: „Dátum”. 
23.    A **Cikktípus** mezőben válassza ki a **Dátum** lehetőséget. 
24.    Kattintson a **Hozzáadás** parancsra. 
25.    Kattintson a **Gyökérhivatkozás** lehetőségre. 
26.    Kattintson az **OK** gombra. 
27.    Kattintson a **Mentés** gombra. 
28.    Zárja be a lapot. 
29.    Kattintson az **Állapot módosítása** elemre. 
30.    Kattintson a **Befejezés** gombra. 
31.    Kattintson az **OK** gombra. 

## <a name="create-model-mapping-configuration"></a>Modell-leképezési konfiguráció létrehozása 
1. A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot. 
2. Az **Új** mezőbe írja be a „Fizetési modell (fiktív) adatmodellen alapuló modell-hozzárendelés” kifejezést. 
3. A **Név** mezőbe írja be, hogy „Külkereskedelmi leképezés”. 
4. Kattintson a **Konfiguráció létrehozása** lehetőségre. 
5. Bontsa ki az **Előfeltételek** szakaszt. 
6. Kattintson a **Szerkesztés** lehetőségre. 
7. Kattintson az **Új** elemre. 
8. A listában jelölje meg a kiválasztott sort. 
9. Az **Előfeltétel összetevő típusa** mezőben válassza ki a **Konfiguráció** lehetőséget. 
10.    A **Külkereskedelmi metaadatok** konfiguráció kiválasztása. 
11.    Kattintson a **Mentés** gombra. 
12.    Hozzáadtunk egy hivatkozást a „Külkereskedelmi metaadat” konfiguráció 1. verziójához. A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik. 
13.    Zárja be a lapot. 
14.    Kattintson a **Tervező** pontra. 
15.    Kattintson a **Tervező** pontra. 
16.    A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations„\Tábla rekordjai** csomópont. 
17.    Kattintson a **Gyökér hozzáadása** gombra. 
18.    A **Név** mezőbe írja be a következőt: „Intrastat”. 
19.    Az **Intrastat** táblarekordjainak kiválasztása. 
20.    Kattintson az **OK** gombra. 

> [!NOTE]
> Csak két tábla van felkínálva, mert csak két tábla lett hozzáadva a jelenleg használt metaadatok készletéhez. 

21.    Kattintson a **Kötés** gombra. 
22.    A fastruktúrában bontsa ki az **Intrastat** csomópontot. 
23.    A fastruktúrában válassza ki az **Instrastat\AmountMST** elemet. 
24.    A fastruktúrában bontsa ki ezt: **Transaction = Intrastat**. 
25.    A fán jelölje be a **Transaction = Intrastat\Számlázott összeg** lehetőséget. 
26.    Kattintson a **Kötés** gombra. 
27.    A fastruktúrában válassza ki az **Instrastat\TransDate** elemet. 
28.    A fastruktúrában válassza ki a **Transaction = Intrastat\Date** elemet. 
29.    Kattintson a **Kötés** gombra. 
30.    A fában bontsa ki az **Intrastat\>Relations** elemet. 
31.    A fában bontsa ki az **Intrastat\>Relations\IntrastatCommodity** elemet. 
32.    A faszerkezetben válassza ki ezt: **Intrastat\>Relations\IntrastatCommodity\Code**. 
33.    A fán jelölje be a **Transaction = Intrastat\Commodity code** lehetőséget. 
34.    Kattintson a **Kötés** gombra. 
35.    Kattintson az **Érvényesítés** gombra. 

> [!NOTE]
> Az adatmodell elemeit az adatforrások olyan cikkeihez társította, amelyek leírása az alkalmazási metaadatoknak a hivatkozott ER-metaadat konfigurációkból származó beállításával történik. 
36.    Kattintson a **Mentés** gombra. 
37.    Zárja be a lapot. 
38.    Zárja be a lapot. 
39.    Ha szükséges, bővíteni lehet a meglévő metaadatokat, majd exportálni lehet a ER metaadatok konfigurációjának új befejezett verzióját. Ezt követően importálhatja a RCS-be, és frissítheti a konfigurált modell-hozzárendelési konfiguráció előfeltételeit, amelyek az importált metaadat-konfiguráció új verziójára hivatkoznak. 

> [!NOTE]
> Ez a módszer az alkalmazás metaadatainak információinak beolvasására az egyetlen elérhető módszer a helyileg telepített alkalmazások esetében (azaz amikor a helyi üzleti adatok LBD vagy telephelyi, telepítési modell használata történik).
        


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]