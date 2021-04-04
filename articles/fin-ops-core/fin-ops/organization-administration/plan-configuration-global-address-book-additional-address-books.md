---
title: Terv a globális címjegyzékhez és további címjegyzékekhez
description: Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a globális vagy bármely más címjegyzék beállítása és konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a0613b944d0446e339480a71fa890702190ed53
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559965"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="2bf1f-103">Terv a globális címjegyzékhez és egyéb címjegyzékekhez</span><span class="sxs-lookup"><span data-stu-id="2bf1f-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bf1f-104">Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a globális vagy bármely más címjegyzék beállítása és konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="2bf1f-105">Egyes döntések megkövetelik a korábban, a termék más területével kapcsolatban hozott döntések (pl. a szervezeti hierarchia) megerősítését.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="2bf1f-106">Globális címjegyzék</span><span class="sxs-lookup"><span data-stu-id="2bf1f-106">Global address book</span></span>

<span data-ttu-id="2bf1f-107">A globális címjegyzék használata előtt meg kell határoznia az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="2bf1f-108">Ezeket az alapértelmezett értékeket a minden további címjegyzékhez felhasználják, amelyet létrehoz.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="2bf1f-109">**Döntések**</span><span class="sxs-lookup"><span data-stu-id="2bf1f-109">**Decisions**</span></span>

- <span data-ttu-id="2bf1f-110">Milyen sorrendben kell a neveknek megjelennie a **Személy** típusának partnerrekordjai számára?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="2bf1f-111">Például egy sorozatot egy vezetéknevet, utónevet, keresztnevet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="2bf1f-112">Törölni kell a felek rekordjait a címjegyzékből a szerepkör-rekord törlésekor?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="2bf1f-113">Például ha egy vevő rekord törlődik, törölni kell partnerrekordot is törölni kell?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="2bf1f-114">Új rekord létrehozásakor, értesíteni kell a felhasználókat, ha ismétlődő rekordot található a globális címjegyzékben?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="2bf1f-115">Szerepelnie kell Data Universal Numbering System (DUNS) számnak egy fél rekordjában lévő adatokban?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="2bf1f-116">Ha a DUNS szám szerepel a fél rekordjában, ellenőrizni kell a szám egyediségét?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="2bf1f-117">Szeretne egy alapértelmezett fél típust, személyt vagy szervezetet a címjegyzék-bejegyzés létrehozásakor a globális címjegyzékben?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="2bf1f-118">Mely felhasználói szerepkörnek kell rendelkeznie hozzáféréssel a privát címekhez és fél rekordjainak kapcsolattartási adataihoz?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="2bf1f-119">További címjegyzékek</span><span class="sxs-lookup"><span data-stu-id="2bf1f-119">Additional address books</span></span>

<span data-ttu-id="2bf1f-120">Miután létrehozta a globális címjegyzéket, további címjegyzéket hozhat létre szükség szerint, például vállalatonként vagy az üzlet sorainként külön címjegyzéket hozhat létre a szervezetben.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="2bf1f-121">Például a Fabrikam egy nemzetközi szervezet, amely több vállalattal és több üzletággal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="2bf1f-122">Fabrikam tervezi a címjegyzékek létrehozását az üzlet minden egyes sorához.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="2bf1f-123">Azoknál az üzletágaknál, amelyek egynél több helyen, például az eszközök pneumatikus üzletnél fordulnak elő. A Fabrikam minden egyes helyhez egy címjegyzék létrehozását tervezi.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="2bf1f-124">Chris, a Fabrikaminformatikai vezetője hozta létre a szükséges címjegyzékek alábbi listáját.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="2bf1f-125">Ez a lista bemutatja a fél azon rekordjait, amelyeket minden címjegyzéknek tartalmaznia kell.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="2bf1f-126">**Állami szektor szerződések (PubSC)** – A Fabrikam által gyakorló állami szektor szerződésekben érintett összes fél társrekordjai.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="2bf1f-127">**Magánszektor szerződések (PriSC)** – A Fabrikam által gyakorló magánszektor szerződésekben érintett összes fél társrekordjai.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="2bf1f-128">**Elektronikus eszközök (ET)** – Az elektronikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam japán vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított elektronikai eszközökkel kommunikál.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="2bf1f-129">**Pneumatikus eszközök (PTJPN)** – A pneumatikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam japán vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított pneumatikus eszközökkel kommunikál.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="2bf1f-130">**Pneumatikus eszközök (PTUSA)** – A pneumatikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam amerikai vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított pneumatikus eszközökkel kommunikál.</span><span class="sxs-lookup"><span data-stu-id="2bf1f-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="2bf1f-131">**Döntés:**</span><span class="sxs-lookup"><span data-stu-id="2bf1f-131">**Decision:**</span></span>

- <span data-ttu-id="2bf1f-132">Hány további címjegyzékek kíván létrehozni?</span><span class="sxs-lookup"><span data-stu-id="2bf1f-132">How many additional address books will you create?</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]