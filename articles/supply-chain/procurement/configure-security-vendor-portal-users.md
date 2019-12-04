---
title: Felhasználói biztonság a szállítói portálon
description: Ez a cikk ismerteti a szállítói portált használó külső szállítók biztonságának beállítását. Az itt olvasható információk csak a Dynamics AX 2016. februári és 2016. májusi verzióira vonatkoznak.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 944b27754e87d80584b7fdfffa46d8af112227e3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813569"
---
# <a name="vendor-portal-user-security"></a><span data-ttu-id="a68f7-104">Szállítói portál felhasználói biztonsága</span><span class="sxs-lookup"><span data-stu-id="a68f7-104">Vendor portal user security</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a68f7-105">Ez a cikk ismerteti a szállítói portált használó külső szállítók biztonságának beállítását.</span><span class="sxs-lookup"><span data-stu-id="a68f7-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="a68f7-106">Az itt olvasható információk csak a Dynamics AX 2016. februári és 2016. májusi verzióira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="a68f7-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="a68f7-107">A Szállítói portál funkciót a Dynamics 365 for Operations rendszer 1611-es verziójának Kiterjesztett szállítói együttműködés funkciója váltotta le.</span><span class="sxs-lookup"><span data-stu-id="a68f7-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="a68f7-108">A biztonságnak a szállítói együttműködésben való beállítására vonatkozó további tudnivalókat lásd: [Szállítói együttműködés beállítása és karbantartása](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="a68f7-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="a68f7-109">A szállítói portálon korlátozott mennyiségű információ érhető el a beszerzési rendelésekkel (PO) kapcsolatban külső szállítók számára.</span><span class="sxs-lookup"><span data-stu-id="a68f7-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="a68f7-110">A Microsoft Dynamics AX szállítói portáljánál fontos a felhasználói jogosultságok helyes beállítása, hogy a szállítók ne férhessenek hozzá véletlenül további információkhoz a Dynamics AX szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="a68f7-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="a68f7-111">**Fontos:** más felhasználókkal ellentétben a külső szállítóknak nem szabad **rendszerfelhasználó** szerepkörrel rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="a68f7-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="a68f7-112">A **rendszerfelhasználó** szerepkör olyan jogosultságokhoz ad hozzáférést, amelyek nem megfelelők külső felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="a68f7-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="a68f7-113">A szállítói portál felhasználóinak beállítása</span><span class="sxs-lookup"><span data-stu-id="a68f7-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="a68f7-114">Mielőtt létrehozna egy felhasználói fiókot valaki számára, aki a szállítói portált fogja használni, be kell állítania a szállítót, hogy lehetővé váljon a szállítói együttműködés.</span><span class="sxs-lookup"><span data-stu-id="a68f7-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="a68f7-115">Használja a **Beszerzési rendelési együttműködési** mezőt az **Általános** lapon, a **Szállítók** oldalon.</span><span class="sxs-lookup"><span data-stu-id="a68f7-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="a68f7-116">A szállítói portált használó külső szállítók esetében a következő beállítást kell használni:</span><span class="sxs-lookup"><span data-stu-id="a68f7-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="a68f7-117">Regisztrálni kell egy Microsoft Azure Active Directory (AAD) felhasználói fiókot a szállító számára a **Felhasználók** oldalon a Dynamics AX rendszerben.</span><span class="sxs-lookup"><span data-stu-id="a68f7-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="a68f7-118">A szállítónak a **Szállító (külső)** biztonsági szerepkörrel kell rendelkeznie, nem pedig a **Rendszerfelhasználó**szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="a68f7-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="a68f7-119">**Megjegyzés**: a **Rendszerfelhasználó** szerepkört automatikusan megadja a rendszer egy új felhasználói fiók létrehozásakor a Dynamics AX rendszerben.</span><span class="sxs-lookup"><span data-stu-id="a68f7-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="a68f7-120">Ezért ezt a szerepkört el kell távolítani, és nyugtázni kell megjelenő figyelmeztetőüzenetet.</span><span class="sxs-lookup"><span data-stu-id="a68f7-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="a68f7-121">A szállítói felhasználó nem rendelkezhet olyan jogosultsággal, amellyel további mezőket adhat a PO-táblázatokból a saját PO-nézetéhez.</span><span class="sxs-lookup"><span data-stu-id="a68f7-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="a68f7-122">A **Személyre szabás** lapon, a **Felhasználók** lapon állítsa be az **Explicit személyre szabás engedélyezve** lehetőségnél a **Nem** értéket.</span><span class="sxs-lookup"><span data-stu-id="a68f7-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="a68f7-123">A felhasználói fiókot egy regisztrált kapcsolattartó személyhez kell társítani.</span><span class="sxs-lookup"><span data-stu-id="a68f7-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="a68f7-124">A **Felhasználók** oldalon, válasszon ki egy kapcsolattartót a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a68f7-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="a68f7-125">A kiválasztott személynek **Kapcsolattartó** szerepkörrel kell rendelkeznie az érintett szállítónál.</span><span class="sxs-lookup"><span data-stu-id="a68f7-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="a68f7-126">Ha egy adott személynek több szállítói fiókkal kell hozzáférnie a szállítói portálhoz (például mert külön jogi személyekről van szó), akkor ezen személy felhasználói fiókjaihoz ugyanazt a regisztrált kapcsolattartó személyt kell társírani.</span><span class="sxs-lookup"><span data-stu-id="a68f7-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="a68f7-127">A **Szállító (külső)** szerepkör tartalmaz minden alapvető képességet, amelyek a szállítói portálon elérhető funkciók használatához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="a68f7-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="a68f7-128">Ezen beállítás segítségével garantálható, hogy a külső felhasználó által látható felhasználói felület csak a tervszerinti forgatókönyvre koncentrál.</span><span class="sxs-lookup"><span data-stu-id="a68f7-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

<a name="additional-resources"></a><span data-ttu-id="a68f7-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a68f7-129">Additional resources</span></span>
--------

[<span data-ttu-id="a68f7-130">Együttműködés a szállítókkal a Szállítói portálon keresztül</span><span class="sxs-lookup"><span data-stu-id="a68f7-130">Collaborate with vendors by using the Vendor portal</span></span>](collaborate-vendors-vendor-portal.md)



