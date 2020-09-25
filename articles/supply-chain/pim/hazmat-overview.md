---
title: Veszélyes anyagok áttekintése
description: Ez a témakör áttekintést nyújt azokról a szolgáltatásokról, amelyek a termékadatok kezelése és a raktárkezelés során a veszélyes anyagok kezelésével és feldolgozásával kapcsolatosak.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 34c0a19308bb5159faa9a4ab06bf65e58da0deb1
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802749"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="8d087-103">Veszélyes anyagok áttekintése</span><span class="sxs-lookup"><span data-stu-id="8d087-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="8d087-104">A szállítási és szállítmányozási előírásoknak való megfelelés érdekében azokat a szervezeteket, amelyeknek a veszélyes áruknak minősülő anyagokat szállítanak, további dokumentációt kell készíteniük a szállítmányokhoz.</span><span class="sxs-lookup"><span data-stu-id="8d087-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="8d087-105">A veszélyes anyagok funkcióval a vevők a kiadott cikkekre vonatkozó adatokat tárolhatnak.</span><span class="sxs-lookup"><span data-stu-id="8d087-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="8d087-106">Ezt az információt ezután felhasználhatja a szállítási dokumentáció előkészítésére.</span><span class="sxs-lookup"><span data-stu-id="8d087-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="8d087-107">A veszélyes árukat szállító szervezetnek rendelkezniük kell saját folyamatokkal és eljárásokkal a szállítási folyamat kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="8d087-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="8d087-108">A Microsoft Dynamics 365 Supply Chain Management csak egy eszköz, amely segítséget nyújt a szükséges dokumentumok előállításában.</span><span class="sxs-lookup"><span data-stu-id="8d087-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="8d087-109">A következő ábra a veszélyes anyagok funkció beállításához és használatához szükséges lépéseket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="8d087-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="8d087-110">![A veszélyes anyagok funkció beállítása és használata](media/hazmat-overview.png "A veszélyes anyagok funkció beállítása és használata")</span><span class="sxs-lookup"><span data-stu-id="8d087-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="8d087-111">A veszélyes anyagok funkció a Termékinformációk kezelésénél van beállítva, és olyan dokumentumokat biztosít, amelyek a Raktárkezelésen keresztül nyomtathatók.</span><span class="sxs-lookup"><span data-stu-id="8d087-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="8d087-112">Ennek megfelelően túlnyomórészt a következő két fő területen tekinti át, állítja be és használja ennek a szolgáltatásnak a funkcióit:</span><span class="sxs-lookup"><span data-stu-id="8d087-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="8d087-113">**Termékinformáció-kezelés:** – A kiadott termékekhez alkalmazható kódokat állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="8d087-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="8d087-114">**Raktárkezelés** – A szállítmányok számára nyomtatandó további szállítási dokumentumokkal végzett munka.</span><span class="sxs-lookup"><span data-stu-id="8d087-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d087-115">Az Supply Chain Management veszélyes anyagokkal kapcsolatos szolgáltatásai egy olyan, hasznos termékinformációk-mezőből és a kapcsolódó funkciókból álló gyűjteményt kínál, amelyek segítik a veszélyes termékekkel kapcsolatos adatok rögzítését és hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="8d087-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="8d087-116">Ezek a szolgáltatások segítenek a szállítási dokumentumok tervezésében és kinyomtatásában is, amelyek tartalmazzák a szállítás alatt álló veszélyes anyagokra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="8d087-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="8d087-117">A rendszer azonban nem biztosítja automatikusan a megfelelést az országa vagy a régiója vonatkozó jogszabályainak.</span><span class="sxs-lookup"><span data-stu-id="8d087-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="8d087-118">Noha ezeknek az eszközöknek az a célja, hogy segítsenek megfelelni az általános szabályoknak, önmagában nem elégségesek, és nem is garantáljuk ezt.</span><span class="sxs-lookup"><span data-stu-id="8d087-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="8d087-119">A szervezet felelős azért, hogy az összes vonatkozó előírás tudatában legyen, és minden szükséges lépést megtegyen azok teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8d087-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="8d087-120">Termékinformációk kezelése</span><span class="sxs-lookup"><span data-stu-id="8d087-120">Product information management</span></span>

<span data-ttu-id="8d087-121">A Termékinformáció-kezelés részben számos beállítási tábla adható hozzá a közúti, légi és tengeri fuvarozáshoz szükséges veszélyesáru-listákban szereplő hivatkozási adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="8d087-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="8d087-122">A következő közös általános szabályozásokra támaszkodtunk a funkcionalitás fejlesztésekor:</span><span class="sxs-lookup"><span data-stu-id="8d087-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="8d087-123">**ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások</span><span class="sxs-lookup"><span data-stu-id="8d087-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="8d087-124">**CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására</span><span class="sxs-lookup"><span data-stu-id="8d087-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="8d087-125">**IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe</span><span class="sxs-lookup"><span data-stu-id="8d087-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="8d087-126">**IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai</span><span class="sxs-lookup"><span data-stu-id="8d087-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="8d087-127">A rendeletek mindegyik készlete a veszélyes áruk és hivatkozási kódok szabványosított listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="8d087-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="8d087-128">Ennek megfelelően a Supply Chain Management tartalmaz egy hivatkozási táblát a listák közös kódjaihoz.</span><span class="sxs-lookup"><span data-stu-id="8d087-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="8d087-129">Minden lista tartalmaz néhány egyedi kódot is, amelyek definiálhatók.</span><span class="sxs-lookup"><span data-stu-id="8d087-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="8d087-130">A veszélyes anyagokra vonatkozó előírások és értékek beállításával, valamint az értékek megfelelő termékekhez történő hozzárendelésével kapcsolatos további tudnivalókat lásd a következő témakörökben:</span><span class="sxs-lookup"><span data-stu-id="8d087-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="8d087-131">Veszélyes anyagok beállítása</span><span class="sxs-lookup"><span data-stu-id="8d087-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="8d087-132">Termékekben, megrendelésekben, szállítmányokban és rakományokban lévő veszélyes anyagok</span><span class="sxs-lookup"><span data-stu-id="8d087-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="8d087-133">Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="8d087-133">Warehouse management</span></span>

<span data-ttu-id="8d087-134">Amikor szállítmányt készít a Raktárkezelés modulban, számos új jelentést nyomtathat, amelyek a Termékinformációk kezelése modulban beállított adatokat használják.</span><span class="sxs-lookup"><span data-stu-id="8d087-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="8d087-135">A rendelkezésre álló jelentésekről és azok használatáról a [Veszélyes anyagokkal kapcsolatos lekérdezések és jelentések](hazmat-reports.md) című témakörben olvashat bővebben.</span><span class="sxs-lookup"><span data-stu-id="8d087-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>
