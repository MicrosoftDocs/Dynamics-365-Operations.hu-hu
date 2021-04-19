---
title: Szállítói katalógusok importálása
description: Ez a témakör leírja a szállítói katalógus adatainak importálása folyamatot.
author: kamaybac
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: dabourq
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: ee709d72098b4304cf7748cae1a328736fa16188
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825230"
---
# <a name="import-vendor-catalogs"></a><span data-ttu-id="46f33-103">Szállítói katalógusok importálása</span><span class="sxs-lookup"><span data-stu-id="46f33-103">Import vendor catalogs</span></span>

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="46f33-104">Szállítói katalógusok importálása</span><span class="sxs-lookup"><span data-stu-id="46f33-104">Vendor catalogs import</span></span>

<span data-ttu-id="46f33-105">A Dynamics 365 Supply Chain Management alkalmazás segítségével a beszerzési szakemberek katalógusokat hozhatnak létre és karbantarthatják azokat, amelyeket a vállalati alkalmazottak használhatnak, ha cikkeket és szolgáltatásokat rendelnek belső használatra.</span><span class="sxs-lookup"><span data-stu-id="46f33-105">In Dynamics 365 Supply Chain Management, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="46f33-106">Beszerzési katalógus létrehozásához lehetőség van a kívánt cikkeket vagy szolgáltatásokat hozzáadni, amelyeket szeretne elérhetővé tenni az alkalmazottaknak, vagy a termékkatalógus-adatok importálásával, vagy a termék katalógusadatok manuális hozzáadásával az alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="46f33-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="46f33-107">A Microsoft Dynamics 365 ügyfélből származó, a szállító által elküldött katalógus adatok feltölthetők.</span><span class="sxs-lookup"><span data-stu-id="46f33-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="46f33-108">A termékadatoknak, amelyeket egy szállító ad át egy katalógus-karbantartási kérelem (CRM) fájl formájában, XML-formátumban kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="46f33-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="46f33-109">A CRM-fájlnak tartalmaznia kell a részletes adatait a terméknek, amely a szállító szállít a vállalatának.</span><span class="sxs-lookup"><span data-stu-id="46f33-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>

## <a name="import-vendor-catalog-data"></a><span data-ttu-id="46f33-110">Szállítói katalógusok adatainak importálása</span><span class="sxs-lookup"><span data-stu-id="46f33-110">Import vendor catalog data</span></span>

<span data-ttu-id="46f33-111">Egy szállító katalógusadatainak importálásához végezze el a következő feladatokat:</span><span class="sxs-lookup"><span data-stu-id="46f33-111">To import vendor catalog data, you must complete the following tasks:</span></span>

1. <span data-ttu-id="46f33-112">Projekt beállítása az adatok kezelése munkaterületen, ahol hozzárendelési szabályainak adta meg.</span><span class="sxs-lookup"><span data-stu-id="46f33-112">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="46f33-113">Válassza ki az **Adatkezelés**, majd az **Szerepek beállítása adatprojektekhez** elemet.</span><span class="sxs-lookup"><span data-stu-id="46f33-113">Select **Data management** and then select **Set up roles for data projects**.</span></span>

