---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Finance szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Finance alkalmazásban.
author: roschlom
manager: AnnBe
ms.date: 02/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 14428491383883c1fc2a8cdcd1975e1f1cb71b40
ms.sourcegitcommit: e9d19f25e64cf4d1c1d07c8031a7081454a6f79e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/18/2021
ms.locfileid: "5474063"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Finance szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Finance alkalmazásban.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://docs.microsoft.com/dynamics/s-e/global/axtechrefrep_61) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.17 kiadásában

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>LCS-adattár tárolási beállításként Elektronikus jelentéskészítési konfigurációkhoz

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lecserélve az új Regulatory Configuration Service (RCS) globális adattárra |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Dynamics 365 Finance-, Supply Chain Management- és Project Operations-termékek|
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: Úgy tervezzük, hogy 2022. április 1. után már nem támogatjuk a Microsoft Dynamics Lifecycle Services (LCS) adattárat tárolási lehetőségként Elektronikus jelentéskészítési (ER) konfigurációk számára. A rendszer az új Microsoft ER-konfigurációkat kizárólag a globális adattárból való letöltésre teszi közzé. A globális adattárat Dynamics 365-termékekből és az RCS-rendszerből érheti el. További információ: [ER-konfigurációk importálása RCS-ből](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.16 kiadásában

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Áfabevallás (CZ) és Ellenőrzési nyilatkozat exportálása (CZ) elektronikus jelentési formátumok a Cseh Köztársaság számára

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új formátumokra cserélve |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: azt tervezzük, hogy 2022. január 22. után megszüntetjük az Áfabevallás (CZ) és Ellenőrzési nyilatkozat exportálása (CZ) elektronikus jelentési formátumok támogatását. Az új Áfabevallás XML (CZ), Áfabevallás Excel (CZ) és Áfa-ellenőrzési nyilatkozat exportálása XML (CZ) elektronikus jelentési formátumokat vezetjük be az Áfabevallási modell alatt. |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>„Főkönyvi tranzakció exportálási formátuma (BE)” elektronikus jelentési formátum és a megfelelő „Főkönyvi tranzakció exportálása (BE)” modell Belgium számára

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A „Standard vizsgálati fájl (SAF-T)” modellt tartalmazó új formátum váltotta fel.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. december 1-jén azt tervezzük, hogy tovább nem támogatjuk a „Főkönyvi tranzakció exportálási formátumát (BE)” elektronikus jelentési formátumát és a megfelelő „Főkönyvi tranzakció exportálása (BE)” modellt. A „Standard könyvvizsgálati fájl (SAF-T)” modell helyett az új „Főkönyv adatexportálás (BE)” formátum és az „Általános főkönyv-adatmodell-leképezése” lesz. |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>„VAT 100” jelentés Egyesült Királyság-beli SSRS formátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új ER formátummal helyettesítve – „Áfabevallás Excel (UK)” formátum az „Áfabevallási modell” alatt.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. december 1-jétől azt tervezzük, hogy már nem támogatjuk a „VAT 100-jelentést” az SSRS formátumban. Egy új „Adóbevallás–Excel (UK)” formátum került be az „Áfabevallási modell” alatt az [MTD ÁFA funkció](../localizations/emea-gbr-mtd-vat-integration.md) lehetőségbe. |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.15 kiadásában

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2020 decemberétől hatályos Microsoft Internet Explorer 11 támogatás az összes Dynamics 365 termékre elavulttá válik, ezért az Internet Explorer 11 nem lesz támogatott 2021. augusztus után.<br><br>Ez hatással lesz azokra, akik Dynamics 365 termékeket használnak, amelyeket a Internet Explorer 11 interfészen való használatra terveztek. 2021. augusztus után az Internet Explorer 11 nem lesz támogatott az ilyen Dynamics 365 termékek esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Az összes Dynamics 365 termék |
| **Telepítési beállítás**              | Összes|
| **Állapot**                         | Elavult. Az Internet Explorer 11 támogatottsága 2021. augusztus után megszűnik.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.12 kiadásában

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Lengyel SSRS-jelentések: Kimeneti áfajegyzék, Beszerzési áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Jogi okból nem szükséges.  |
| **Felváltotta másik szolgáltatás?**   | Igen (Az alapértelmezett ellenőrzési fájlok Excel-formátumban, áfabevallással-JPK_VDEK) |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. július 1-től már nem tervezzük az SSRS-jelentések támogatását **Kimeneti áfajegyék, Bemeneti áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014**. A (JPK_VDEK) alapértelmezett ellenőrzési fájljához tartozó Excel formátumú példa lesz bevezetve. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.11 kiadásában

### <a name="norwegian-standard-main-accounts"></a>Norvég standard főszámlák

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Újratervezés  |
| **Felváltotta másik szolgáltatás?**   | Igen (ER-formátumú alkalmazás-specifikus paraméterekkel felülírva) |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. április 1-től már nem tervezzük támogatni a szabványos fő számlákhoz kapcsolódó funkciókat: hivatkozási mező, kapcsolódó tábla, adatentitás. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.7 kiadásában

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A csoportfiók kiválasztásához tartozó funkció módosult.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Munkafolyamat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2020. december 1-túl a program nem támogatja a kínai bizonylattípus-beállításokat a Számalcsoportok kiválasztása nélkül. További részleteket az új kialakításról lásd: [A 10.0.7 újdonságai](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
