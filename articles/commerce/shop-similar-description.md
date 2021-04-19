---
title: „Hasonló megvásárlása leírás” javaslatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan engedélyezheti a „hasonló megvásárlása leírás” termékjavaslatokat a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: bsokolov
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ce01ef1d4b916d955685b4d01dafd3d54d6fcebd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795405"
---
# <a name="enable-shop-similar-description-recommendations"></a>„Hasonló leírású termékek vásárlása” javaslatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan engedélyezheti a „hasonló megvásárlása leírás” termékjavaslatokat a Microsoft Dynamics 365 Commerce szolgáltatásban.

A „hasonló megvásárlása leírás” javaslatokat tartalmazó funkció a Dynamics 365 Commerce szolgáltatásban mesterséges intelligenciát és gépi tanulást (AI-ML) alkalmaz, hogy olyan termékeket ajánljon a vevőnek, amelyek leírása hasonlít ahhoz, amit a vevő keres. A „hasonló megvásárlása leírás” javaslatok elérhetők a Commerce összes kiskereskedelmi csatornáján, ezzel a kiskereskedők segíthetnek a vevőknek abban, hogy könnyebben megtalálják azt, amit akarnak.

A „hasonló megvásárlása leírás” javaslatok a termékek képeit és leírásait használják a megtekintett termékek változataiban ahhoz, hogy találatot adjanak és javasoljanak vizuálisan hasonló termékeket a kiskereskedők termékkatalógusaiból.

A „hasonló megvásárlása leírás” javaslatlisták elérhetők mind a pénztárnál (POS), mind az e-kereskedelmi felületeken.

## <a name="example-scenarios"></a>Példaforgatókönyvek

A következő példaforgatókönyvek azokat a javaslattípusokat mutatják be, amelyeket a „hasonló megvásárlása leírás” funkció nyújthat:

- Egy vevő megtekint egy retró stílusú szarukeretes szemüveget, és egy sor ajánlást kap más, hasonló kialakítású szemüvegekre vonatkozóan a kiskereskedői kínálatból.
- Egy vevő a „hasonló megvásárlása leírás” javaslatokat használja olyan kávéízek keresésére, amelyek hasonlóak ízben ahhoz, amelyet korábban vásárolt a kiskereskedőtől.

## <a name="set-up-shop-similar-description-recommendations"></a>„Hasonló megvásárlása leírás” javaslatok beállítása

A termékjavaslatok funkció csak azoknak a Commerce-ügyfeleknek támogatott, akik a tárhelyüket az Azure Data Lake Storage Gen2 szolgáltatásba telepítették.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt a „hasonló megvásárlása leírás” javaslatok megjeleníthetők a vevőknek, a következő előfeltételeknek kell megfelelnie:

- [Termék ajánlásainak engedélyezése ](enable-product-recommendations.md)a Commerce Headquarters alkalmazásban.
- Győződjön meg róla, hogy a médiakiszolgáló támogatja a HTTPS-hívásokat.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>„Hasonló megvásárlása leírás” javaslatok funkció bekapcsolása

Ha be szeretné kapcsolni a Commerce központi felületén a „hasonló megvásárlása leírás” ajánlások funkciót, kövesse az alábbi lépéseket.

1. A **Funkciókezelés** munkaterületen az elérhető funkciók listájában keresse meg és válassza ki a **Hasonló megvásárlása leírás** lehetőséget.
1. A jobb oldali panelen válassza ki az **Engedélyezés** lehetőséget.

> [!NOTE]
> A funkció bekapcsolásakor a rendszer elkezdi létrehozni a termékajánlási listákat. Megtörténhet, hogy akár egy napot is igénybe vesz, amíg a listák elérhetővé és láthatóvá válnak az online felületen és a pénztárterminálokon.
>
> Ha kikapcsolja a funkciót, a termékjavaslatok más típusait ez nem érinti. A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Hasonló megvásárlása leírás hozzáadása a termékadatok oldalaihoz

Miután bekapcsolta a Hasonló megvásárlása leírás javaslatok funkciót a Commerce központi felületén, a Commerce webhelykészítő lehetővé teszi, hogy hozzáadjon **Hasonló megvásárlása leírás** gombot a vásárlásmezőhöz bármely termék adatlapján (PDP). A gombot kiválasztó vevő egy erre dedikált **Hasonló megvásárlása leírás** oldalra kerül, ahol vizuálisan hasonló termékek jelennek meg. Itt a vevő használhatja a választókat a termékek szűrésére.

Ahhoz, hogy a **Hasonló megvásárlása leírás** gombot hozzáadja a PDP-hez a Commerce webhelykészítő segítségével, kövesse ezeket a lépéseket.

1. Nyisson meg egy már meglévő webhelykészítő lapot, ami vásárlásmező modult tartalmaz.
1. A bal oldali navigációs ablakban válassza ki a vásárlásmező modult.
1. A jobb oldali navigációs ablakban jelölje be a **Hasonló megvásárlása hivatkozás engedélyezése** jelölőnégyzetet.
1. Válassza a **Mentés** lehetőséget.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. Az oldal közzététele után a PDP tartalmazni fogja a **Hasonló megvásárlása leírás** gombot.

A következő ábra bemutatja a **Hasonló megvásárlása hivatkozás engedélyezése** jelölőnégyzetet, és a **Hasonló megvásárlása leírás** gombot egy PDP-oldalon a webhelykészítőben.

![A Hasonló megvásárlása hivatkozás engedélyezése jelölőnégyzeten és Hasonló megvásárlása leírás gomb egy PDP-oldalon a webhelykészítőben](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[„Hasonló szettek vásárlása” javaslatok engedélyezése](shop-similar-looks.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]