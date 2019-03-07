---
title: Helyhez és felekhez tartozó kapcsolattípusok hozzáadása
description: Ez a témakör egy új, helyhez és felekhez tartozó kapcsolattípus hozzáadását ismerteti
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 543784e8072f88c10f63e1b44921b9f2d37308c3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "357496"
---
# <a name="add-location-roles-and-party-relationship-types"></a><span data-ttu-id="e286d-103">Helyszerepekhez és felekhez tartozó kapcsolattípusok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="e286d-103">Add location roles and party relationship types</span></span> 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a><span data-ttu-id="e286d-104">Hely szerepköreinek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="e286d-104">Add location roles</span></span>

<span data-ttu-id="e286d-105">Két módszer áll rendelkezésre új helyszerepkör hozzáadására a cím és kapcsolattartási adatokhoz:</span><span class="sxs-lookup"><span data-stu-id="e286d-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="e286d-106">Hozzáadás **A cím és a kapcsolattartási adatok célja** oldalon.</span><span class="sxs-lookup"><span data-stu-id="e286d-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="e286d-107">Az új szerepkör mentésére a **LogisticsLocationRole** táblában kerül sor (típus= 0), ami azt jelzi, hogy a szerepkör nem a rendszer által meghatározott szerepkör a **LogisticsLocationRoleType** felsorolásban és a bővítményeiben.</span><span class="sxs-lookup"><span data-stu-id="e286d-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="e286d-108">A felhasználó akkor tudja használni ezt a szerepkört, amikor címet vagy kapcsolattartási adatokat létrehozásakor hoz létre.</span><span class="sxs-lookup"><span data-stu-id="e286d-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Cím- és tartalomadatok típusa](media/Address-Contact.PNG)

-  <span data-ttu-id="e286d-110">Adja hozzá a **LogisticsLocationRoleType** felsorolás kiterjesztéséhez, és hagyja, hogy az adatbázis feltöltődjön a szinkronizálási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="e286d-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="e286d-111">Hozzon létre kiterjesztést a **LogisticsLocationRoleType** felsoroláshoz, és adja meg az új szerepkör a kiterjesztésben.</span><span class="sxs-lookup"><span data-stu-id="e286d-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="e286d-113">Hozzon létre egy új erőforrásfájlt az új szerepkörhöz, majd rendeljen hozzá egy értéket a tulajdonságaihoz.</span><span class="sxs-lookup"><span data-stu-id="e286d-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Új erőforrás-fájl](media/Resource.PNG)
        
    3.  <span data-ttu-id="e286d-115">Hozzon létre egy adatfeltöltési osztályt, és adjon meg egy kezelési módszert az új szerepkör feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="e286d-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Adatfeltöltés](media/Dirdata.PNG)

    4.  <span data-ttu-id="e286d-117">Az új helyszerepkör feltöltésének teszteléséhez létrehozhat egy futtatható osztályt, és hívja elő ezt: DirDataPopulation::insertLogisticsLocationRoles() a Fő() menüben.</span><span class="sxs-lookup"><span data-stu-id="e286d-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="e286d-118">Miután ez a folyamat befejeződött, látnia kell a feltöltött új szerepkört a **LogisticsLocationRole** táblában, melynek típusa \>0.</span><span class="sxs-lookup"><span data-stu-id="e286d-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="e286d-119">Az új szerepkör megjelenik a **Cím- és kapcsolattartási adatok célja** oldalon.</span><span class="sxs-lookup"><span data-stu-id="e286d-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Új hely beszúrása](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a><span data-ttu-id="e286d-121">Fél-kapcsolattípus hozzáadása</span><span class="sxs-lookup"><span data-stu-id="e286d-121">Add party relationship types</span></span> 

<span data-ttu-id="e286d-122">Új kapcsolattípust kétféleképpen lehet hozzáadni:</span><span class="sxs-lookup"><span data-stu-id="e286d-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="e286d-123">Hozzáadás a **kapcsolattípusok** oldalon keresztül.</span><span class="sxs-lookup"><span data-stu-id="e286d-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="e286d-124">Az új kapcsolat mentésére itt kerül sor: **DirRelationshipTypeTable**, systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="e286d-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Kapcsolattípusok](media/Relationship.PNG)

-  <span data-ttu-id="e286d-126">Adja hozzá a **DirSystemRelationshipType** felsorolás kiterjesztéséhez, és hagyja, hogy az adatbázis feltöltődjön a szinkronizálási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="e286d-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="e286d-127">Hozzon létre kiterjesztést a **DirSystemRelationshipType** felsoroláshoz, majd adja meg az új kapcsolat típusát.</span><span class="sxs-lookup"><span data-stu-id="e286d-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="e286d-128">Hozzon létre egy inicializálót ehhez az új típushoz.</span><span class="sxs-lookup"><span data-stu-id="e286d-128">Create an initializer for this new type.</span></span> <span data-ttu-id="e286d-129">Számos példa található a fő kódra, az egyikük **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="e286d-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="e286d-130">Ez az egy inicializáló-osztály a "Gyermek" kapcsolattípusú félhez.</span><span class="sxs-lookup"><span data-stu-id="e286d-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="e286d-131">A inicializálót ennek a kódnak a másolásával és beillesztésével, majd frissítse a kijelölt területeket.</span><span class="sxs-lookup"><span data-stu-id="e286d-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="e286d-133">Az új kapcsolattípus feltöltésének teszteléséhez létrehozhat egy futtaható osztályt, és hívja elő ezt: DirDataPopulation::insertDirRelationshipTypes() a Fő() menüben.</span><span class="sxs-lookup"><span data-stu-id="e286d-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="e286d-134">Az új kapcsolattípus megjelenik a **DirRelationshipTypeTable** táblában, és az új kapcsolattípus elérhető lesz a **Kapcsolattípusok** lapon.</span><span class="sxs-lookup"><span data-stu-id="e286d-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Futtatható osztály](media/Runnable.PNG)
