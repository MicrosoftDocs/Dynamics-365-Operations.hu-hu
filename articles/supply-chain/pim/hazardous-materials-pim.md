---
title: Veszélyes anyagok
description: Ez a témakör a környezetében tárolt veszélyes anyagi dokumentumokkal és adatokkal kapcsolatos információkat tartalmaz.
author: lachlancashMS
manager: AnnBe
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
ms.openlocfilehash: 76dd6539e39bb77c546e613b290fc5decba9457f
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982308"
---
# <a name="hazardous-materials"></a><span data-ttu-id="61f94-103">Veszélyes anyagok</span><span class="sxs-lookup"><span data-stu-id="61f94-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61f94-104">A veszélyes anyagokkal kapcsolatos információk a Termékinformáció-kezelés részben állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="61f94-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="61f94-105">Ez a modul a Raktárkezelés segítségével kinyomtatható dokumentumokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="61f94-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="61f94-106">A veszélyes áruknak minősített anyagok szállításakor a szállítmányoknak további papírmunkát kell tartalmazniuk.</span><span class="sxs-lookup"><span data-stu-id="61f94-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="61f94-107">A veszélyes anyagokra vonatkozó funkciók segítségével az ügyfelek tárolhatják az osztályozási adatokat, és azt a kiadott elemekkel összekapcsolhatják.</span><span class="sxs-lookup"><span data-stu-id="61f94-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="61f94-108">Ezt az információt ezután felhasználhatja a szállítási dokumentáció előkészítésére.</span><span class="sxs-lookup"><span data-stu-id="61f94-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61f94-109">A veszélyes áruk szállításának kezelése céljából a Microsoft Dynamics 365 Supply Chain Management lehetővé teszi a termékekkel kapcsolatos további hivatkozási adatok beállítását.</span><span class="sxs-lookup"><span data-stu-id="61f94-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="61f94-110">További, szállítással kapcsolatos dokumentumokat is be lehet állítani.</span><span class="sxs-lookup"><span data-stu-id="61f94-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="61f94-111">A rendszer azonban nem felel meg automatikusan az országa vagy a régiója szabályzatának.</span><span class="sxs-lookup"><span data-stu-id="61f94-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="61f94-112">Ehelyett egy olyan eszköz, amely segítséget nyújt az általános programjához.</span><span class="sxs-lookup"><span data-stu-id="61f94-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="61f94-113">Ez a funkció csak akkor használható, ha végrehajtotta az alábbi beállítást:</span><span class="sxs-lookup"><span data-stu-id="61f94-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="61f94-114">**Termékinformáció-kezelés:** a kiadott termékekhez alkalmazható kódokat állít be.</span><span class="sxs-lookup"><span data-stu-id="61f94-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="61f94-115">**Raktárkezelés:** további szállítási dokumentumok használata szállítási információk nyomtatására.</span><span class="sxs-lookup"><span data-stu-id="61f94-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="61f94-116">Termékinformáció-kezelés</span><span class="sxs-lookup"><span data-stu-id="61f94-116">Product information management</span></span>

<span data-ttu-id="61f94-117">A Termékinformáció-kezelés részben számos beállítási tábla adható hozzá a közúti, légi és tengeri fuvarozáshoz szükséges veszélyesáru-listákban szereplő hivatkozási adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="61f94-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="61f94-118">Íme néhány gyakran hivatkozott előírás:</span><span class="sxs-lookup"><span data-stu-id="61f94-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="61f94-119">**ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások</span><span class="sxs-lookup"><span data-stu-id="61f94-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="61f94-120">**CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására</span><span class="sxs-lookup"><span data-stu-id="61f94-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="61f94-121">**IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe</span><span class="sxs-lookup"><span data-stu-id="61f94-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="61f94-122">**IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai</span><span class="sxs-lookup"><span data-stu-id="61f94-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="61f94-123">A szabályozások mindegyikének van egy veszélyesáru-listája, amely hivatkozási kódokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="61f94-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="61f94-124">A különböző típusú fuvarozások listája közös nemzetközi osztályozásokon alapszik.</span><span class="sxs-lookup"><span data-stu-id="61f94-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="61f94-125">A Supply Chain Management tartalmaz egy hivatkozási táblát a lista közös kódjaihoz.</span><span class="sxs-lookup"><span data-stu-id="61f94-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="61f94-126">Minden lista tartalmaz néhány egyedi kódot is, amelyeket Ön határozhat meg.</span><span class="sxs-lookup"><span data-stu-id="61f94-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="61f94-127">Az adatok konfigurálásának megkezdéséhez hozzon létre egy olyan szabályt, amelyet a kezdeti paraméterek konfigurálására használhat fel.</span><span class="sxs-lookup"><span data-stu-id="61f94-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="61f94-128">Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="61f94-128">Warehouse management</span></span>

<span data-ttu-id="61f94-129">Egy szállítmány előkészítését követően számos új jelentést lehet kinyomtatni.</span><span class="sxs-lookup"><span data-stu-id="61f94-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="61f94-130">Ezek a jelentések a Termékinformáció-kezelés részben megadott adatokat használják.</span><span class="sxs-lookup"><span data-stu-id="61f94-130">These reports use the information that you set up in Product information management.</span></span>
