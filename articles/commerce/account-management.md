---
title: Fiókkezelési lapok és modulok
description: Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.
author: v-chgri
manager: annbe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f9fc3731cd9d21294b0161e1d419f255096d7790
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885809"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="ec2f0-103">Fiókkezelési lapok és modulok</span><span class="sxs-lookup"><span data-stu-id="ec2f0-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ec2f0-104">Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ec2f0-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ec2f0-105">Overview</span></span>

<span data-ttu-id="ec2f0-106">A fiókkezelési lapok egy csoportjára vonatkozik, amelyek a felhasználói fiókkal kapcsolatos információk kezelésére szolgálnak a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="ec2f0-107">A fiókkezelési lapok közé tartozik a fiókkezelés nyitólapja, a felhasználói profil lapja, a felhasználói cím lapja, a rendeléselőzmények lapja, a rendelés részleteinek lapja, a hűségprogram lapja és a kívánságlista lapja.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="ec2f0-108">A fiókkezelés érkezési oldala</span><span class="sxs-lookup"><span data-stu-id="ec2f0-108">Account management landing page</span></span>

<span data-ttu-id="ec2f0-109">A fiókkezelés nyitólapja a következő modulokat használja:</span><span class="sxs-lookup"><span data-stu-id="ec2f0-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="ec2f0-110">**Tartalomelhelyezés** – Ez a modul egy tárolómodul, amely a fiókkezelés nyitólapjának összes modulját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="ec2f0-111">**Fiók üdvözlőeleme** – Ez a modul a fiókkezelési lap üdvözlő üzenetének biztosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="ec2f0-112">A fejlécre és a csempeméretre vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="ec2f0-113">A **Csempeméret** tulajdonság meghatározza a modul szélességét a tartalomelhelyezési modulban.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="ec2f0-114">Az értékek **1** és **12** között lehetnek, ahol a **12** a tartalomelhelyezési tároló teljes szélességét jelenti.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="ec2f0-115">**Fiók rendelésleadási eleme** – Ez a modul a felhasználói fiók által leadott rendelések számának összefoglalására szolgál.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="ec2f0-116">A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ec2f0-117">A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a rendeléselőzmények lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="ec2f0-118">**Fiók profil elhelyezési eleme** – Ez a modul a felhasználói profil összesítését biztosítja.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="ec2f0-119">A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ec2f0-120">A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a felhasználói profil lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="ec2f0-121">**Fiók kívánságlista eleme** – Ez a modul a vevői kívánságlistán szereplő cikkek összesítését biztosítja.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="ec2f0-122">Előfordulhat például, hogy a „10 cikk szerepel a kívánságlistáján.” felirat látható.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="ec2f0-123">A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ec2f0-124">A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a kívánságlista lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="ec2f0-125">**Fiók cím eleme** – Ez a modul a felhasználó címének összefoglalóját biztosítja.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="ec2f0-126">Előfordulhat például, hogy itt a „2 cím van hozzáadva a fiókjához.” üzenet látható.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="ec2f0-127">A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ec2f0-128">A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a felhasználó címe lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="ec2f0-129">**Fiók hűségprogram elem** – Ez a modul a hűségprogrammal kapcsolatos információk megjelenítésére és hivatkozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="ec2f0-130">A fejlécre, a csempeméretre, a „részletek megtekintése” hivatkozásra és a „legyen tag” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="ec2f0-131">A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a hűségprogram lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="ec2f0-132">A „legyen tag„ hivatkozást úgy kell beállítani, hogy egy olyan lapra irányítson át, amelyen a felhasználók csatlakozhatnak a hűségprogramhoz.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="ec2f0-133">Rendeléselőzmények lap</span><span class="sxs-lookup"><span data-stu-id="ec2f0-133">Order history page</span></span>

<span data-ttu-id="ec2f0-134">A rendeléselőzmények lap a rendeléselőzmények modulban jeleníti meg a felhasználó által a közelmúltban leadott összes rendelést.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="ec2f0-135">Rendelés részleteit tartalmazó oldal</span><span class="sxs-lookup"><span data-stu-id="ec2f0-135">Order details page</span></span>

<span data-ttu-id="ec2f0-136">A rendelés részletei lap részletes adatokat tartalmaz minden rendelésről, és elérhető a rendeléselőzmények lapról.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="ec2f0-137">A rendelés részletei modult használja, amely az értékesítési azonosító vagy a tranzakció azonosítója segítségével kéri le a rendelés részleteit.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="ec2f0-138">Felhasználói profil lap</span><span class="sxs-lookup"><span data-stu-id="ec2f0-138">User profile page</span></span>

<span data-ttu-id="ec2f0-139">A felhasználói profil lap a felhasználói fiók adatait jeleníti meg, például a felhasználó nevét és e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-139">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="ec2f0-140">A felhasználói profil modult használja.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-140">It uses the user profile module.</span></span> <span data-ttu-id="ec2f0-141">Annak ellenére, hogy az e-mail-cím nem távolítható el, lehetőség van a szerkesztésére.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-141">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="ec2f0-142">A felhasználói profiloldal megjeleníti a felhasználói beállításokat is, amelyek lehetővé teszik, hogy a felhasználó fel- vagy leiratkozzon bizonyos szolgáltatásokról, mint a testreszabás vagy a javaslatok listája.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-142">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="ec2f0-143">Felhasználó címe lap</span><span class="sxs-lookup"><span data-stu-id="ec2f0-143">User address page</span></span>

<span data-ttu-id="ec2f0-144">A felhasználó címe lapon látható a felhasználói fiókhoz társított címek listája.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-144">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="ec2f0-145">A felhasználó vagy a fizetés során adta meg a címeit, vagy közvetlenül ezen az oldalon.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-145">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="ec2f0-146">A felhasználói cím modul a címek hozzáadására és szerkesztésére, az elsődleges cím beállítására, valamint a meglévő címek megjelenítésére szolgál a lapon.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-146">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="ec2f0-147">Kívánságlista lap</span><span class="sxs-lookup"><span data-stu-id="ec2f0-147">Wish list page</span></span>

<span data-ttu-id="ec2f0-148">A kívánságlista lap megjeleníti azokat a cikkeket, amelyeket hozzáadtak a vevői kívánságlistához.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-148">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="ec2f0-149">A kívánságlista modult használja a kívánságlistán szereplő cikkek megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-149">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="ec2f0-150">Hűségprogram oldala</span><span class="sxs-lookup"><span data-stu-id="ec2f0-150">Loyalty page</span></span>

<span data-ttu-id="ec2f0-151">A hűségprogram lapon a vevők csatlakozhatnak egy hűségprogramhoz, vagy ha már tagok egy hűségprogramban, megtekinthetik a programjuk részleteit.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-151">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="ec2f0-152">Megtekinthetik a legutóbbi tranzakciók során az általuk gyűjtött és beváltott pontokat is.</span><span class="sxs-lookup"><span data-stu-id="ec2f0-152">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec2f0-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ec2f0-153">Additional resources</span></span>

[<span data-ttu-id="ec2f0-154">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="ec2f0-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ec2f0-155">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ec2f0-156">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ec2f0-157">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ec2f0-158">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ec2f0-159">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ec2f0-160">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ec2f0-161">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="ec2f0-161">Footer module</span></span>](author-footer-module.md)
