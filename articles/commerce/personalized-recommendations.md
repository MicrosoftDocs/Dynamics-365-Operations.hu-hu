---
title: Személyre szabott termékajánlatok engedélyezése
description: Ez a témakör bemutatja, hogyan készíthet személyre szabott termékajánlatokat az ügyfelei számára a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f535cf0bc3c733426af22cf453ffe97f721f8d9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000583"
---
# <a name="enable-personalized-recommendations"></a>Személyre szabott ajánlatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan készíthet személyre szabott termékajánlatokat az ügyfelei számára a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce programban a kiskereskedők a személyre szabott termékajánlatokat (más néven személyre szabásokat) tehetnek elérhetővé. Ily módon a személyre szabott ajánlások belefoglalhatók az online felhasználói élménybe és a pénztárba (POS). Ha be van kapcsolva a személyre szabási funkció, akkor a rendszer társíthatja a felhasználó beszerzési és termékinformációit az egyéni ajánlások előállításához.

## <a name="personalization-prerequisites"></a>Személyre szabás előfeltételei

Mielőtt személyre szabott termékajánlásokat tehetne elérhetővé a vevők számára, vegye figyelembe, hogy csak a Commerce azon felhasználónak esetében támogatottak a termékajánlások, akik áttelepítették a tárolójukat az Azure Data Lake Store rendszerbe. Mielőtt a vevők személyre szabott termékajánlásokat kaphatnának, a kereskedőknek [be kell kapcsolniuk a termékajánlatokat](enable-product-recommendations.md).

> [!NOTE]
> A termékajánlások bekapcsolásával bekapcsolja a személyre szabást is. Ha azonban kikapcsolja a személyre szabást, akkor nem kapcsolja ki a termékajánlások egyéb típusait.

A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="turn-on-personalization"></a>Személyre szabás bekapcsolása

Ha be szeretné kapcsolni a személyre szabást, hajtsa végre az alábbi lépéseket.

1. A Commerce Headquarters alkalmazásban keressen rá a **Szolgáltatások kezelése** lehetőségre.
1. Válassza a **Mind** lehetőséget, ha meg szeretné tekinteni a rendelkezésre álló szolgáltatások listáját. 
1. A Keresés mezőbe írja be az **Ajánlatok** kifejezést.
1. Válassza ki a **Testreszabott termékajánlatok** funkciót.
1. A **Testreszabott termékajánlatok** tulajdonságok ablaktáblán válassza az **Engedélyezés most** lehetőséget.

![Személyre szabás bekapcsolása](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> A személyre szabás bekapcsolásakor a személyre szabott termékajánlási lista létrehozásának folyamata elindul. Előfordulhat, hogy egy napra is szükség lehet, amíg a listák elérhetővé és láthatóvá válnak online és a pénztárnál.

## <a name="personalized-lists"></a>Személyre szabott lista

A már létező, géppel készített listák személyre szabásának engedélyezése mellett az ajánlatok szolgáltatás lehetővé teszi a termék felfedezési élményének személyre szabását online és a pénztárnál egyaránt.

Ha be van kapcsolva a személyre szabás, akkor a kiskereskedők személyre szabott „Önnek ajánljuk” listákat jeleníthetnek meg online, vagy „Vásárlónak ajánlott” listákat a POS terminálokon. Ezenkívül a kiskereskedők személyre szabhatják a meglévő termékajánlási listákat, és az Általános adatvédelmi rendelet (GDPR) által biztosított leiratkozási élményt nyújthatnak a hitelesített felhasználók számára. Ha kikapcsolja a személyre szabást, kikapcsolja ezeket a funkciókat is.

### <a name="online-picks-for-you-lists"></a>Online „Önnek ajánljuk” listák

A „Önnek ajánljuk” lista egy mesterséges intelligencia/gépi tanulás (AI-ML) lista, amely ajánlott termékek személyre szabott listáját jeleníti meg egy hitelesített felhasználó számára. Ez a lista a felhasználói omnicsatorna beszerzési előzményein alapul. A személyre szabott ajánlások dinamikusan frissülnek, ahogy a felhasználó több beszerzést eszközöl. Ez a listatípus a kategóriák szerinti szűrést is támogatja, így a kiskereskedők legjobb ajánlatokat jeleníthetnek meg a navigációs hierarchiák alapján.

Mielőtt az „Önnek ajánljuk” lista megjelenne bármilyen e-Commerce oldalon, a következő felhasználói követelményeknek kell teljesülniük:

- A felhasználóknak be kell jelentkezniük. A névtelen felhasználók nem fogják látni a személyre szabott ajánlásokat.
- A felhasználóknak legalább egy beszerzéssel kall rendelkezniük a fiókjukban.
- A felhasználóknak fel kell iratkozniuk a személyre szabott ajánlások fogadására.

A következő ábra egy „Önnek ajánljuk” lista példáját jeleníti meg egy online áruház oldalon.

![Online „Önnek ajánljuk” lista](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>„Vásárlónak ajánlott” listák a pénztárnál

Az ügyfélkör-kezelési élmény javítása érdekében a kiskereskedők személyre szabhatják a meglévő ügyfélrészletek oldalakat egy környezetfüggő „Vásárlónak ajánlott” lista hozzáadásával.

A következő ábra egy „Vásárlónak ajánlott” lista példáját jeleníti meg POS terminálon.

![„Vásárlónak ajánlott” lista a pénztárnál](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Személyre szabás alkalmazása a meglévő ajánlatok listáira

A kiskereskedők személyre szabhatják a meglévő ajánlási listákat, például: „Új”, „Népszerű”, „Legkelendőbb”, „Másoknak ez is tetszett” és „Gyakran együtt vásárolt modell”. Ha a meglévő listákra alkalmaznak személyre szabást, akkor a bejelentkezett felhasználó által korábban vásárolt termékek eltávolításra kerülnek ezekből a listákból. Mind a névtelen felhasználók, mind a személyre szabott ajánlások fogadásáról leiratkozott felhasználók számára a meglévő listák alapértelmezett verziói jelennek meg. Ennélfogva a kiskereskedőknek nem kell manuálisan karbantartania különböző oldalélményeket.

Például egy bejelentkezett felhasználó már megvásárolta a fekete órát és a barna munkabakancsot, amely a „Népszerű - alapértelmezett” listában jelenik meg a következő ábrán. Ennélfogva a felhasználó ezen termékek helyett új termékeket fog látni a „Népszerű - személyre szabott” listában látható módon.

![Személyre szabás alkalmazása](./media/applypersonalization.png)

Személyre szabás alkalmazásához egy meglévő ajánlati listára a Commerce webhelykészítőjében, kövesse az alábbi lépéseket.

1. Nyisson meg egy termékgyűjtő modult tartalmazó meglévő webhelykészítő lapot.
1. A bal oldali navigációs ablakban válassza ki a termékgyűjtő modult.
1. A jobb oldali navigációs ablakban válassza ki a listát a **Termékek** alatt.
1. A **Terméklista-konfiguráció kiválasztása** párbeszédpanelen, a **Típus** alatt vélassza ki a típust.
1. Válassza ki a **Személyre szabás alkalmazása** jelölőnégyzetet, majd válassza az **OK** lehetőséget.

    ![Személyre szabás alkalmazása egy népszerű listára](./media/ApplyPersonalizationToTrending.PNG)

1. Mentse az oldalt, fejezze be a szerkesztését, majd tegye közzé. Az oldal közzététele után a bejelentkezett felhasználók személyre szabott népszerű listákat láthatnak.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]