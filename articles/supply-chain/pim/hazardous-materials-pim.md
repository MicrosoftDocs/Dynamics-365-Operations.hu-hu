---
title: Veszélyes anyagok
description: Ez a témakör a környezetében tárolt veszélyes anyagi dokumentumokkal és adatokkal kapcsolatos információkat tartalmaz.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: feee6b348ac1870295a894ad988278b23a3f30a3
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979040"
---
# <a name="hazardous-materials"></a><span data-ttu-id="cc393-103">Veszélyes anyagok</span><span class="sxs-lookup"><span data-stu-id="cc393-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cc393-104">A veszélyes anyagokkal kapcsolatos információk a Termékinformáció-kezelés részben állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="cc393-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="cc393-105">Ez a modul a Raktárkezelés segítségével kinyomtatható dokumentumokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="cc393-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="cc393-106">A veszélyes áruknak minősített anyagok szállításakor a szállítmányoknak további papírmunkát kell tartalmazniuk.</span><span class="sxs-lookup"><span data-stu-id="cc393-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="cc393-107">A veszélyes anyagokra vonatkozó funkciók segítségével az ügyfelek tárolhatják az osztályozási adatokat, és azt a kiadott elemekkel összekapcsolhatják.</span><span class="sxs-lookup"><span data-stu-id="cc393-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="cc393-108">Ezt az információt ezután felhasználhatja a szállítási dokumentáció előkészítésére.</span><span class="sxs-lookup"><span data-stu-id="cc393-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc393-109">A Microsoft Dynamics 365 Supply Chain Management veszélyes anyagokkal kapcsolatos szolgáltatásai egy olyan, hasznos termékinformációk-mezőből és a kapcsolódó funkciókból álló gyűjteményt kínál, amelyek segítik a veszélyes termékekkel kapcsolatos adatok rögzítését és hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="cc393-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="cc393-110">Ezek a szolgáltatások segítenek a szállítási dokumentumok tervezésében és kinyomtatásában is, amelyek tartalmazzák a szállítás alatt álló veszélyes anyagokra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="cc393-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="cc393-111">A rendszer azonban nem biztosítja automatikusan a megfelelést az országa vagy a régiója vonatkozó jogszabályainak.</span><span class="sxs-lookup"><span data-stu-id="cc393-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="cc393-112">Noha ezeknek az eszközöknek az a célja, hogy segítsenek megfelelni az általános szabályoknak, önmagában nem elégségesek, és nem is garantáljuk ezt.</span><span class="sxs-lookup"><span data-stu-id="cc393-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="cc393-113">A szervezet felelős azért, hogy az összes vonatkozó előírás tudatában legyen, és minden szükséges lépést megtegyen azok teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cc393-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="cc393-114">Ez a funkció csak akkor használható, ha végrehajtotta az alábbi beállítást:</span><span class="sxs-lookup"><span data-stu-id="cc393-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="cc393-115">**Termékinformáció-kezelés:** a kiadott termékekhez alkalmazható kódokat állít be.</span><span class="sxs-lookup"><span data-stu-id="cc393-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="cc393-116">**Raktárkezelés:** további szállítási dokumentumok használata szállítási információk nyomtatására.</span><span class="sxs-lookup"><span data-stu-id="cc393-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="cc393-117">Termékinformáció-kezelés</span><span class="sxs-lookup"><span data-stu-id="cc393-117">Product information management</span></span>

<span data-ttu-id="cc393-118">A Termékinformáció-kezelés részben számos beállítási tábla adható hozzá a közúti, légi és tengeri fuvarozáshoz szükséges veszélyesáru-listákban szereplő hivatkozási adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="cc393-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="cc393-119">Íme néhány gyakran hivatkozott előírás:</span><span class="sxs-lookup"><span data-stu-id="cc393-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="cc393-120">**ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások</span><span class="sxs-lookup"><span data-stu-id="cc393-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="cc393-121">**CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására</span><span class="sxs-lookup"><span data-stu-id="cc393-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="cc393-122">**IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe</span><span class="sxs-lookup"><span data-stu-id="cc393-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="cc393-123">**IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai</span><span class="sxs-lookup"><span data-stu-id="cc393-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="cc393-124">A szabályozások mindegyikének van egy veszélyesáru-listája, amely hivatkozási kódokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="cc393-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="cc393-125">A különböző típusú fuvarozások listája közös nemzetközi osztályozásokon alapszik.</span><span class="sxs-lookup"><span data-stu-id="cc393-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="cc393-126">A Supply Chain Management tartalmaz egy hivatkozási táblát a lista közös kódjaihoz.</span><span class="sxs-lookup"><span data-stu-id="cc393-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="cc393-127">Minden lista tartalmaz néhány egyedi kódot is, amelyeket Ön határozhat meg.</span><span class="sxs-lookup"><span data-stu-id="cc393-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="cc393-128">Az adatok konfigurálásának megkezdéséhez hozzon létre egy olyan szabályt, amelyet a kezdeti paraméterek konfigurálására használhat fel.</span><span class="sxs-lookup"><span data-stu-id="cc393-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="cc393-129">Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="cc393-129">Warehouse management</span></span>

<span data-ttu-id="cc393-130">Egy szállítmány előkészítését követően számos új jelentést lehet kinyomtatni.</span><span class="sxs-lookup"><span data-stu-id="cc393-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="cc393-131">Ezek a jelentések a Termékinformáció-kezelés részben megadott adatokat használják.</span><span class="sxs-lookup"><span data-stu-id="cc393-131">These reports use the information that you set up in Product information management.</span></span>
