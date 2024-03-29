---
title: AI-ML-alapú termékajánlás eredményeinek kiigazítása
description: Ez a cikk bemutatja, hogy hogyan lehet testreszedni a termék ajánlási eredményeit a vállalatnak a jól érthető intelligencia – gépi tanulás (AI-STB) alapján.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d74fa013d44e0f113bdf0ce0ca9efeb943926e9f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901702"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a>AI-ML-alapú termékajánlás eredményeinek kiigazítása


[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet a vállalatnak a visszaható intelligencia – gépi tanulás (AI-STB) alapján módosítani a termék ajánlási eredményeit. 

A termékjavaslatok engedélyezése után az alapértelmezett beállítások lépnek érvénybe ezek a paraméterek számos szükséglethez használhatók lehetnek. A legjobb az, ha hagynak egy kis időt arra, hogy az eredmények megfelelnek-e a termékek értékesítési irányának. Javasoljuk, hogy néhány napig értékelje ki az eredményeket, mielőtt igény szerint módosítaná a paramétereket az újratesztelés előtt. 

## <a name="understanding-recommendation-list-parameters"></a>Az ajánlási lista paramétereinek ismertetése

A paraméterek módosítása előtt az alábbi részből megismerheti, hogy milyen hatással lesznek az eredményekre.

### <a name="trending-product-list"></a>"Népszerű" terméklista

A "Népszerű" terméklista két módosítható paraméterrel rendelkezik:

![Példa a "Népszerű" lista alapértelmezett paramétereire](./media/exampletrendingparameters.png)

1. **Új termékek belefoglalása a legutóbbi X napból** – Azok a termékek, amelyek az aktuális dátumtól számított megadott számú napon belül lettek hozzáadva használhatók termékjelöltek kiválasztásához. A kép alapértelmezett értéke azt sugallja, hogy maximum 180 napos termékek használhatók fel a népszerű termékek listájában.
1. **Értékesítések belefoglalása a legutóbbi X napból** – Azok az értékesítési tranzakciók, amelyek az aktuális dátumtól számított megadott számú napon belül történtek használhatók a termékek rendezéséhez. A fenti alapértelmezett érték azt sugallja, hogy az elmúlt 30 napban a termékhez tartozó összes vásárlás lenne felhasználva a termék helyének meghatározásához a népszerű termékek listáján. 

### <a name="best-selling-product-list"></a>"Legkelendőbb" termékek listája

A vállalattól függően a "Legkelendőbb" lista eltérő eredményt adhat, mint a népszerű, annak ellenére, hogy mindkettő tranzakcióadatokat használ a termékek rendezéséhez. Mivel a legjobban fogyó termékek esetében nincs határ a szortiment dátuma alapján, a legjobban fogyó termékek listáján megjelenhetnek olyan nagyon népszerű, régebbi termékek , amelyek már lekerültek a népszerű termékek listájáról. 

A "Legkelendőbb" terméklista egyetlen módosítható paraméterrel rendelkezik:

![Példa a Legkelendőbb lista alapértelmezett paraméterére.](./media/examplebestsellingparameters.PNG)

1. **Értékesítések belefoglalása a legutóbbi X napból** – Azok az értékesítési tranzakciók, amelyek az aktuális dátumtól számított megadott számú napon belül történtek használhatók a termékek rendezéséhez. A fenti alapértelmezett érték azt sugallja, hogy az elmúlt 30 napban a termékhez tartozó összes vásárlás lenne felhasználva a termék helyének meghatározásához a Legkelendőbb termékek listáján. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Termékek manuális hozzáadása vagy eltávolítása az ajánlási listákból

### <a name="for-new-trending-or-best-selling-lists"></a>Az "Új", "Népszerű" vagy "Legkelendőbb" listák esetében

1.  Válassza a **Retail és Commerce** > **Termékajánlatok** > **Ajánlási paraméterek** elemet.
1.  A megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.
1.  Jelölje ki a listát a termékek hozzáadásához vagy eltávolításához.
1.  Ha termékeket szeretne hozzáadni a táblázathoz, válassza a **Sor hozzáadása** lehetőséget. 
1.  A Termék oszlopban keressen egy terméket **Név** vagy **Termékszám** alapján.

    ![Példa a termék keresésére az Új terméklistán.](./media/examplenewlistconfiguration1.png)

1.  A Sor típusa oszlopban válassza ki a két beállítás egyikét:
    -   **Belefoglalás** – egy terméket a lista elejére kényszerít
    -   **Kizárás** – eltávolít egy terméket a listából.
    
    ![Példa a termékeknek az Új terméklistára való felvételére vagy Új terméklistáról való kihagyására.](./media/examplenewlistconfiguration2.png)

1.  A **Megjelenítési sorrend** módosítása megváltoztatja azt, hogy a **belefoglalásra** megjelölt termékek milyen sorendben jelenjenek meg a listában.
    - Ha két terméknél ugyanaz **megjelenítési sorrend** értéke, akkor a két eredmény végső sorrendje eltérhet a háttéroldaltól.
1.  Termékek eltávolításához a táblázatból: válassza ki a törölni kívánt sort, és válassza az **Eltávolítás** elemet.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>A "Másoknak ez is tetszett" vagy "Gyakran együtt vásárolt" listák esetében

A "Gyakran együtt vásárolt", illetve a "Másoknak ez is tetszett" listák esetében gépi tanulást alkalmazunk a fogyasztók vásárlási mintáinak elemzéséhez, illetve kapcsolódó termékek ajánlásához, amelyeket gyakran megvásároltak együtt egy megtekintett termékkel. 
 
A *megtekintett termék* az a termék, amelyhez az eredményeket generálni szeretné. Az ajánlási listák manuális módosításával összefüggésben ehhez a termékhez adja hozzá vagy távolítja el az eredményeket. 

A következő lépések végrehajtásával manuálisan adhat hozzá vagy távolíthat el eredményeket egy alaptermékhez:
1.  Válassza ki a **Kiinduló terméket**. 
1.  A **Termék** oszlopban keressen egy terméket **Név** vagy **Cikkszám alapján.**
![Példa a termék keresésére a Gyakran együtt vásárolt listában.](./media/exampleFBTlistconfiguration1.png)
1. A **Sor típusa** oszlopban válassza ki a két beállítás egyikét:
    - **Belefoglalás** – egy terméket a lista elejére kényszerít
    - **Kizárás** – eltávolít egy terméket a listából.     
![Példa egy termék belefoglalására vagy kizárására a Gyakran együtt vásárolt listában.](./media/exampleFBTlistconfiguration2.png)
1.  Termékek eltávolításához a táblázatból: válassza ki a törölni kívánt sort, és válassza az Eltávolítás elemet.


## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Termékajánlatok hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]