---
title: Első lépések a Franciaország elektronikus számlázási bővítményében
description: Ez a cikk a Franciaországra vonatkozó Elektronikus számlázási bővítmény első lépésekkel kapcsolatban tartalmaz tájékoztatást.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 365316b204b6d76fa6ee6b2402fefee50c8ff3ef
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220712"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Első lépések a Franciaország elektronikus számlázási bővítményében

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a cikk a Franciaországi elektronikus számlázással kapcsolatban tartalmaz tájékoztatást. Ez a varázsló végigvezeti a konfigurációs szolgáltatáson (RCS) országfüggő konfigurációs lépéseken. Ezek a lépések kiegészítik az [Első lépések modulnak az Elektronikus számlázás bővítményben leírt lépéseit](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Országspecifikus konfiguráció a francia Cho proxy pro benyújtása (FR) Elektronikus számlázás funkcióhoz

Néhány lépés szükséges a **francia Choíme Pro benyújtása (FR) Elektronikus** számlázás funkció konfigurálához. A konfiguráció néhány paramétere az alapértelmezett értékekkel lesz közzétéve. Ezeket az értékeket át kell vizsgálni és frissíteni kell, hogy jobban tükrözzék az üzleti tevékenységeket.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené a ebben a cikkben olvasható eljárásokat, teljesítsen a következő előfeltételeket:

- Ismerkedjen meg az elektronikus számlázással. A további tudnivalókat lásd [az Elektronikus számlázás modul áttekintésében](e-invoicing-service-overview.md).
- Regisztráció RCS-re, és az elektronikus számlázás beállítása. További információért tekintse át az alábbi cikkeket:

    - [Az elektronikus számlázási szolgáltatás regisztrációja és telepítése](e-invoicing-sign-up-install.md)
    - [Azure-erőforrások beállítása elektronikus számlázáshoz](e-invoicing-set-up-azure-resources.md)
    - [A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba](e-invoicing-install-add-in-microservices-lcs.md)
    - [Az Elektronikus](e-invoicing-activate-setup-integration.md) számlázás funkcióval való integráció aktiválása és beállítása – Microsoft Dynamics a jelen cikk adataival aktiválhatja a 365 Pénzügy Dynamics 365 Supply Chain Management vagy alkalmazás, illetve az Elektronikus számlázás szolgáltatás közötti integrációt.
    - [NAF-kódok és SIRET-számok](emea-fra-naf-codes-siret-numbers.md)[, NAF-kódok és SIRET-számok](tasks/fr-00003-naf-codes-siret-numbers.md) beállítása – a cikkekben található információk segítségével BEÁLLÍTHATJa a NAF-kódokat és a SIRET-számokat a jogi személyekben. 

- A szervezetet regisztrálni kell ahhoz, hogy a Chokodás Pro vállalatban működtethető legyen. A Microsoft alkalmazásprogramozási felületen (API) keresztül integrálja a Cho a Cho a Cho egy OAuth2 módban való használatát. A Cho akkori pro regisztrációval és alkalmazásaktiválással kapcsolatos részletes információk a hivatalos dokumentációban [olvashatók](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    A következő lépések szerint regisztrálhat a Cho egy pro cégnél.

    1. A regisztrációt a [PISTE portálra](https://piste.gouv.fr/en/component/apiportal/registration) ússa el. 
    2. Alkalmazás regisztrálása és a nyitott engedélyezési (OAuth) hitelesítő adatok aktiválása.
    3. Az OAuth hitelesítő adatok és a titkos kulcs ügyfél-azonosítójának másolása és mentése. Ezeket az információkat a későbbi lépésekben fogja használni.
    4. A regisztráláshoz [menjen a Cho proxyportálra](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment). 
    5. Technikai fiók létrehozása API-hozzáféréshez. A további tudnivalókat lásd [: Műszaki fiók létrehozása API-hozzáféréshez a termelésben](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. A technikai fiók felhasználói azonosítójának és a jelszónak a másolása. Ezeket az információkat a későbbi lépésekben fogja használni.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>A francia Cho guy pro submission (FR) elektronikus számlázás funkció alkalmazásbeállításának országspecifikus konfigurációja

A francia **Cho guy pro benyújtása (FR)** elektronikus számlázás funkció néhány paramétere az alapértelmezett értékekkel lesz közzétéve. Mielőtt telepíti az elektronikus számlázási szolgáltatást a szolgáltatási környezetben, szükség szerint ellenőrizze és frissítse az alapértelmezett értékeket, hogy azok jobban tükrözzék az üzleti műveleteket.

1. Az Azure kulcs kulcsában hozza létre az szolgáltatásokat és a hozzájuk tartozó hivatkozásokat. A további tudnivalókat lásd [: Vevői tanúsítványok és azok adatai](e-invoicing-customer-certificates-secrets.md).
2. Importálja a **francia Chopart Pro submission (FR)**[globalizációs funkció legújabb verzióját a globális tárházból történő importálási funkciók leírása szerint](e-invoicing-import-feature-global-repository.md).
3. Készítsen másolatot az importált globalizációs funkcióról, és válassza ki a konfigurációszolgáltatót. A további tudnivalókat lásd [a Globalizáció létrehozása funkcióval kapcsolatban](e-invoicing-create-new-globalization-feature.md).
4. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
5. A Beállítások **lap** rácsán válassza ki **az UBL értékesítési számla származtatott funkcióbeállítását**.
6. **Válassza a** Szerkesztés lehetőséget, **·** **·** **majd a Feldolgozási folyamat szakasz Feldolgozási folyamat lapján válassza az (Előnézet) Integráció a francia Cho proxyval a Francia Cho proxy** **Pro küldés műveletnévvel.**
7. A Paraméterek **szakaszban**, az **Ügyfélazonosító** titkos neve mezőben válassza ki azt a titkos nevet, amit az ügyfélazonosítóhoz létrehozott a kulcskulcsban.
8. Az Ügyfél titkos **neve mezőben** válassza ki a titkos nevet, amit a kulcskulcsban tárolt ügyféltitkhoz létrehozott.
9. A Technikai **bejelentkezési titkos név** mezőben válassza ki azt a titkos nevet, amit a technikai fiókba való bejelentkezéshez hozott létre a kulcskulcsban.
10. A Technikai **jelszó titkos neve** mezőben válassza ki azt a titkos nevet, amit a kulcshoz létrehozott a technikai fiók jelszavához.
11. A Feldolgozási **folyamat lapon**, **a** Feldolgozási folyamat szakaszban válassza **a Francia Cho proxyval** **való integrációt a Francia Cho guy pro kérési állapottal műveletnévvel**.
12. A Paraméterek **szakaszban**, az **Ügyfélazonosító** titkos neve mezőben válassza ki azt a titkos nevet, amit az ügyfélazonosítóhoz létrehozott a kulcskulcsban.
13. Az Ügyfél titkos **neve mezőben** válassza ki a titkos nevet, amit a kulcskulcsban tárolt ügyféltitkhoz létrehozott.
14. A Technikai **bejelentkezési titkos név** mezőben válassza ki azt a titkos nevet, amit a technikai fiókba való bejelentkezéshez hozott létre a kulcskulcsban.
15. A Technikai **jelszó titkos neve** mezőben válassza ki azt a titkos nevet, amit a kulcshoz létrehozott a technikai fiók jelszavához.
16. Válassza a **Mentés** gombot, majd zárja be az oldalt.
17. Ismételje meg a 6–16 **. lépést az UBL projektszámla** származtatott funkcióbeállítása, **az UBL értékesítési jóváírás származtatott** **funkcióbeállítása és az UBL projekt-jóváírás származtatott funkcióbeállítása** esetén.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázási bővítmény áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási bővítményszolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md)
