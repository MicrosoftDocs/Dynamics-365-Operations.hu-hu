--- 
title: "ISO20022 jóváírási konfiguráció importálása"
description: "Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 46cdc37181a1d4da0b14b428cc3231f740cc54aa
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="d8b6f-103">ISO20022 jóváírási konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="d8b6f-103">Import ISO20022 credit transfer configuration</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d8b6f-104">Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="d8b6f-105">A német ISO 20022 átutalási formátum szolgál példaként.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="d8b6f-106">Ez az eljárás egyéb rendelkezésre álló elektronikus jelentéskészítési formátumokhoz is használható.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="d8b6f-107">A feladat DEMF bemutatócég segítségével készült, de a feladat végrehajtásához bármely bemutatócég adatai felhasználhatók.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="d8b6f-108">Ez az első azon öt eljárás közül, amelyek együtt mutatják be elektronikus jelentési beállítások használatával a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="d8b6f-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="d8b6f-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d8b6f-111">Az elérhető konfigurációs szolgáltatók listájáról válassza a Microsoftot.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="d8b6f-112">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-112">Click Set active.</span></span>
4. <span data-ttu-id="d8b6f-113">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-113">Click Repositories.</span></span>
5. <span data-ttu-id="d8b6f-114">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-114">Click Open.</span></span>
6. <span data-ttu-id="d8b6f-115">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-115">Click Show filters.</span></span>
7. <span data-ttu-id="d8b6f-116">Alkalmazza a következő szűrőket: adja meg az „ISO20022 átutalás (DE)” szűrőértéket a „Konfiguráció neve” mezőben az „ezzel kezdődik” szűrési operátor használatával</span><span class="sxs-lookup"><span data-stu-id="d8b6f-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="d8b6f-117">Vagy keresse meg a konfigurációt a listán, válassza ki és helyezze át az Importálási feladatba.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="d8b6f-118">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-118">Click Import.</span></span>
    * <span data-ttu-id="d8b6f-119">Ha az Importálás gomb nem elérhető, az azt jelenti, hogy a konfiguráció importálása már megtörtént.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="d8b6f-120">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-120">Click Yes.</span></span>


