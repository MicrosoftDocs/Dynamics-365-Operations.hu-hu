---
title: ISO20022 jóváírási konfiguráció importálása
description: Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 01f44c49b6623cbcc2f08cfd6e4978c9a1676b83
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444023"
---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="5ccc1-103">ISO20022 jóváírási konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="5ccc1-103">Import ISO20022 credit transfer configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5ccc1-104">Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="5ccc1-105">A német ISO 20022 átutalási formátum szolgál példaként.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="5ccc1-106">Ez az eljárás egyéb rendelkezésre álló elektronikus jelentéskészítési formátumokhoz is használható.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="5ccc1-107">A feladat DEMF bemutatócég segítségével készült, de a feladat végrehajtásához bármely bemutatócég adatai felhasználhatók.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="5ccc1-108">Ez az első azon öt eljárás közül, amelyek együtt mutatják be elektronikus jelentési beállítások használatával a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="5ccc1-109">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="5ccc1-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5ccc1-111">Az elérhető konfigurációs szolgáltatók listájáról válassza a Microsoftot.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="5ccc1-112">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-112">Click Set active.</span></span>
4. <span data-ttu-id="5ccc1-113">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-113">Click Repositories.</span></span>
5. <span data-ttu-id="5ccc1-114">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-114">Click Open.</span></span>
6. <span data-ttu-id="5ccc1-115">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-115">Click Show filters.</span></span>
7. <span data-ttu-id="5ccc1-116">Alkalmazza a következő szűrőket: adja meg az „ISO20022 átutalás (DE)” szűrőértéket a „Konfiguráció neve” mezőben az „ezzel kezdődik” szűrési operátor használatával</span><span class="sxs-lookup"><span data-stu-id="5ccc1-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="5ccc1-117">Vagy keresse meg a konfigurációt a listán, válassza ki és helyezze át az Importálási feladatba.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="5ccc1-118">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-118">Click Import.</span></span>
    * <span data-ttu-id="5ccc1-119">Ha az Importálás gomb nem elérhető, az azt jelenti, hogy a konfiguráció importálása már megtörtént.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="5ccc1-120">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="5ccc1-120">Click Yes.</span></span>

