---
title: Elektronikus számlázás Egyiptomihoz
description: Ez a témakör az Microsoft Dynamics Egyiptomi elektronikus számlázással kapcsolatban nyújt segítséget a 365-ös pénzügyi és az elektronikus számlázásban Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: e21c4ce4d676c3194665672a078dc1e3d0492799
ms.sourcegitcommit: 5f7177b9ab192b5a6554bfc2f285f7cf0b046264
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661722"
---
# <a name="electronic-invoicing-for-egypt"></a>Elektronikus számlázás Egyiptomihoz

[!include [banner](../includes/banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az egyiptomi Elektronikus számlázással kapcsolatos első lépéseket. Ez a varázsló végigvezeti a konfigurációs szolgáltatáson (RCS) országfüggő konfigurációs lépéseken. Ezek a lépések kiegészítik az [Elektronikus számlázás beállítása modulban leírt lépéseket](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené a témakörben található eljárásokat, teljesítsen a következő előfeltételeket:

- Az Elektronikus számlázás témakörben [leírt módon ismerkedjen meg az elektronikus számlázással](e-invoicing-service-overview.md).
- Regisztráció RCS-re, és az elektronikus számlázás beállítása. További információért tekintse át az alábbi témaköröket:

    - [Az elektronikus számlázási szolgáltatás regisztrációja és telepítése](e-invoicing-sign-up-install.md)
    - [Azure-erőforrások beállítása elektronikus számlázáshoz](e-invoicing-set-up-azure-resources.md)
    - [A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba](e-invoicing-install-add-in-microservices-lcs.md)
    
- Aktiválja a Microsoft Dynamics 365 Pénzügy Dynamics 365 Supply Chain Management [vagy -alkalmazás és az Elektronikus számlázás szolgáltatás közötti integrációt az Aktiválás és beállítás integráció az Elektronikus számlázással leírtak szerint](e-invoicing-activate-setup-integration.md).
- Digitális tanúsítványtitk létrehozása az Azure kulcstárolóban, [és beállítása a vevői tanúsítványokban és azok tanúsítványában leírt módon](e-invoicing-customer-certificates-secrets.md). Tesztelési célokra az egyiptomi adóhatóság olyan specifikus digitális tesztelési tanúsítványokat biztosít, amelyek csak a tesztelési és megoldás-ellenőrzési fázisok során használhatók. További információt az [egyiptomi adóhatóság webhelyén talál az egyiptomi e-számlázási SDK-ban megadott hivatkozás használatával](https://sdk.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Országspecifikus konfiguráció az Egyiptomi elektronikus számla (ENGEDMÉNY) szolgáltatáshoz

Az Egyiptomi elektronikus számla **(EGYIPTOMI)** elektronikus számlázás funkció néhány paramétere az alapértelmezett értékekkel teszi közzé a teljesítést. Mielőtt telepíti az elektronikus számlázási szolgáltatást a szolgáltatási környezetben, ellenőrizze az alapértelmezett értékeket, és szükség szerint frissítse őket, hogy jobban tükrözzék az üzleti működést.

1. Az Egyiptomi elektronikus számla **(STB)**[globalizációs funkció legújabb verziójának importálása a globális tárházból való importálási funkciók leírása szerint](e-invoicing-import-feature-global-repository.md).
2. Az importált globalizációs funkció másolatának létrehozása és annak konfigurációs szolgáltatójának kiválasztása a [Globalizáció létrehozása funkcióban leírtak szerint](e-invoicing-create-new-globalization-feature.md).
3. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
4. A Beállítások **lap** rácsán válassza ki **az Értékesítési számla származtatott funkcióbeállítását**.
5. Válassza ki a **Szerkesztés** opciót.
6. A Feldolgozási **folyamat lapon**, **a Feldolgozási** folyamat szakaszban jelölje **be a JSON-dokumentum aláírási dokumentumát az egyiptomi adóhatóság számára**.
7. A Paraméterek **szakaszban** válassza **ki a Tanúsítvány nevét**, majd válassza ki a létrehozott digitális tanúsítvány nevét.
8. A Feldolgozási folyamat **szakaszban** válassza **az Egyiptomi ETA-szolgáltatással való integrálás lehetőséget**. Ismételje meg ezt a lépést a művelet két előfordulásával.
9. A Paraméterek **szakaszban** válassza a webszolgáltatás **URL-címét** **és bejelentkezési szolgáltatásÁNAK URL-címét**. Ezután tekintse át az URL-paramétereket. A tesztelési és termelési URL-cím [az egyiptomi adóhatóság webhelyén, az Egyiptomi e-számlázási SDK-ban megadott hivatkozás használatával olvasható](https://sdk.invoicing.eta.gov.eg/faq/).
10. Válassza a **Mentés** gombot, és zárja be az oldalt.
11. Ismételje meg a 4–10. lépést a Projektszámla **származtatott funkcióbeállítása** esetén.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Országspecifikus konfiguráció az Egyiptomi elektronikus számla (ENGEDMÉNY) alkalmazás beállításaihoz

A pénzügyi és az ellátásilánc-kezelési környezetben paramétereket kell beállítani. Ezt a beállítást két helyen lehet végrehajtani:

- Közvetlenül a Pénzügy és az Ellátásilánc-kezelés környezetben. A további tudnivalókat lásd [az Elektronikus számlázás paramétereinek beállítása.](e-invoicing-set-up-parameters.md)
- RCS-ben. Az elektronikus számlázás funkció beállításának hatókörében megadhatja az összes paramétert, majd az elektronikus számlázási funkció telepítésekor közvetlenül a pénzügyi vagy ellátásilánc-kezelési környezetbe telepítheti azokat.

Mindkét beállításban ugyanazok a paraméterek. Ha az elektronikus számlázási szolgáltatás első szolgáltatását telepíti, akkor ezeket a lépéseket követve állítsa be a paramétereket az RCS szolgáltatásban, majd telepítse a csatlakoztatott alkalmazásba.

> [!NOTE]
> Az elektronikus számlázás funkcióverziói közül néhány előre meghatározott, a Pénzügy és az Ellátásilánc-kezelés modul alkalmazásspecifikus paramétereinek készletét tartalmazhatja. Ebben az esetben ellenőriznie kell az adatok helyességét. Ellenkező esetben manuálisan állítsa be a paramétereket.

1. Az Egyiptomi elektronikus számla **(STB)** globalizációs funkció létrehozott másolatának megkeresése.
2. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
3. A **Beállítások** lapon válassza az **Alkalmazás beállítása** elemet.
4. A Kapcsolódó **alkalmazások mezőben** válassza ki azt az alkalmazást, ahová telepíteni szeretné a paramétereket.
5. Az Elektronikus dokumentumtípusok **lapon** válassza a **Hozzáadás** gombra rekord létrehozásához.
6. A Tábla **neve mezőben** adja hozzá a **CustInvoiceJour táblát**.
7. A Környezet **mezőben** adjon hozzá hivatkozást a vevői **számla** környezetének megfeleltetési nevéhez. A konfiguráció a vevői **számla környezetmodell.**
8. Az Elektronikus dokumentumok **megfeleltetése mezőben** adjon hozzá hivatkozást a vevői **számla megfeleltetésének** nevére. A konfiguráció a számlamodell **megfeleltetése**.
9. Válassza a **Mentés** lehetőséget.
10. A **Választípusok lapon** válassza a Hozzáadás **lehetőséget**.
11. A **Válasz típusa** mezőbe írja be a **Válasz** értéket.
12. A Leírás **mezőben** adja meg a Folyamat **válaszát**.
13. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
14. A Modellleképezés **mezőben** válassza a Válaszüzenet **importálása lehetőséget**. A konfiguráció Egyiptomi válaszüzenet **importálása (STB)**.
15. Válassza a **Mentés** lehetőséget.
16. Válassza a **Hozzáadás** lehetőséget.
17. A Választípus **mezőben** adja meg **a ResponseData mezőt**.
18. A Leírás **mezőbe** írja be a Folyamat válaszának **adatait**.
19. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
20. Az Adatentitás **neve** mezőben válassza **a SalesInvoiceHeaderV2Entity lehetőséget**.
21. A Modellleképezés **mezőben** válassza a Válaszadatok **importálása lehetőséget**. A konfiguráció Egyiptomi válaszadat-importálási **formátum (STB)**.
22. Válassza a **Mentés** gombot, és zárja be az oldalt.
23. Zárja be a lapot.

Ha szolgáltatást és alkalmazásbeállításokat is telepít a Pénzügyi vagy Ellátásilánc-kezeléshez kapcsolódó alkalmazásra, [akkor tekintse át a Globalizációs funkció befejezése, közzététele és telepítése lehetőséget.](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Ha engedélyezi az **Egyiptomi elektronikus számla (STB) funkciót**, akkor előfordulhat, hogy csak bizonyos adatokat kell elküldeni. Ezek az adatok tartalmazzák a szervezet adóregisztrációs azonosítóját. Az adatokat olyan külső szervezeteknek fogják továbbítani, amelyek számára az adóhatóság engedélyezte, hogy elektronikus számlákat küldjenek el az adóhatóságnak a kormányzati webszolgáltatással való integrációhoz szükséges előre meghatározott formátumban. A funkció engedélyezéséhez és letiltásához a rendszergazda a Szervezet **felügyelete –** \> **Elektronikus** \> **dokumentumparaméterek lehetőséget használhatja.** Válassza ki a **Funkciók** lapot, majd az **Egyiptomi elektronikus száma (EG)** funkciót tartalmazó sorokat, és végezze el a megfelelő kijelölést. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatokra az adatvédelmi nyilatkozatunk [vonatkozik](https://go.microsoft.com/fwlink/?LinkId=512132). A további tudnivalókat lásd az országspecifikus funkciódokumentáció "Adatvédelmi nyilatkozat" szakaszában.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázás áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az elektronikus számlázási használata során](e-invoicing-get-started.md)
- [Elektronikus vevői számlák Egyiptomban](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
