---
title: Eltávolított vagy elavult szolgáltatások a Dynamics 365 Finance alkalmazásban
description: Ez a témakör olyan funkciókat ismertet, amelyek el vannak távolítva, illetve amelyek a Dynamics 365 Pénzügy rendszerből való eltávolításra tervezve vannak.
author: kfend
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 0278b57ccfa2da9dba6b5ea77821fdc47ad2d078
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846654"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Eltávolított vagy elavult szolgáltatások a Dynamics 365 Finance alkalmazásban

[!include [banner](../includes/banner.md)]

Ez a témakör olyan funkciókat ismertet, amelyek el vannak távolítva, illetve amelyek a Dynamics 365 Pénzügy rendszerből való eltávolításra tervezve vannak.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Pénzügy és művelet alkalmazások objektumaival kapcsolatos részletes információk a Műszaki hivatkozási [jelentésekben találhatók](/dynamics/s-e/global/axtechrefrep_61). Ezeknek a jelentéseknek a különböző verzióit össze lehet hasonlítani, hogy megismerjük a Pénzügyi és műveleti alkalmazások egyes verzióiban módosult vagy eltávolított objektumokat.

## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.26 kiadásában

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Áfajelentés Finnországhoz (terv a jelentési kódok alapján)

[Áfajelentés Finnországhoz](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve a Finnországra vonatkozó új áfabevallási tervvel, [áfabevallással](../localizations/emea-fin-vat-declaration.md). |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Alkalmazás |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: 2023. március 1-jével úgy tervezjük, hogy a továbbiakban nem lesz támogatva a Finnország áfajelentése (finn jelentéselrendezés). Az adóbevallási **modellben új áfabevallási TXT** **és áfabevallási Excel (FI)** elektronikus jelentési formátumok (**ER)** találhatók. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.24 kiadásában

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Áfajelentés Svédországhoz (terv jelentési kódok alapján)

[Áfajelentés Svédországhoz](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve Svédországra vonatkozó új áfabevallási tervvel, [áfabevallással](../localizations/emea-swe-vat-declaration-sweden.md) |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Alkalmazás |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: 2022. december 1-jéig úgy tervezjük, hogy a továbbiakban nem lesz támogatva a Svéd Áfajelentés (svéd jelentéselrendezés). Az adóbevallási **modellben új ÁFAbevallási XML- (SE**) **és áfabevallási Excel -formátumok (SE)** **formátumok** bevezetettek. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Áfabevallás Ausztriában (jelentési kódokon alapuló terv)

[Áfabevallás részletei Ausztriához](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve egy új áfabevallási tervvel, [áfabevallással Ausztriában](../localizations/emea-aut-vat-declaration-austria.md) |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Alkalmazás |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: 2022. december 1-éig azt terveztük, **hogy az áfabevallási modellen már nem lesz támogatva az elektronikus bevallási (AT)** **formátum**. Az **adóbevallási modellben új ÁFAbevallási XML** **- és áfabevallási Excel-formátumok (AT)** **is bevezethetők**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>ELSTER nyilatkozat Németország számára (terv a jelentési kódok alapján)

[Áfakimutatás](../localizations/emea-de-vat-declaration.md)</br>
[Elektronikus adóbevallás beállítása Németország számára](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[Elektronikus áfabevallás (ELSTER) továbbítása](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve egy új áfabevallási tervre, [egy németországi áfabevallásra](../localizations/emea-deu-vat-declaration-germany.md) |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Alkalmazás |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: 2022 **. december 1-jére már nem terveztük az Elster (DE)** **és az Elster elektronikus** jelentés (ER) formátumok támogatását. Az **adóbevallási modellben új ÁFAbevallási XML** **- és áfabevallási Excel-formátumok (DE)** **is bevezethetők**. |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>Holland ob-nyilatkozat (jelentéskódok alapján terv)

[Ob nyilatkozat](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve a holland áfabevallás új tervére, [áfabevallásra](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Alkalmazás |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: 2022. december 1-éig azt tervezjük, **hogy a továbbiakban nem lesz támogatva az OB nyilatkozat (NL)** **és a OB nyilatkozatmodell** elektronikus jelentési (ER) formátuma. Az **adóbevallási modellben új ÁFAbevallási XML** **- és áfabevallási Excel-formátumok (NL)** **is bevezetett**. |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.20 kiadásában

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>"RTIR lekérdezési számlaadat-kérelem (HU)" Elektronikus jelentéskészítés (ER) formátumkonfiguráció

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Kizárva az elektronikus üzenetkezelés feldolgozásból a magyarországi online számlázási rendszerrel történő együttműködésből |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2022. április 15-re már nem lesz támogatva az „RTIR lekérdezési számlaadat-kérelem (HU)” formátumkonfiguráció. |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>"Francia FEC ellenőrzési fájl" Elektronikus jelentési (ER) formátum Franciaország számára "Német audit fájlkimenet" formátumban

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Helyébe az új "FEC auditfájl (FR)" formátum lép |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2022. május 1-től nem tervezzük támogatni a "francia FEC auditfájl" elektronikus jelentési (ER) formátumot Franciaország számára "Német ellenőrzési fájlkimenet" formátumban. Ehelyett az "Adatexport modell" alatt új FEC auditfájl (FR) formátum kerül bevezetésre. |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.17 kiadásában

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>LCS-adattár tárolási beállításként Elektronikus jelentéskészítési konfigurációkhoz

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve az új Regulatory Configuration Service (RCS) globális adattárra |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Dynamics 365 Pénzügy, Ellátásilánc-kezelés és Projektművelet termékek|
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: Úgy tervezzük, hogy 2022. április 1. után már nem támogatjuk a Microsoft Dynamics Lifecycle Services (LCS) adattárat tárolási lehetőségként Elektronikus jelentéskészítési (ER) konfigurációk számára. A rendszer az új Microsoft ER-konfigurációkat kizárólag a globális adattárból való letöltésre teszi közzé. A globális adattárat Dynamics 365-termékekből és az RCS-rendszerből érheti el. További tájékoztatás: [ER-konfigurációk importálása az RCS-ből](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) és a [Regulatory Configuration Service - Lifecycle Services tárolás kivezetése](../localizations/rcs-lcs-repo-dep-faq.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.16 kiadásában

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Áfabevallás (CZ) és Ellenőrzési nyilatkozat exportálása (CZ) elektronikus jelentési formátumok a Cseh Köztársaság számára

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új formátumokra cserélve |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: azt tervezzük, hogy 2022. január 22. után megszüntetjük az Áfabevallás (CZ) és Ellenőrzési nyilatkozat exportálása (CZ) elektronikus jelentési formátumok támogatását. Az új Áfabevallás XML (CZ), Áfabevallás Excel (CZ) és Áfa-ellenőrzési nyilatkozat exportálása XML (CZ) elektronikus jelentési formátumokat vezetjük be az Áfabevallási modell alatt. |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>„Főkönyvi tranzakció exportálási formátuma (BE)” elektronikus jelentési formátum és a megfelelő „Főkönyvi tranzakció exportálása (BE)” modell Belgium számára

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A „Standard vizsgálati fájl (SAF-T)” modellt tartalmazó új formátum váltotta fel.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. december 1-jén azt tervezzük, hogy tovább nem támogatjuk a „Főkönyvi tranzakció exportálási formátumát (BE)” elektronikus jelentési formátumát és a megfelelő „Főkönyvi tranzakció exportálása (BE)” modellt. A „Standard könyvvizsgálati fájl (SAF-T)” modell helyett az új „Főkönyv adatexportálás (BE)” formátum és az „Általános főkönyv-adatmodell-leképezése” lesz. |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>„VAT 100” jelentés Egyesült Királyság-beli SSRS formátum

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új ER formátummal helyettesítve – „Áfabevallás Excel (UK)” formátum az „Áfabevallási modell” alatt.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. december 1-jétől azt tervezzük, hogy már nem támogatjuk a „VAT 100-jelentést” az SSRS formátumban. Egy új „Adóbevallás–Excel (UK)” formátum került be az „Áfabevallási modell” alatt az [MTD ÁFA funkció](../localizations/emea-gbr-mtd-vat-integration.md) lehetőségbe. |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.15 kiadásában

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2020 decemberétől hatályos Microsoft Internet Explorer 11 támogatás az összes Dynamics 365 termékre elavulttá válik, ezért az Internet Explorer 11 nem lesz támogatott 2021. augusztus után.<br><br>Ez hatással lesz azokra, akik Dynamics 365 termékeket használnak, amelyeket a Internet Explorer 11 interfészen való használatra terveztek. 2021. augusztus után az Internet Explorer 11 nem lesz támogatott az ilyen Dynamics 365 termékek esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Az összes Dynamics 365 termék |
| **Telepítési beállítás**              | Összes|
| **Állapot**                         | Elavult. Az Internet Explorer 11 támogatottsága 2021. augusztus után megszűnik.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.12 kiadásában

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Nem lett avultatva: Lengyel SSRS-jelentések: Kimeneti áfajegyzék, Beszerzési áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Jogi okból nem szükséges.  |
| **Felváltotta másik szolgáltatás?**   | Igen (Az alapértelmezett ellenőrzési fájlok Excel-formátumban, áfabevallással-JPK_VDEK) |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Nem lett avultatva: 2021. április 27-től tervezzük az SSRS-jelentések támogatását **Kimeneti áfajegyék, Bemeneti áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014**. A (JPK_VDEK) alapértelmezett ellenőrzési fájljához tartozó Excel formátumú példa lett bevezetve. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.11 kiadásában

### <a name="norwegian-standard-main-accounts"></a>Norvég standard főszámlák

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Újratervezés  |
| **Felváltotta másik szolgáltatás?**   | Igen (ER-formátumú alkalmazás-specifikus paraméterekkel felülírva) |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. április 1-től már nem tervezzük támogatni a szabványos fő számlákhoz kapcsolódó funkciókat: hivatkozási mező, kapcsolódó tábla, adatentitás. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.7 kiadásában

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A csoportfiók kiválasztásához tartozó funkció módosult.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Munkafolyamat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2020. december 1-túl a program nem támogatja a kínai bizonylattípus-beállításokat a Számalcsoportok kiválasztása nélkül. További részleteket az új kialakításról lásd: [A 10.0.7 újdonságai](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
