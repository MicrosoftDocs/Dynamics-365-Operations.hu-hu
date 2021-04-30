---
title: A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése
description: Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezését ismerteti.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c4d596f27ffe15a97dc04e2ce7e85d21f8e7161f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908395"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="e17d2-103">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="e17d2-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e17d2-104">Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezését ismerteti.</span><span class="sxs-lookup"><span data-stu-id="e17d2-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="e17d2-105">A Teams alkalmazást Dynamics 365 Commerce rendszerből származó információkkal információkkal szeretné kiépíteni, és szinkronizálni szeretné a kezelési funkciókat a Teams és a pénztár (POS) alkalmazás között, akkor engedélyeznie kell a Commerce központi felületének integrációs funkcióit.</span><span class="sxs-lookup"><span data-stu-id="e17d2-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="e17d2-106">Amikor engedélyezi a Teams integrációját, hozzájárul ahhoz, hogy adatait megossza a Teams alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="e17d2-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="e17d2-107">Előfordulhat, hogy a Teams alkalmazással megosztott adatok a Commerce-adatoktól eltérő országban találhatók, és eltérő megfelelőségi szabványok vonatkoznak rájuk.</span><span class="sxs-lookup"><span data-stu-id="e17d2-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="e17d2-108">A további tudnivalókat lásd: [Microsoft megbízhatósági központ](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="e17d2-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="e17d2-109">A Microsoft adatvédelmi irányelveit a [Microsoft adatvédelmi nyilatkozatában](https://aka.ms/privacy) találja.</span><span class="sxs-lookup"><span data-stu-id="e17d2-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="e17d2-110">A Teams-integráció engedélyezése</span><span class="sxs-lookup"><span data-stu-id="e17d2-110">Enable Teams integration</span></span>

<span data-ttu-id="e17d2-111">A Microsoft Teams és a Commerce integrációjának engedélyezése előtt regisztrálnia kell a Teams alkalmazást a bérlővel az Azure Portalon.</span><span class="sxs-lookup"><span data-stu-id="e17d2-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="e17d2-112">A Teams alkalmazásnak a bérlővel való regisztrálásához az Azure Portalon, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e17d2-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="e17d2-113">A Teams alkalmazás Azure Portalon található bérlőjével történő regisztrálásához kövesse a következő lépéseit: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="e17d2-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="e17d2-114">Másolja az **Alkalmazás (ügyfél) azonosítója** értékét a regisztrált alkalmazás **Áttekintés** lapjára.</span><span class="sxs-lookup"><span data-stu-id="e17d2-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="e17d2-115">Ezt az értéket arra fogja használni, hogy lehetővé tegye a Teams integrációját a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="e17d2-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="e17d2-116">Másolja a tanúsítvány értékét, amely az 1. lépésben, a [tanúsítvány hozzáadásakor](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) lett megadva.</span><span class="sxs-lookup"><span data-stu-id="e17d2-116">Copy the certificate value that was entered when you [added a certificate](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="e17d2-117">A tanúsítvány nyilvános kulcsként vagy alkalmazáskulcsként is ismert.</span><span class="sxs-lookup"><span data-stu-id="e17d2-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="e17d2-118">Ezt az értéket arra fogja használni, hogy lehetővé tegye a Teams integrációját a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="e17d2-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="e17d2-119">A Teams integráció engedélyezéséhez a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e17d2-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e17d2-120">Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="e17d2-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="e17d2-121">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e17d2-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e17d2-122">Állítsa a **Microsoft Teams-integráció engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e17d2-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="e17d2-123">Az **Alkalmazásazonosító** és **Alkalmazáskulcs** mezőkben adja meg a Teams alkalmazás Azure Portalon való regisztrálásakor kapott értékeket.</span><span class="sxs-lookup"><span data-stu-id="e17d2-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="e17d2-124">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e17d2-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="e17d2-125">Az alábbi ábra egy példát mutat be a Teams integrációs konfigurációjáról a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="e17d2-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Teams-integráció konfigurációja a Commerce központi felületén](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="e17d2-127">A Teams-integráció letiltása</span><span class="sxs-lookup"><span data-stu-id="e17d2-127">Disable Teams integration</span></span>

<span data-ttu-id="e17d2-128">A Microsoft Teams-integráció letiltásához a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e17d2-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e17d2-129">Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="e17d2-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="e17d2-130">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e17d2-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="e17d2-131">Állítsa a **Microsoft Teams-integráció engedélyezése** beállítást **Nem** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e17d2-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="e17d2-132">Törölje az értékeket az **Alkalmazásazonosító** és az **Alkalmazáskulcs** mezőkből.</span><span class="sxs-lookup"><span data-stu-id="e17d2-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="e17d2-133">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e17d2-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e17d2-134">A Teams Commerce szolgáltatással való integrációjának letiltása után a POS-terminálok a továbbiakban nem jelenítik meg a Teams alkalmazásból közzétett feladatokat.</span><span class="sxs-lookup"><span data-stu-id="e17d2-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e17d2-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e17d2-135">Additional resources</span></span>

[<span data-ttu-id="e17d2-136">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="e17d2-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="e17d2-137">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="e17d2-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="e17d2-138">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="e17d2-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="e17d2-139">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="e17d2-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="e17d2-140">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="e17d2-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="e17d2-141">Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK</span><span class="sxs-lookup"><span data-stu-id="e17d2-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
