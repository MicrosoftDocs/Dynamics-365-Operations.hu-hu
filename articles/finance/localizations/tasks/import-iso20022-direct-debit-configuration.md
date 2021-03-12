---
title: ISO20022 beszedési megbízási konfiguráció importálása
description: Ez az eljárás bemutatja, hogyan importálható vevői fizetési elektronikus jelentéskészítési konfiguráció.
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
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d68e5a63ea3b037cc111d6732857f0aae1ce7e5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989951"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="0338b-103">ISO20022 beszedési megbízási konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="0338b-103">Import ISO20022 direct debit configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0338b-104">Ez az eljárás bemutatja, hogyan importálható vevői fizetési elektronikus jelentéskészítési konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="0338b-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="0338b-105">Ez az eljárás az ISO 20022 beszedési megbízási formátumot használja példaként.</span><span class="sxs-lookup"><span data-stu-id="0338b-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="0338b-106">Az eljárás a DEMF bemutatócég adatainak segítségével készült, de a célra bármely bemutatócég adatai felhasználhatók.</span><span class="sxs-lookup"><span data-stu-id="0338b-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="0338b-107">Ez az első azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a vevői kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="0338b-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="0338b-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="0338b-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="0338b-109">Az elérhető konfigurációs szolgáltatók listájáról válassza a Microsoftot.</span><span class="sxs-lookup"><span data-stu-id="0338b-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="0338b-110">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="0338b-110">Click Set active.</span></span>
4. <span data-ttu-id="0338b-111">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="0338b-111">Click Repositories.</span></span>
5. <span data-ttu-id="0338b-112">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="0338b-112">Click Open.</span></span>
6. <span data-ttu-id="0338b-113">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="0338b-113">Click Show filters.</span></span>
7. <span data-ttu-id="0338b-114">Alkalmazza a következő szűrőket: adja meg az „ISO20022 beszedési megbízás (DE)” szűrőértéket a „Konfiguráció neve” mezőben az „ezzel kezdődik” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="0338b-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="0338b-115">Szükség esetén a konfiguráció megtalálható a listában, válassza ki, és hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="0338b-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="0338b-116">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="0338b-116">Click Import.</span></span>
    * <span data-ttu-id="0338b-117">Ha az Importálás gomb nem elérhető, az azt jelenti, hogy a konfiguráció importálása már megtörtént.</span><span class="sxs-lookup"><span data-stu-id="0338b-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="0338b-118">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="0338b-118">Click Yes.</span></span>

