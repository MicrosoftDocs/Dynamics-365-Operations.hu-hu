---
title: Első lépések az elektronikus számlázási használata során
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Elektronikus számlázással kapcsolatos első lépéseket a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban.
author: gionoder
ms.date: 11/08/2021
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
ms.openlocfilehash: ebef9cf97f7a91e0a2fd45f5e0e0fc620070b42a
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779694"
---
# <a name="get-started-with-electronic-invoicing"></a>Első lépések az elektronikus számlázási használata során

[!include [banner](../includes/banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Elektronikus számlázással kapcsolatos első lépéseket. Ez a témakör a Regulatory Configuration Services (RCS) és a Dynamics 365 Finance általános konfigurációs lépésein vezeti végig, és az üzleti dokumentumok benyújtásához és a feldolgozás eredményeinek ellenőrzéshez szükséges lépéseket mutatja meg.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:

- Konfigurálja a Microsoft Dynamics Lifecycle Services (LCS) és a Regulatory Configuration Service (RCS) szolgáltatást, valamint a Microsoft Dynamics 365 Finance vagy a Dynamics 365 Supply Chain Management környezetet. A további tudnivalókat lásd az [Első lépések az elektronikus számlázás szolgáltatásfelügyeletének használata során](e-invoicing-get-started-service-administration.md) tartalmaz.
- Hozzon létre egy konfigurációszolgáltatót a szervezethez. További információért tekintse át az [Egy konfigurációszolgáltató létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Elektronikus számlázási funkció importálása a Microsoft konfigurációszolgáltatóból 

1. Jelentkezzen be a saját RCS-fiókjába.
2. A **Globalizációs funkciók** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. Válassza ki az **Import**, majd a **Szinkronizálás** lehetőséget.
4. Szűrje a **Konfigurációszolgáltató** oszlopot a **Microsoft** kifejezés szerint.
5. Válassza ki a táblából az elektronikus számlázás funkció nevét, majd válassza az **Importálás** lehetőséget.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Elektronikus számlázás funkció létrehozása a szervezetszolgáltató keretében

1. Az RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
2. Válassza a **Hozzáadás** > **Meglévő szolgáltatás alapján** lehetőséget, és a **Név** mezőben adja meg az Elektronikus számlázási funkció nevét.
3. A **Leírás** mezőbe írja be a funkció leírását.
4. Az **Alapfunkció** mezőben válassza ki az importált Elektronikus számlázási funkciót a Microsoft konfigurációszolgáltatóból.
5. Válassza a **Létrehozás lehetőséget**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Országspecifikus konfiguráció az elektronikus számlázási funkcióhoz

Az országtól vagy régiótól függően az Elektronikus számlázási funkció specifikus konfigurálást igényelhet. 

> [!NOTE]
> Ha Finnország esetében engedélyezi az elektronikus számlázás funkciót, akkor a keresések alkalmazásspecifikus paraméterei nem támogatottak. A probléma megoldásához tekintse át az Elektronikus jelentés modulban az értékesítési számla és a projekt **·** számlaformátumának konfigurációit. Manuálisan állítsa be a számított mezőt $PaymentMethodSubstitution hozzárendeléshez, majd kötnie kell azt a mezőt az értékesítési számla és a projekt számlaformátuma **·** Alapján **aPaymentMeansCode** mezőhöz.
>
> Ha engedélyezi az Elektronikus számlázás funkciót Olaszország számára, akkor a keresések alkalmazásspecifikus paraméterei nem támogatottak. A probléma megoldásához állítsa be kézzel az Elektronikus jelentés modulban a számított mezőt $NaturaReverseCharge **·** **·** hozzárendeléséhez.
>
> A más helyekkel kapcsolatos konkrét lépéseket lásd az adott ország vagy régió számára elérhető "Első lépések" dokumentációban.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importálja a modell-leképezési konfigurációk az elektronikus jelentéskészítésből

1. Az RCS-ben válassza ki az **Elektronikus jelentéskészítés** munkaterületet.
2. Jelölje ki a **Microsoft** konfigurációs szolgáltatók listájából az **Adattárak** lehetőséget.
3. Válassza a **Globális** lehetőséget, majd a műveletei panelen válassza a **Megnyitás** lehetőséget.
4. A modell-hozzárendelési konfigurációk importálása a következő tábla alapján funkciónév szerint.

| Funkció neve                         | Modell-leképzési konfiguráció |
|--------------------------------------|-----------------------------|
| Osztrák elektronikus számlák (AT)    | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Belga elektronikus számla (BE)      | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Brazil NF-e (BR)                  | <p>Vevői számlakontextus-modell</p><p>Pénzügyi bizonylatok</p><p>Válaszüzenet-modell</p> |
| Brazil NFS-e ABRASF Curitiba (BR) | <p>Vevői számlakontextus-modell</p><p>Pénzügyi bizonylatok</p><p>Válaszüzenet-modell</p> |
| Dán elektronikus számla (DK)       | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Egyiptomi elektronikus számla (EG)     | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p><p>Válaszüzenet-modell</p> |
| Észt elektronikus számla (EE)     | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Finn elektronikus számla (FI)       | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Francia elektronikus számla (FR)       | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Német elektronikus számla (DE)       | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| FatturaPA (IT)                       | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Mexikói CFDI Interfactura (MX)       | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p><p>Válaszüzenet-modell</p> |
| Holland elektronikus számla (NL)        | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Norvég elektronikus számla (NO)    | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Spanyol elektronikus számla (ES)      | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| PEPPOL elektronikus számla            | <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |
| Szaúd-arábiai elektronikus számla (SA)| <p>Vevői számlakontextus-modell</p><p>Számlamodell</p> |


## <a name="configure-the-application-setup"></a>Az alkalmazás beállításának konfigurálása

1. Válassza ki a létrehozott Elektronikus számlázás funkciót.
2. A **Beállítások** lapon válassza az **Alkalmazás beállítása** elemet.
3. Az **Alkalmazás csatlakoztatása** mezőben válassza ki a Finance- vagy Supply Chain Management-példányhoz társított kapcsolatot.
4. Az **Elektronikus dokumentumtípusok** szakaszban válassza a **Hozzáadás** lehetőséget.
5. Válasszon ki és adjon meg egy **Táblanév** értéket a következő táblázatnak megfelelően.

    | Funkció neve                         | Üzleti dokumentum | Tábla neve |
    |--------------------------------------|-------------------|------------|
    | Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Brazil NF-e (BR)                  | <p>Pénzügyi bizonylat</p><p>Helyesbítő levél</p> | Pénzügyi bizonylat |
    | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat | Pénzügyi bizonylat |
    | Dán elektronikus számla (DK)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Egyiptomi elektronikus számla (EG)     | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Észt elektronikus számla (EE)     | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Finn elektronikus számla (FI)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Francia elektronikus számla (FR)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Német elektronikus számla (DE)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | FatturaPA (IT)                       | <p>Értékesítési számla</p><p>Projektszámla | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Mexikói CFDI Interfactura (MX)       | <p>Értékesítési számla</p><p>Szállítólevél</p><p>Készletátvitel</p><p>Fizetéskiegészítés</p> | Vevői számlanapló |
    | Holland elektronikus számla (NL)        | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Norvég elektronikus számla (NO)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Spanyol elektronikus számla (ES)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | PEPPOL elektronikus számla            | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Szaúd-arábiai elektronikus számla (SA)| <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |

6. Minden egyes létrehozott táblanévhez válassza ki és adja meg a kontextusértéket a következő táblázatnak megfelelően.

    | Funkció neve                         | Üzleti dokumentum | Környezet |
    |--------------------------------------|-------------------|---------|
    | Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Brazil NF-e (BR)                  | <p>Pénzügyi bizonylat</p><p>Helyesbítő levél</p> | <p>Vevői számla kontextusmodell – pénzügyi bizonylat kontextusa</p><p>Vevői számla környezetmodell – FD helyesbítő levél kontextusa</p> |
    | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat| Vevői számla kontextusmodell – pénzügyi bizonylat kontextusa |
    | Dán elektronikus számla (DK)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Egyiptomi elektronikus számla (EG)     | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Észt elektronikus számla (EE)     | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Finn elektronikus számla (FI)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Francia elektronikus számla (FR)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Német elektronikus számla (DE)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | FatturaPA (IT)                       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Mexikói CFDI Interfactura (MX)       | <p>Értékesítési számla</p><p>Szállítólevél</p><p>Készletátvitel</p><p>Fizetéskiegészítés</p> | Vevői számla kontextusmodell – vevői számla kontextusa |
    | Holland elektronikus számla (NL)        | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Norvég elektronikus számla (NO)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Spanyol elektronikus számla (ES)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | PEPPOL elektronikus számla            | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Szaúd-arábiai elektronikus számla (SA)| <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |

7. Minden egyes táblanévhez és kontextushoz válasszon ki és adjon meg egy üzletidokumentum-leképezés értéket a következő táblának megfelelően.

    | Funkció neve                         | Üzleti dokumentum | Üzleti dokumentum leképezése |
    |--------------------------------------|-------------------|---------------------------|
    | Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Brazil NF-e (BR)                  | <p>Pénzügyi bizonylat</p><p>Helyesbítő levél</p> | <p>Pénzügyi bizonylat leképezése – pénzügyi bizonylatok leképezése</p><p>Pénzügyi bizonylat leképezése – helyesbítő levél leképezése</p> |
    | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat | Pénzügyi bizonylat leképezése – pénzügyi bizonylatok leképezése |
    | Dán elektronikus számla (DK)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Egyiptomi elektronikus számla (EG)     | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Észt elektronikus számla (EE)     | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Finn elektronikus számla (FI)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Francia elektronikus számla (FR)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Német elektronikus számla (DE)       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | FatturaPA (IT)                       | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Mexikói CFDI Interfactura (MX)       | <p>Értékesítési számla</p><p>Szállítólevél</p><p>Készletátvitel</p><p>Fizetéskiegészítés</p> | Számlamodell leképezése – vevői számla |
    | Holland elektronikus számla (NL)        | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Norvég elektronikus számla (NO)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Spanyol elektronikus számla (ES)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | PEPPOL elektronikus számla            | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Szaúd-arábiai elektronikus számla (SA)| <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Az alkalmazás beállításainak országspecifikus konfigurációja

Az országtól vagy régiótól függően az Alkalmazásbeállítás funkció specifikus konfigurálást igényelhet. 

Az adott lépésekről az adott ország vagy régió számára elérhető Első lépések dokumentációjában található részletes információ.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Az Elektronikus számlázás szolgáltatás telepítése szolgáltatási környezetbe

1. A **Verziók** lapon válassza ki az Elektronikus számlázási funkció telepíteni kívánt verzióját.
2. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.
3. Válassza az **Állapot módosítása** \> **Közzététel** lehetőséget.
4. Válassza a **Telepítés** lehetőséget.
5. A **Telepítés a csatlakoztatott alkalmazásra** lehetőségnél válassza az **Nem** lehetőséget.
6. A **Telepítés szolgáltatási környezetbe** lehetőségnél válassza az **Igen** lehetőséget.
7. A **Szolgáltatási környezet** mezőben válassza ki azt az Elektronikus számlázási szolgáltatási környezetet, amelybe telepíteni szeretné az Elektronikus számlázási szolgáltatást.
8. A **Kezdő dátum** mezőben azt a dátumot, amikor az Elektronikus számlázási funkciónak hatályba kell lépnie az Elektronikus számlázásban.
9. Válassza ki az **OK** lehetőséget.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Az Elektronikus számlázás szolgáltatás telepítése Csatlakoztatott alkalmazásba

1. A **Verziók** lapon válassza ki az Elektronikus számlázási funkció egy telepíteni kívánt verzióját.
2. Válassza a **Telepítés** lehetőséget.
3. A **Telepítés a csatlakoztatott alkalmazásra** lehetőségnél válassza az **Igen** lehetőséget.
4. Az **Alkalmazás csatlakoztatása** mezőben válassza ki a Finance- vagy Supply Chain Management-példányhoz társított kapcsolatot.
5. A **Telepítés szolgáltatási környezetbe** lehetőségnél válassza az **Nem** lehetőséget.
6. Válassza ki az **OK** lehetőséget.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Az Elektronikus számlázási funkció bekapcsolása a Finance vagy Supply Chain Management szolgáltatásban

1. Jelentkezzen be a Finance vagy a Supply Chain Management szolgáltatásba, és ellenőrizze, hogy a megfelelő jogi személynél van-e.
2. Menjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Elektronikus dokumentumparaméterek** lehetőségre.
3. A **Funkciók** lapon válassza ki azt az ország-/régióspecifikus funkciót, amely bekapcsolja a Finance vagy a Supply Chain Management szolgáltatás számlázási funkcióját. Az alábbi táblázat felsorolja azokat az elektronikus számlázási funkciókat, amelyek az egyes országok és régiók számára elérhetők. 

    | Funkció neve                                          | Ország/régió  |
    |-------------------------------------------------------|-----------------|
    | Osztrák elektronikus számlák (AT)                     | Ausztria         |
    | Belga elektronikus számla (BE)                       | Belgium         |
    | CFDI mexikói elektronikus számla (MX)                  | Mexikó          |
    | Dán elektronikus számla (DK)                        | Dánia         |
    | Holland elektronikus számla (NL)                         | Hollandia |
    | Egyiptomi elektronikus számla (EG)                      | Egyiptom           |
    | Észt elektronikus számla (EE)                      | Észtország         |
    | Finn elektronikus számla (FI)                       | Finnország         |
    | Francia elektronikus számla (FR)                        | Franciaország          |
    | Német elektronikus számla (DE)                        | Németország         |
    | Olasz elektronikus számla (IT)                       | Olaszország           |
    | NF-e szövetségi – brazil elektronikus számla (BR)      | Brazília          |
    | NFS-e – Brazil szolgáltatás (városi) elektronikus számla   | Brazília          |
    | Norvég elektronikus számla (NO)                     | Norvégia          |
    | PEPPOL elektronikus számla                             | Globális          |
    | Spanyol elektronikus számla (ES)                       | Spanyolország           |
    | Szaúd-arábiai elektronikus számla (SA)                 | Szaúd-Arábia    |
    

4. Válassza a **Mentés** lehetőséget.

## <a name="issue-electronic-invoices"></a>Elektronikus számlák kibocsátása

1. Menjen a **Szervezeti adminisztráció** \> **Időszakos** \> **Elektronikus dokumentumok** \> **Elektronikus dokumentumok beküldése** lehetőségre.
2. **A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.
3. Ha táblanevet szeretne hozzáadni a lekérdezésszűrőhöz, válassza a **Hozzáadás** lehetőséget.
4. Válassza ki a számlákat tartalmazó táblát.

    > [!NOTE]
    > A tábla nevének a témakör korábbi, [Az alkalmazás beállításának konfigurálása](#configure-the-application-setup) szakasz táblájában kell szerepelnie.

5. Válassza ki a lekérdezni kívánt mezőnevet a táblában.
6. Adja meg annak a feltételnek a táblanevét és mezőnevét, amely alapján a lekérdezést futtatni akarja.
7. Ha további mezőket és feltételeket szeretne hozzáadni a lekérdezéshez, ismételje meg az 5–6. lépést, majd válassza az **OK** gombot.
8. Válassza ki az **OK** lehetőséget.

## <a name="view-submission-logs"></a>Beküldési naplók megtekintése

1. Menjen a **Szervezeti adminisztráció** \> **Időszakos** \> **Elektronikus dokumentumok** \> **Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a számlákat tartalmazó táblát.

    > [!NOTE]
    > A tábla nevének a témakör korábbi, [Az alkalmazás beállításának konfigurálása](#configure-the-application-setup) szakasz táblájában kell szerepelnie.

3. Válasszon ki egy számlát a rácsban, majd válassza a **Lekérdezés** \> **Beküldési részletek** lehetőséget.

## <a name="download-an-electronic-document-file"></a>Elektronikusdokumentum-fájl letöltése

1. Menjen a **Szervezeti adminisztráció** \> **Időszakos** \> **Elektronikus dokumentumok** \> **Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a számlákat tartalmazó táblát.
3. Válasszon ki egy dokumentumot a rácsban, majd válassza az **Elektronikus dokumentum** \> **letöltése** fájlt. A program az elektronikus dokumentumfájlt tartalmazó archívumot javasolja letöltéshez.

> [!NOTE]
> Fájlok letöltése előtt be kell kapcsolva lennie az Exportálás eredménye lehetőségnek az RCS elektronikus számlázási funkcióbeállításában található kapcsolódó **·** művelet esetében.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Elektronikus számlázás áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az Brazíliára vonatkozó elektronikus számlázás használata során](e-invoicing-bra-get-started.md)
- [Első lépések a Mexikóra vonatkozó elektronikus számlázás használata során](e-invoicing-mex-get-started.md)
- [Első lépések az Olaszországra vonatkozó elektronikus számlázási használata során](e-invoicing-ita-get-started.md)
- [Elektronikus vevői számlák Egyiptomban](emea-egy-e-invoices.md)
- [Elektronikus vevői számlák Szaúd-Arábiában](emea-sau-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
