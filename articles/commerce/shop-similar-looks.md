---
title: Engedélyezze a "hasonló megvásárlása" javaslatlistákat
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni a "hasonló megjelenésű" javaslatlistákat a Microsoft Dynamics 365 Commerce szolgáltatásnál.
author: bebeale
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e70365be8484d71ef9e0e9823b0a4406b0fd2761439780cafc30e1284bda1f20
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722000"
---
# <a name="enable-shop-similar-looks-recommendations"></a>„Hasonló szettek vásárlása” javaslatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet engedélyezni a "hasonló megjelenésű" javaslatlistákat a Microsoft Dynamics 365 Commerce szolgáltatásnál.

A "hasonló megvásárlása" javaslatlista funkció a Dynamics 365 Commerce által mesterséges intelligenciát és gépi tanulást (AI-ML) alkalmaz, hogy a vizuálisan hasonló termékeket a vevők számára ajánlani tudja. A "hasonló megvásárlása" javaslatok elérhetők a Commerce összes kiskereskedelmi csatornáján, ezzel a kiskereskedők növelhetik a vevők elégedettségét azzal, hogy könnyebben megtalálják azt, amit akarnak.

A "hasonló megvásárlása" javaslatlista funkció felhasználja a termékek képeit a megtekintett termékek változataiban ahhoz, hogy találatot adjon és javasoljon vizuálisan hasonló termékeket a kiskereskedők termékkatalógusaiból. 

A "hasonló megvásárlása" javaslatlisták elérhetők mind a pénztárnál (POS), mind az e-Commerce tapasztalatainál.

### <a name="example-scenarios"></a>Példaforgatókönyvek

- Egy vevő egy fekete csíkos pulóvert tekint meg, egy hasonló pulóverre vonatkozó ajánlást kap piros színben. A vevő kiválasztja a javasolt terméket az eredetileg megtekintett termék helyett és ezután kap javaslatot egy hasonló termékre piros színben. 
- A vevő a "hasonló megvásárlása" javaslatlisták alapján talál olyan fülbevalókra, melyek összeillenek ahhoz a gyűrűhöz, amelyet a vevő megvenne.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>"Hasonló megvásárlása" javaslatlista engedélyezése a Commerce Headquarters alkalmazásban

A termékjavaslatok funkció csak azoknak a Commerce-ügyfeleknek támogatott, akik a tárhelyüket az Azure Data Lake Gen2-re telepítették.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt a kiskereskedők megkezdhetik a "hasonló megvásárlása" javaslatlisták megjelenítését a vevők számára, két előfeltételt kell teljesíteni:

- [Termék ajánlásainak engedélyezése ](enable-product-recommendations.md)a Commerce Headquarters alkalmazásban.
- Győződjön meg róla, hogy a médiakiszolgáló támogatja a HTTPS-hívásokat.

Ahhoz hogy a javaslatlista keresőmotorja hozzáférhessen a termékek képeihez, a kiskereskedőknek generálniuk kell URL-címet a termékekhez. A termékek URL-címének generálásához kövesse az alábbi lépéseket a Commerce-központban.

1. Menjen a **Termék képek**-re.
1. A műveleti ablaktáblán válassza ki a **Médiasablon meghatározása** lehetőséget.
1. A **Médiasablon meghatározása** tulajdonságai panelen, a **Média URL-cím** alatt válassza ki a **URL-cím generálása** elemet.

> [!NOTE]
> Ha engedélyezi a "hasonló megvásárlása" ajánlások funkcióját, akkor a javaslatlista létrehozási folyamata elkezdődik. Legalább egy napot vesz igénybe, amíg a listák elérhetővé és láthatóvá válnak az online felületen és a POS terminálon.

Ha engedélyezni szeretné a Commerce Headquarters "hasonló megvásárlása" funkcióját, kövesse az alábbi lépéseket.

1. Lépjen a **Funkciókezelés** lehetőségre.
1. A rendelkezésre álló szolgáltatások listáján keresse meg és válassza ki a **hasonló megvásárlása** funkciót.
1. A jobb oldali ablakban válassza az **Engedélyezés** lehetőséget a szolgáltatás bekapcsolásához.

A következő ábra bemutatja a **hasonló megvásárlása** funkciót a **Funkciókezelés** oldalon a Commerce Headquarters lapján.

![A hasonló megvásárlása funkció a Funkciókezelés lapján a Commerce Headquarters oldalán.](./media/enableshopsimilarlooks.png)

Az előző feladatok befejezése után a POS-terminálokat a program automatikusan kibővíti egy  **hasonló termékek**-et tartalmazó panellel. Ha rámegy a **Bővebben** lehetőségre, a POS terminál felhasználóit egy "hasonló megvásárlása" oldalra irányítja, amely tovább szűrhető.

> [!NOTE]
> Ha kikapcsolja a "hasonló megvásárlása" javaslatok funkcióját, nem lesz egyik termék se hatással az ajánlatokra. A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Adja hozzá a hasonló megvásárlása gombot a termék adatlapjához a Commerce Site Builder segítségével

Miután engedélyezte a "hasonló megvásárlása" javaslatok funkcióját a Commerce Headquarters rendszerben, a Commerce webhelykészítő lehetővé teszi a kiskereskedők számára, hogy hozzáadjon **hasonló megvásárlása** gombot a vásárlásmezőhöz bármely termék adatlapján (PDP). A gombot kiválasztó vevő egy "hasonló megvásárlása" oldalra kerül, ahol vizuálisan hasonló termékek jelennek meg. Ott a vevő használhatja a választókat a termékek szűrésére.

Ahhoz, hogy a **Hasonló megvásárlása** gombot hozzáadja a PDP-hez a Commerce webhelykészítő segítségével, kövesse ezeket a lépéseket.

1. Nyisson meg egy már meglévő webhelykészítő lapot, ami vásárlásmező modult tartalmaz.
1. A bal oldali navigációs ablakban válassza ki a vásárlásmező modult.
1. A jobb oldali navigációs ablakban jelölje be a **Hasonló megvásárlása link engedélyezése** jelölőnégyzetet.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. A lap közzététele után a PDP tartalmazni fogja a **hasonló megvásárlása** gombot.

A következő ábra bemutatja a **Hasonló megvásárlása link engedélyezése** jelölőnégyzetet, és a **hasonló megvásárlása** gombot egy PDP-oldalon a webhelykészítőben.

![A Hasonló megvásárlása link engedélyezése jelölőnégyzeten és hasonló megvásárlása gomb egy PDP-oldalon a webhelykészítőben.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
