---
title: Első lépések az Elektronikus számlázásbővítménnyel
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Elektronikus számlázásbővítménnyel kapcsolatos első lépéseket a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban.
author: gionoder
manager: AnnBe
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 07954c5c96f390bc651794f8b6c61f2a1a17ab8b
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111220"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Első lépések az Elektronikus számlázásbővítménnyel

[!include [banner](../includes/banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Elektronikus számlázásbővítménnyel kapcsolatos első lépéseket.

Az alábbi táblázat felsorolja az Elektronikus számlázás funkcióit, valamint azokat az üzleti dokumentumokat, amelyekre alkalmazni lehet őket.

| Funkció neve                         | Üzleti dokumentum |
|--------------------------------------|-------------------|
| Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Brazil NF-e (BR)                  | <p>55. modell típusú pénzügyi bizonylat</p><p>Helyesbítő levél</p> |
| Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat |
| Brazil NFS-e São Paulo (BR)       | Szolgáltatási pénzügyi bizonylat |
| Dán elektronikus számla (DK)       | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Egyiptomi elektronikus számla (EG)     | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Észt elektronikus számla (EE)     | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Finn elektronikus számla (FI)       | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Francia elektronikus számla (FR)       | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Német elektronikus számla (DE)       | <p>Értékesítési számla</p><p>Projektszámla</p> |
| FatturaPA (IT)                       | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Mexikói CFDI Interfactura (MX)       | <p>Értékesítési számla</p><p>Szállítólevél</p><p>Készletátvitel</p><p>Fizetéskiegészítés</p> |
| Holland elektronikus számla (NL)        | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Norvég elektronikus számla (NO)    | <p>Értékesítési számla</p><p>Projektszámla</p> |
| Spanyol elektronikus számla (ES)      | <p>Értékesítési számla</p><p>Projektszámla</p> |
| PEPPOL elektronikus számla            | <p>Értékesítési számla</p><p>Projektszámla</p> |

## <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:

- Konfigurálja az RCS-szolgáltatást és a Microsoft Dynamics 365 Finance- vagy Dynamics 365 Supply Chain Management-környezetet úgy, hogy elküldhesse az Elektronikus számlázási bővítménybe.
- Hozzon létre szolgáltatási környezetet, és tegye közzé az Elektronikus számlázási bővítményben. A további tudnivalókat lásd az [Első lépések az elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során](e-invoicing-get-started-service-administration.md) tartalmaz.
- Hozzon létre csatlakoztatott alkalmazást. A további tudnivalókat lásd az [Első lépések az elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során](e-invoicing-get-started-service-administration.md) tartalmaz.
- Hozzon létre egy konfigurációszolgáltatót a szervezethez. További információért tekintse át a [Konfigurációszolgáltató létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Elektronikus számlázási funkció importálása a Microsoft konfigurációszolgáltatóból 

1. Jelentkezzen be a saját RCS-fiókjába.
2. Nyissa meg a **Globalizációs funkció** munkaterületet, a **Funkciók** szakaszban válassza az **e-számlázás** csempét.
3. Válassza ki az **Import**, majd a **Szinkronizálás** lehetőséget.
4. Szűrje a **Konfigurációszolgáltató** oszlopot a **Microsoft** kifejezés szerint.
5. Válassza ki az Elektronikus számlázási funkció nevét a témakör elején található táblából, majd válassza az **Importálás** lehetőséget.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Elektronikus számlázás funkció létrehozása a szervezetszolgáltató keretében

1. Az RCS-ben nyissa meg a **Globalizációs funkció** munkaterületet, és a **Funkciók** szakaszban válassza az **e-számlázás** csempét.
2. Válassza a **Hozzáadás** > **Meglévő szolgáltatás alapján** lehetőséget, és a **Név** mezőben adja meg az Elektronikus számlázási funkció nevét.
3. A **Leírás** mezőbe írja be a funkció leírását.
4. Az **Alapfunkció** mezőben válassza ki az importált Elektronikus számlázási funkciót a Microsoft konfigurációszolgáltatóból.
5. Válassza a **Létrehozás lehetőséget**.

## <a name="configure-the-electronic-invoicing-feature"></a>Az Elektronikus számlázási funkció konfigurálása

Az országtól vagy régiótól függően az Elektronikus számlázási funkció további konfigurálást igényelhet. Az adott lépésekről az adott ország vagy régió számára elérhető Első lépések dokumentációjában található részletes információ.

## <a name="configure-the-application-setup"></a>Az alkalmazás beállításának konfigurálása

1. Válassza ki a létrehozott Elektronikus számlázás funkciót.
2. A **Verzió** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
3. A **Beállítások** lapon válassza az **Alkalmazás beállítása** elemet.

    > [!NOTE]
    > Ellenőrizze, hogy a szervezet be van-e állítva **Aktív** konfigurációszolgáltatóként. További információért tekintse át a [Konfigurációszolgáltató létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

4. Válassza a **Funkció beállítása** lehetőséget, majd a **Csatlakoztatott alkalmazás** elemet.
5. Az **Elektronikus dokumentumtípusok** szakaszban válassza a **Hozzáadás** lehetőséget.
6. A funkció által támogatott minden egyes üzleti dokumentumhoz válasszon ki és adjon meg egy **Táblanév** értéket a következő táblázatnak megfelelően.

    | Funkció neve                         | Üzleti dokumentum | Tábla neve |
    |--------------------------------------|-------------------|------------|
    | Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számlanapló</p><p>Projektszámla</p> |
    | Brazil NF-e (BR)                  | <p>Pénzügyi bizonylat</p><p>Helyesbítő levél</p> | Pénzügyi bizonylat |
    | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat | Pénzügyi bizonylat |
    | Brazil NFS-e São Paulo (BR)       | Szolgáltatási pénzügyi bizonylat | Pénzügyi bizonylat |
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

7. A funkció által támogatott minden egyes üzleti dokumentumhoz válasszon ki és adjon meg egy **Kontextus** értéket a következő táblázatnak megfelelően.

    | Funkció neve                         | Üzleti dokumentum | Környezet |
    |--------------------------------------|-------------------|---------|
    | Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Vevői számla kontextusmodell – vevői számla kontextusa</p><p>Vevői számla kontextusmodell – projektszámla kontextusa</p> |
    | Brazil NF-e (BR)                  | <p>Pénzügyi bizonylat</p><p>Helyesbítő levél</p> | <p>Vevői számla kontextusmodell – pénzügyi bizonylat kontextusa</p><p>Vevői számla környezetmodell – FD helyesbítő levél kontextusa</p> |
    | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat| Vevői számla kontextusmodell – pénzügyi bizonylat kontextusa |
    | Brazil NFS-e São Paulo (BR)       | Szolgáltatási pénzügyi bizonylat| Vevői számla kontextusmodell – pénzügyi bizonylat kontextusa |
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

8. A funkció által támogatott minden egyes üzleti dokumentumhoz válasszon ki és adjon meg egy **Üzleti dokumentum leképezése** értéket a következő táblázatnak megfelelően.

    | Funkció neve                         | Üzleti dokumentum | Üzleti dokumentum leképezése |
    |--------------------------------------|-------------------|---------------------------|
    | Osztrák elektronikus számlák (AT)    | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Belga elektronikus számla (BE)      | <p>Értékesítési számla</p><p>Projektszámla</p> | <p>Számlamodell leképezése – vevői számla</p><p>Számlamodell leképezése – projektszámla</p> |
    | Brazil NF-e (BR)                  | <p>Pénzügyi bizonylat</p><p>Helyesbítő levél</p> | <p>Pénzügyi bizonylat leképezése – pénzügyi bizonylatok leképezése</p><p>Pénzügyi bizonylat leképezése – helyesbítő levél leképezése</p> |
    | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylat | Pénzügyi bizonylat leképezése – pénzügyi bizonylatok leképezése |
    | Brazil NFS-e São Paulo (BR)       | Szolgáltatási pénzügyi bizonylat | Pénzügyi bizonylat leképezése – pénzügyi bizonylatok leképezése |
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

Az országtól vagy régiótól függően az Elektronikus számlázási funkció további konfigurálást igényelhet. Az adott lépésekről az adott ország vagy régió számára elérhető Első lépések dokumentációjában található részletes információ.

## <a name="deploy-the-electronic-invoicing-feature"></a>Az Elektronikus számlázási funkció telepítése

1. A **Verziók** lapon válassza ki az Elektronikus számlázási funkció telepíteni kívánt verzióját.
2. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.
3. Válassza az **Állapot módosítása** \> **Közzététel** lehetőséget.
4. Válassza a **Telepítés** lehetőséget.
5. A **Telepítés a csatlakoztatott alkalmazásra** lehetőségnél válassza az **Igen** lehetőséget.
6. Az **Alkalmazás csatlakoztatása** oldalon válassza ki a Finance- vagy Supply Chain Management-példányhoz társított kapcsolatot.
7. A **Telepítés szolgáltatási környezetbe** lehetőségnél válassza az **Igen** lehetőséget.
8. A **Szolgáltatási környezet** mezőben válassza ki azt az Elektronikus számlázási szolgáltatási környezetet, amelybe telepíteni szeretné az Elektronikus számlázási szolgáltatást.
9. A **Kezdő dátum** mezőben azt a dátumot, amikor az Elektronikus számlázási funkciónak hatályba kell lépnie az Elektronikus számlázási bővítményben.
10. Válassza ki az **OK** lehetőséget.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Az Elektronikus számlázási funkció bekapcsolása a Finance vagy Supply Chain Management szolgáltatásban

1. Jelentkezzen be a Finance vagy a Supply Chain Management szolgáltatásba, és ellenőrizze, hogy a megfelelő jogi személynél van-e.
2. Menjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Elektronikus dokumentumparaméterek** lehetőségre.
3. A **Funkciók** lapon válassza ki az alábbi táblázatban felsorolt funkcióhivatkozás(oka)t, és ezzel bekapcsolhatja a Finance vagy a Supply Chain Management Elektronikus számlázási funkcióját.

    | Funkció neve                         | Ország/régió  | Funkcióra mutató hivatkozás |
    |--------------------------------------|-----------------|-------------------|
    | Osztrák elektronikus számlák (AT)    | Ausztria         | EUR-00023 |
    | Belga elektronikus számla (BE)      | Belgium         | EUR-00023 |
    | Brazil NF-e (BR)                  | Brazília          | BR-00053 |
    | Brazil NFS-e ABRASF Curitiba (BR) | Brazília          | BR-00095 |
    | Brazil NFS-e São Paulo (BR)       | Brazília          | BR-00095 |
    | Dán elektronikus számla (DK)       | Dánia         | <p>EUR-00023</p><p>DK-00001</p> |
    | Holland elektronikus számla (NL)        | Hollandia | EUR-00023 |
    | Egyiptomi elektronikus számla (EG)     | Egyiptom           | EG-00008 |
    | Észt elektronikus számla (EE)     | Észtország         | EUR-00023 |
    | Finn elektronikus számla (FI)      | Finnország         | EUR-00023 |
     Francia elektronikus számla (FR)       | Franciaország           | EUR-00023 |
    | Német elektronikus számla (DE)       | Németország         | EUR-00023 |
    | Mexikói CFDI Interfactura (MX)       | Mexikó          | <p>MX-00010</p><p>MX-00016</p> |
    | Norvég elektronikus számla (NO)    | Norvégia          | <p>EUR-00023</p><p>NO-00010</p> |
    | Spanyol elektronikus számla (ES)      | Spanyolország           | <p>EUR-00023</p><p>ES-00025</p> |
    | Olasz elektronikus számla (IT)      | Olaszország           | <p>EUR-00023</p><p>IT-00036</p> |
    | PEPPOL elektronikus számla            | Európa          | EUR-00023 |

4. Válassza a **Mentés** lehetőséget.

## <a name="issue-electronic-invoices"></a>Elektronikus számlák kibocsátása

1. Menjen a **Szervezeti adminisztráció** \> **Időszakos** \> **Elektronikus dokumentumok** \> **Elektronikus dokumentumok beküldése** lehetőségre.
2. A **Szerepeltetni kívánt rekord** gyorslapon válassza a **Szűrő** elemet.
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

Az országtól vagy régiótól függően az Elektronikus számlázási funkció további konfigurálást igényelhet. Az adott lépésekről az adott ország vagy régió számára elérhető Első lépések dokumentációjában található részletes információ.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Elektronikus számlázási bővítmény áttekintése](e-invoicing-service-overview.md)
- [Első lépések a brazil Elektronikus számlázásbővítménnyel](e-invoicing-bra-get-started.md)
- [Első lépések a mexikói Elektronikus számlázásbővítménnyel](e-invoicing-mex-get-started.md)
- [Első lépések az olasz Elektronikus számlázásbővítménnyel](e-invoicing-ita-get-started.md)
- [Elektronikus vevői számlák Egyiptomban](emea-egy-e-invoices.md)
