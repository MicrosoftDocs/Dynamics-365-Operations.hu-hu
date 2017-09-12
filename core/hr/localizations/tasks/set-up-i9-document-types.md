--- 
title: "I-9 dokumentumtípusok beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet megtekinteni és létrehozni I-9 igazoláshoz használt dokumentumtípusokat."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3b0e7f09994367f5683ed5c6d1f3b3ba3d550cc7
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="72e1c-103">I-9 dokumentumtípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="72e1c-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="72e1c-104">Ez az eljárás bemutatja, hogyan lehet megtekinteni és létrehozni I-9 igazoláshoz használt dokumentumtípusokat.</span><span class="sxs-lookup"><span data-stu-id="72e1c-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="72e1c-105">I-9 dokumentumtípusok létrehozása előtt létre kell hoznia kiállító hivatalokat és azonosítótípusokat is.</span><span class="sxs-lookup"><span data-stu-id="72e1c-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="72e1c-106">Az eljárás létrehozásához használt bemutatóvállalat az USMF, amely tartalmaz példákat a kiadási szervekre és a művelet végrehajtásához szükséges azonosítótípusokra is.</span><span class="sxs-lookup"><span data-stu-id="72e1c-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="72e1c-107">Ugorjon az Emberi erőforrások > Dolgozók > I-9 > I-9 dokumentumtípusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="72e1c-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="72e1c-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="72e1c-108">Click New.</span></span>
3. <span data-ttu-id="72e1c-109">Az I-9 dokumentumtípus mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="72e1c-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="72e1c-110">Példa: Iskolai azonosító.</span><span class="sxs-lookup"><span data-stu-id="72e1c-110">Example: School ID.</span></span>  
4. <span data-ttu-id="72e1c-111">Jelölje ki az azonosítás típusát.</span><span class="sxs-lookup"><span data-stu-id="72e1c-111">Select the identification type.</span></span>  <span data-ttu-id="72e1c-112">Példa: Iskolai azonosító.</span><span class="sxs-lookup"><span data-stu-id="72e1c-112">Example:  School ID</span></span>
    * <span data-ttu-id="72e1c-113">Azonosítótípusok közé a TAJ-szám (SS), vízum száma, útlevél azonosítója vagy jogosítvány száma tartozik.</span><span class="sxs-lookup"><span data-stu-id="72e1c-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's licence.</span></span>  
5. <span data-ttu-id="72e1c-114">Jelölje be a dokumentumtípushoz használt I-9 dokumentumlistát.</span><span class="sxs-lookup"><span data-stu-id="72e1c-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="72e1c-115">A I-9 folyamat részeként az alkalmazottaknak olyan dokumentációt kell bemutatniuk, amely bizonyítja a munkáltatónak a személyazonosságot és a munkavállalási engedélyt.</span><span class="sxs-lookup"><span data-stu-id="72e1c-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="72e1c-116">Az USA Állampolgársági és bevándorlási hivatal webhelye tájékoztatást nyújt arról, hogy mely dokumentumok elfogadhatók, és mely listához tartoznak.</span><span class="sxs-lookup"><span data-stu-id="72e1c-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="72e1c-117">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="72e1c-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="72e1c-118">Az Űrlap mezőben adja meg a dokumentumtípus hivatalos űrlapszámát.</span><span class="sxs-lookup"><span data-stu-id="72e1c-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="72e1c-119">Példa: Iskolai azonosító.</span><span class="sxs-lookup"><span data-stu-id="72e1c-119">Example: School ID.</span></span>
    * <span data-ttu-id="72e1c-120">A hivatalos űrlapszámok a USA Állampolgársági és bevándorlási hivatalának webhelyén megtalálhatók.</span><span class="sxs-lookup"><span data-stu-id="72e1c-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="72e1c-121">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="72e1c-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="72e1c-122">Az Aktív jelölőnégyzet bejelölése vagy a jelölés törlése</span><span class="sxs-lookup"><span data-stu-id="72e1c-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="72e1c-123">A Lejárat mezőben adja meg a 2019. 10. 27. dátumot.</span><span class="sxs-lookup"><span data-stu-id="72e1c-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="72e1c-124">A lejárati dátum nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="72e1c-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="72e1c-125">Válassza ki a dokumentumtípust kibocsátó hatóságot.</span><span class="sxs-lookup"><span data-stu-id="72e1c-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="72e1c-126">Példa: Megye/terület</span><span class="sxs-lookup"><span data-stu-id="72e1c-126">Example: Province/territory</span></span>
10. <span data-ttu-id="72e1c-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="72e1c-127">Click Save.</span></span>


