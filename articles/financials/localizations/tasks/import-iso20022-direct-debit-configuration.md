--- 
title: "ISO20022 beszedési megbízási konfiguráció importálása"
description: "Ez az eljárás bemutatja, hogyan importálható vevői fizetési elektronikus jelentéskészítési konfiguráció."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
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
ms.openlocfilehash: ea88fd6edca291db984223413f671eec8935fc9a
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="febc7-103">ISO20022 beszedési megbízási konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="febc7-103">Import ISO20022 direct debit configuration</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="febc7-104">Ez az eljárás bemutatja, hogyan importálható vevői fizetési elektronikus jelentéskészítési konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="febc7-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="febc7-105">Ez az eljárás az ISO 20022 beszedési megbízási formátumot használja példaként.</span><span class="sxs-lookup"><span data-stu-id="febc7-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="febc7-106">Az eljárás a DEMF bemutatócég adatainak segítségével készült, de a célra bármely bemutatócég adatai felhasználhatók.</span><span class="sxs-lookup"><span data-stu-id="febc7-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="febc7-107">Ez az első azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a vevői kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="febc7-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="febc7-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="febc7-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="febc7-109">Az elérhető konfigurációs szolgáltatók listájáról válassza a Microsoftot.</span><span class="sxs-lookup"><span data-stu-id="febc7-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="febc7-110">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="febc7-110">Click Set active.</span></span>
4. <span data-ttu-id="febc7-111">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="febc7-111">Click Repositories.</span></span>
5. <span data-ttu-id="febc7-112">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="febc7-112">Click Open.</span></span>
6. <span data-ttu-id="febc7-113">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="febc7-113">Click Show filters.</span></span>
7. <span data-ttu-id="febc7-114">Alkalmazza a következő szűrőket: adja meg az „ISO20022 beszedési megbízás (DE)” szűrőértéket a „Konfiguráció neve” mezőben az „ezzel kezdődik” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="febc7-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="febc7-115">Szükség esetén a konfiguráció megtalálható a listában, válassza ki, és hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="febc7-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="febc7-116">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="febc7-116">Click Import.</span></span>
    * <span data-ttu-id="febc7-117">Ha az Importálás gomb nem elérhető, az azt jelenti, hogy a konfiguráció importálása már megtörtént.</span><span class="sxs-lookup"><span data-stu-id="febc7-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="febc7-118">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="febc7-118">Click Yes.</span></span>


