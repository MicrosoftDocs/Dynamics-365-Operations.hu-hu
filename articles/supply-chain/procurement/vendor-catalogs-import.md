---
title: Szállítói katalógusok importálása
description: Ez a témakör leírja a szállítói katalógus adatainak importálása folyamatot.
author: mkirknel
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 7ed2c50b28fdbd1baf4caa0a8a7f2f05d6a53fd6
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429939"
---
# <a name="import-vendor-catalogs"></a>Szállítói katalógusok importálása

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Szállítói katalógusok importálása

A Dynamics 365 Supply Chain Management alkalmazás segítségével a beszerzési szakemberek katalógusokat hozhatnak létre és karbantarthatják azokat, amelyeket a vállalati alkalmazottak használhatnak, ha cikkeket és szolgáltatásokat rendelnek belső használatra. Beszerzési katalógus létrehozásához lehetőség van a kívánt cikkeket vagy szolgáltatásokat hozzáadni, amelyeket szeretne elérhetővé tenni az alkalmazottaknak, vagy a termékkatalógus-adatok importálásával, vagy a termék katalógusadatok manuális hozzáadásával az alaptermékhez. 

A Microsoft Dynamics 365 ügyfélből származó, a szállító által elküldött katalógus adatok feltölthetők.

A termékadatoknak, amelyeket egy szállító ad át egy katalógus-karbantartási kérelem (CRM) fájl formájában, XML-formátumban kell lenniük. A CRM-fájlnak tartalmaznia kell a részletes adatait a terméknek, amely a szállító szállít a vállalatának.

## <a name="import-vendor-catalog-data"></a>Szállítói katalógusok adatainak importálása

Egy szállító katalógusadatainak importálásához végezze el a következő feladatokat:

1. Projekt beállítása az adatok kezelése munkaterületen, ahol hozzárendelési szabályainak adta meg. Válassza ki az **Adatkezelés**, majd az **Szerepek beállítása adatprojektekhez** elemet.

2. Állítsa be a beszerzési kategóriák hierarchiáját, és rendelje a szállítókat beszerzési kategóriákhoz. Árucikk-kódok használatakor az árucikk-kódokat adja a beszerzési kategóriákhoz. Beszerzési kategóriahierarchia beállításával kapcsolatos további tudnivalókat lásd: [Beszerzési kategóriák hierarchiájának beállítása](../procurement/tasks/set-up-procurement-category-hierarchy.md).

3. Konfigurálja a szállítót katalógus importálásához. Válasszon ki egy szállítót, és válassza a **Beszerzés** > **Beállítás** > **Szállító konfigurálása katalógus importálásához** elemet.

4. Hajtsa végre: munkafolyamat konfigurálása katalógus importálásához. Hozzon létre egy CMR-fájlsablon és ossza meg a szállítóval.

5. Válassza a **Beszerzés és forrás** \> **Közös** \> **Katalógusok** \> **Szállítói katalógusok** elemet szállítói katalógus létrehozásához. A katalógus karbantartási kérelem (CRM) fájlok, amelyeket a szállítótól kapott, ebben a katalógusban vannak csoportosítva. 

6. Töltse fel a CMR-fájlt.

7. Tekintse át, hagyja jóvá vagy utasítsa el a szállítói katalógusban szereplő termékeket. A termékek automatikusan vannak hozzárendelve a beszerzési kategóriákhoz. 

A jóváhagyott termékek felvehetők az alaptermékbe, és kiadhatók a kiválasztott jogi személyeknek. Csak jóváhagyott termékek adhatók hozzá a beszerzési katalógushoz.

## <a name="generate-a-catalog-import-file-template"></a>Katalógusimportálási fájlsablon létrehozása

A katalógusimportálási fájlsablon egy XSD-fájl, amely egy szállító termékeihez tartozó CMR-fájl létrehozásához használható. A CMR-fájlt új katalógus létrehozására, illetve meglévő katalógus cseréjére vagy módosítására is használhatja.

1. Válassza a **Beszerzés és forrás** \> **Katalógusok** \> **Szállítói katalógusok** elemet, és kattintson duplán a használni kívánt katalógusra.

2. Töltse le az aktuális katalógus importálási sablonját (XSD-fájl). Itt: **Katalógus módosítása** oldal, **Műveleti ablak**, **Katalógusok** lap, **Kapcsolódó információk** csoport, kattintson a **Katalógussablon előállítása** elemre, és válassza ki a **Beszerzési kategória** elemet.

    - A **Beszerzési kategória** lehetőséggel olyan katalógussablon generálható, amely tartalmazza azokat a beszerzési kategóriákat, amelyekben a szállító jogosult termékeket kínálni.

3. A **Mentés másként** párbeszédpanelen válassza ki azt a helyet, ahol a katalógusfájl-sablont tárolni szeretné, és mentse a fájlt.

További tájékoztatás és példák ebben a blogbejegyzésben: [Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/) szállítói katalógusok.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]