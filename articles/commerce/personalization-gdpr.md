---
title: Leiratkozás a személyre szabott ajánlatokról
description: Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a személyre szabott ajánlatok fogadásáról való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6a64b45e1326673dd84c3c705491c9c100cdd069
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817523"
---
# <a name="opt-out-of-personalized-recommendations"></a>Leiratkozás a személyre szabott ajánlatokról

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a személyre szabott ajánlatok fogadásáról való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A fiók létrehozása során az új vásárlók számára automatikusan be van állítva a személyre szabott ajánlatok fogadására. A Dynamics 365 Commerce azonban többféle módszert kínál a kereskedőknek, amellyel felhasználóik számára lehetővé tehetik az ezen ajánlások fogadásáról való leiratkozást és a személyes adatok feldolgozásának korlátozását. A személyre szabott ajánlások fogadásáról leiratkozott hitelesített felhasználóknak esetében azonnal leáll a személyre szabott listák megelenítése. Ezenkívül a személyre szabáshoz gyűjtött összes személyes adat el lesz távolítva a személyre szabott ajánlások modelljeiből.

Ha további tájékoztatást szeretne arról, hogyan lehet személyre szabott termékajánlásokat kapni, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>A leiratkozási élmény megvalósítási módjai a kereskedők számára

A leiratkozási élményt a kerekedők háromféle módon tudják megvalósítani.

### <a name="opting-out-on-behalf-of-users"></a>Leiratkozás a felhasználók nevében

A Commerce háttérrendszer Fiókkezelés részében a kereskedők elvégezhetik a leiratkozást a felhasználók nevében.

1. A háttérrendszer kezdőoldaláról keressen rá az **összes vevőre**.
1. Keressen meg és válasszon ki egy vevőt, majd válassza ki a **Kiskereskedelem** gyorslapot.

    ![Kiskereskedelem gyorslap](./media/Disablepersonalizationpart1.png)

1. Az **Adatvédelem** alatt állítsa a **Személyre szabás letiltása** beállítást **Igen**értékre.

    ![Adatvédelmi beállítások](./media/Disablepersonalizationpart2.png)

1. Válassza a **Mentés** gombot, és zárja be az oldalt.

### <a name="module-based-opt-out-experience"></a>Modulalapú leiratkozási élmény

A kereskedők lehetővé tehetik a hitelesített felhasználók számára, hogy saját maguk iratkozzanak le a személyre szabott ajánlásokról. Ennek a leiratkozási élménynek a biztosításához adja hozzá a leiratkozási modult a vásárlói fiók profiloldalaihoz.

### <a name="custom-extensions"></a>Egyéni bővítmények

A kereskedők saját bővítményeiket hozhatnak létre a felhasználók leiratkozási élményének kezeléséhez. További információk: [Retail Server API-k hívása](e-commerce-extensibility/call-retail-server-apis.md) és [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Személyre szabott ajánlási adatok digitális másolatának beolvasása egy hitelesített felhasználó nevében

Előfordulhat, hogy a vevők a személyes adataik digitális másolatát szeretnék beszerezni, és meg szeretnék tekinteni az ajánlásaik eredményeinek exportált nézetét is. Ha egy vevő igényli ezeket az adatokat, akkor a kiskereskedőnek létre kell hoznia egy testreszabott kiterjesztést, amely meghívja a Retail Server alkalmazásprogramozási felületét (API), és lekérdezi az **Önnek ajánljuk** lista összes eredményét a vevő vevői azonosítója alapján. Ezután az eredmények vesszővel tagolt értékek (CSV) formátumban exportálhatók és a vevővel megoszthatók.

A következő példa azt mutatja be, hogyan hajthatja végre egy kiskereskedő ezt a feladatot.

1. A kiskereskedő létrehoz egy egyéni bővítményt a személyes ajánlások adatainak lekéréséhez a felhasználó nevében. A modulok létrehozásával, a meglévő modulok klónozásával, a Retail Server API-k hívásával és a hívási adatokkal kapcsolatos további tudnivalókat lásd: [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).
2. Az egyéni bővítmény hívást indít a **get-recommendations** alapadat-művelethez, és átadja a szükséges információkat a lista követelményei alapján. Az **Önnek ajánljuk** lista esetében a bűvítménynek át kell adnia a helyes listanevet és a vevő ügyfél azonosítóját az adatműveletnek.

    Az egyéni bővítmény létrehozásához egyik módja az ajánlási eredmények visszaadására szolgáló, meglévő termékgyűjtő modul klónozása. A meglévő modul klónozásával a kiskereskedő módosíthatja a meglévő kódot, és hozzáadhat egy új gombot, amely az ajánlatok eredményeit CSV-fájlba exportálja. További információk: [Modulkönyvtár moduljának klónozása](e-commerce-extensibility/clone-starter-module.md) és [Termékgyűjtési modulok](product-collection-module-overview.md).

    A Retail Server API-függvénytár teljes nézetét lásd: [Retail Server ügyfél és fogyasztói API-k](dev-itpro/retail-server-customer-consumer-api.md).

3. Miután létrehozta az egyéni bővítményt, a kiskereskedő a hitelesített felhasználó egyedi vevői azonosítója alapján exportálhatja az összes ajánlási eredmény CSV-fájlját.
4. A kiskereskedő megoszthatja a hitelesített felhasználóval az exportált CSV-fájlt, amely által ajánlott termékek teljes személyre szabott listáját tartalmazza.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Termékajánlatok hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)
