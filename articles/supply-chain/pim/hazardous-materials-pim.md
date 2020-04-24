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
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5006f06d90ddcc314a51878e9e21337de7d493e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208462"
---
# <a name="hazardous-materials"></a><span data-ttu-id="feba2-103">Veszélyes anyagok</span><span class="sxs-lookup"><span data-stu-id="feba2-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="feba2-104">A veszélyes anyagokkal kapcsolatos információk a Termékinformáció-kezelés részben állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="feba2-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="feba2-105">Ez a modul a Raktárkezelés segítségével kinyomtatható dokumentumokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="feba2-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="feba2-106">A veszélyes áruknak minősített anyagok szállításakor a szállítmányoknak további papírmunkát kell tartalmazniuk.</span><span class="sxs-lookup"><span data-stu-id="feba2-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="feba2-107">A veszélyes anyagokra vonatkozó funkciók segítségével az ügyfelek tárolhatják az osztályozási adatokat, és azt a kiadott elemekkel összekapcsolhatják.</span><span class="sxs-lookup"><span data-stu-id="feba2-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="feba2-108">Ezt az információt ezután felhasználhatja a szállítási dokumentáció előkészítésére.</span><span class="sxs-lookup"><span data-stu-id="feba2-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feba2-109">A veszélyes áruk szállításának kezelése céljából a Microsoft Dynamics 365 Supply Chain Management lehetővé teszi a termékekkel kapcsolatos további hivatkozási adatok beállítását.</span><span class="sxs-lookup"><span data-stu-id="feba2-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="feba2-110">További, szállítással kapcsolatos dokumentumokat is be lehet állítani.</span><span class="sxs-lookup"><span data-stu-id="feba2-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="feba2-111">A rendszer azonban nem felel meg automatikusan az országa vagy a régiója szabályzatának.</span><span class="sxs-lookup"><span data-stu-id="feba2-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="feba2-112">Ehelyett egy olyan eszköz, amely segítséget nyújt az általános programjához.</span><span class="sxs-lookup"><span data-stu-id="feba2-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="feba2-113">Ez a funkció csak akkor használható, ha végrehajtotta az alábbi beállítást:</span><span class="sxs-lookup"><span data-stu-id="feba2-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="feba2-114">**Termékinformáció-kezelés:** a kiadott termékekhez alkalmazható kódokat állít be.</span><span class="sxs-lookup"><span data-stu-id="feba2-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="feba2-115">**Raktárkezelés:** további szállítási dokumentumok használata szállítási információk nyomtatására.</span><span class="sxs-lookup"><span data-stu-id="feba2-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="feba2-116">Termékinformáció-kezelés</span><span class="sxs-lookup"><span data-stu-id="feba2-116">Product information management</span></span>

<span data-ttu-id="feba2-117">A Termékinformáció-kezelés részben számos beállítási tábla adható hozzá a közúti, légi és tengeri fuvarozáshoz szükséges veszélyesáru-listákban szereplő hivatkozási adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="feba2-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="feba2-118">Íme néhány gyakran hivatkozott előírás:</span><span class="sxs-lookup"><span data-stu-id="feba2-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="feba2-119">**ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások</span><span class="sxs-lookup"><span data-stu-id="feba2-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="feba2-120">**CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására</span><span class="sxs-lookup"><span data-stu-id="feba2-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="feba2-121">**IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe</span><span class="sxs-lookup"><span data-stu-id="feba2-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="feba2-122">**IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai</span><span class="sxs-lookup"><span data-stu-id="feba2-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="feba2-123">A szabályozások mindegyikének van egy veszélyesáru-listája, amely hivatkozási kódokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="feba2-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="feba2-124">A különböző típusú fuvarozások listája közös nemzetközi osztályozásokon alapszik.</span><span class="sxs-lookup"><span data-stu-id="feba2-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="feba2-125">A Supply Chain Management tartalmaz egy hivatkozási táblát a lista közös kódjaihoz.</span><span class="sxs-lookup"><span data-stu-id="feba2-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="feba2-126">Minden lista tartalmaz néhány egyedi kódot is, amelyeket Ön határozhat meg.</span><span class="sxs-lookup"><span data-stu-id="feba2-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="feba2-127">Az adatok konfigurálásának megkezdéséhez hozzon létre egy olyan szabályt, amelyet a kezdeti paraméterek konfigurálására használhat fel.</span><span class="sxs-lookup"><span data-stu-id="feba2-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="feba2-128">Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="feba2-128">Warehouse management</span></span>

<span data-ttu-id="feba2-129">Egy szállítmány előkészítését követően számos új jelentést lehet kinyomtatni.</span><span class="sxs-lookup"><span data-stu-id="feba2-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="feba2-130">Ezek a jelentések a Termékinformáció-kezelés részben megadott adatokat használják.</span><span class="sxs-lookup"><span data-stu-id="feba2-130">These reports use the information that you set up in Product information management.</span></span>