2. <span data-ttu-id="46f33-114">Állítsa be a beszerzési kategóriák hierarchiáját, és rendelje a szállítókat beszerzési kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="46f33-114">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="46f33-115">Árucikk-kódok használatakor az árucikk-kódokat adja a beszerzési kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="46f33-115">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="46f33-116">Beszerzési kategóriahierarchia beállításával kapcsolatos további tudnivalókat lásd: [Beszerzési kategóriák hierarchiájának beállítása](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="46f33-116">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>

3. <span data-ttu-id="46f33-117">Konfigurálja a szállítót katalógus importálásához.</span><span class="sxs-lookup"><span data-stu-id="46f33-117">Configure the vendor for catalog import.</span></span> <span data-ttu-id="46f33-118">Válasszon ki egy szállítót, és válassza a **Beszerzés** > **Beállítás** > **Szállító konfigurálása katalógus importálásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="46f33-118">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>

4. <span data-ttu-id="46f33-119">Hajtsa végre: munkafolyamat konfigurálása katalógus importálásához.</span><span class="sxs-lookup"><span data-stu-id="46f33-119">Configure workflow for catalog import.</span></span> <span data-ttu-id="46f33-120">Hozzon létre egy CMR-fájlsablon és ossza meg a szállítóval.</span><span class="sxs-lookup"><span data-stu-id="46f33-120">Create a CMR file template and share this with your vendor.</span></span>

5. <span data-ttu-id="46f33-121">Válassza a **Beszerzés és forrás** \> **Közös** \> **Katalógusok** \> **Szállítói katalógusok** elemet szállítói katalógus létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="46f33-121">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="46f33-122">A katalógus karbantartási kérelem (CRM) fájlok, amelyeket a szállítótól kapott, ebben a katalógusban vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="46f33-122">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6. <span data-ttu-id="46f33-123">Töltse fel a CMR-fájlt.</span><span class="sxs-lookup"><span data-stu-id="46f33-123">Upload the CMR file.</span></span>

7. <span data-ttu-id="46f33-124">Tekintse át, hagyja jóvá vagy utasítsa el a szállítói katalógusban szereplő termékeket.</span><span class="sxs-lookup"><span data-stu-id="46f33-124">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="46f33-125">A termékek automatikusan vannak hozzárendelve a beszerzési kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="46f33-125">The products are automatically mapped to the procurement categories.</span></span> 

<span data-ttu-id="46f33-126">A jóváhagyott termékek felvehetők az alaptermékbe, és kiadhatók a kiválasztott jogi személyeknek.</span><span class="sxs-lookup"><span data-stu-id="46f33-126">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="46f33-127">Csak jóváhagyott termékek adhatók hozzá a beszerzési katalógushoz.</span><span class="sxs-lookup"><span data-stu-id="46f33-127">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="46f33-128">Katalógusimportálási fájlsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="46f33-128">Generate a catalog import file template</span></span>

<span data-ttu-id="46f33-129">A katalógusimportálási fájlsablon egy XSD-fájl, amely egy szállító termékeihez tartozó CMR-fájl létrehozásához használható.</span><span class="sxs-lookup"><span data-stu-id="46f33-129">The catalog import file template is an XSD file that you use to create a CMR file for a vendor's products.</span></span> <span data-ttu-id="46f33-130">A CMR-fájlt új katalógus létrehozására, illetve meglévő katalógus cseréjére vagy módosítására is használhatja.</span><span class="sxs-lookup"><span data-stu-id="46f33-130">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1. <span data-ttu-id="46f33-131">Válassza a **Beszerzés és forrás** \> **Katalógusok** \> **Szállítói katalógusok** elemet, és kattintson duplán a használni kívánt katalógusra.</span><span class="sxs-lookup"><span data-stu-id="46f33-131">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor  catalogs** and double-click the catalog that you want  to work with.</span></span>

2. <span data-ttu-id="46f33-132">Töltse le az aktuális katalógus importálási sablonját (XSD-fájl).</span><span class="sxs-lookup"><span data-stu-id="46f33-132">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="46f33-133">Itt: **Katalógus módosítása** oldal, **Műveleti ablak**, **Katalógusok** lap, **Kapcsolódó információk** csoport, kattintson a **Katalógussablon előállítása** elemre, és válassza ki a **Beszerzési kategória** elemet.</span><span class="sxs-lookup"><span data-stu-id="46f33-133">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    - <span data-ttu-id="46f33-134">A **Beszerzési kategória** lehetőséggel olyan katalógussablon generálható, amely tartalmazza azokat a beszerzési kategóriákat, amelyekben a szállító jogosult termékeket kínálni.</span><span class="sxs-lookup"><span data-stu-id="46f33-134">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="46f33-135">A **Mentés másként** párbeszédpanelen válassza ki azt a helyet, ahol a katalógusfájl-sablont tárolni szeretné, és mentse a fájlt.</span><span class="sxs-lookup"><span data-stu-id="46f33-135">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="46f33-136">További tájékoztatás és példák ebben a blogbejegyzésben: [Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/) szállítói katalógusok.</span><span class="sxs-lookup"><span data-stu-id="46f33-136">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]