---
title: Számlakezelési oldalak és modulok
description: Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 29523d03fb687684dae7d0ce08208905cce702df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206631"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="8ec90-103">Számlakezelési oldalak és modulok</span><span class="sxs-lookup"><span data-stu-id="8ec90-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8ec90-104">Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8ec90-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8ec90-105">A fiókkezelési lapok egy csoportjára vonatkozik, amelyek a felhasználói fiókkal kapcsolatos információk kezelésére szolgálnak a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8ec90-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="8ec90-106">A fiókkezelési lapok közé tartozik a fiókkezelés nyitólapja, a felhasználói profil lapja, a felhasználói cím lapja, a rendeléselőzmények lapja, a rendelés részleteinek lapja, a hűségprogram lapja és a kívánságlista lapja.</span><span class="sxs-lookup"><span data-stu-id="8ec90-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="8ec90-107">A fiókkezelés érkezési oldala</span><span class="sxs-lookup"><span data-stu-id="8ec90-107">Account management landing page</span></span>

<span data-ttu-id="8ec90-108">A fiókkezelés nyitólapja a következő modulokat használja:</span><span class="sxs-lookup"><span data-stu-id="8ec90-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="8ec90-109">**Tároló** – az összes számlavezetési oldalmodult egy tárolón belül kell elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="8ec90-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="8ec90-110">**Számla üdvözlőcsempéje** – Ez a modul a számlavezetési lap üdvözlő üzenetének biztosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="8ec90-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="8ec90-111">A címsorhoz tartozó tulajdonságokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="8ec90-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="8ec90-112">**Számla általános csempéje** – ez a modul a számlavezetés oldalakhoz, például a "rendelési előzmények" vagy a "saját profil" oldalakhoz való hivatkozások biztosítására használható.</span><span class="sxs-lookup"><span data-stu-id="8ec90-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="8ec90-113">Az általános csempe modul bármely lap csempéjének konfigurálására használható.</span><span class="sxs-lookup"><span data-stu-id="8ec90-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="8ec90-114">A Fabrikamnál ez a modul a számlavezetés nyitóoldala "Order History" és "saját profil" hivatkozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="8ec90-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="8ec90-115">**Számla kívánságlista csempéje** – Ez a modul a vevői kívánságlistán szereplő cikkek összesítését biztosítja.</span><span class="sxs-lookup"><span data-stu-id="8ec90-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="8ec90-116">Előfordulhat például, hogy a „10 cikk szerepel a kívánságlistáján.” felirat látható.</span><span class="sxs-lookup"><span data-stu-id="8ec90-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="8ec90-117">A címsorra és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="8ec90-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="8ec90-118">A „Részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a kívánságlista lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="8ec90-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="8ec90-119">**Számla címcsempéje** – Ez a modul a felhasználó címének összefoglalóját biztosítja.</span><span class="sxs-lookup"><span data-stu-id="8ec90-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="8ec90-120">Előfordulhat például, hogy itt a „2 cím van hozzáadva a fiókjához.” üzenet látható.</span><span class="sxs-lookup"><span data-stu-id="8ec90-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="8ec90-121">A címsorra és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="8ec90-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="8ec90-122">A „Részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a felhasználó címe lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="8ec90-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="8ec90-123">**Számla hűségprogram csempe** – Ez a modul a hűségprogrammal kapcsolatos információk megjelenítésére és hivatkozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="8ec90-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="8ec90-124">Ennek a csempének két állapota van: egy állapot a hűségprogramhoz való csatlakozásra mutató hivatkozásokat mutat be, ha a felhasználó még nem tagja.</span><span class="sxs-lookup"><span data-stu-id="8ec90-124">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="8ec90-125">A másik állapot olyan hivatkozásokat mutat be, amelyek a hűségprogram részleteinak lapját jelenítik meg, ha a felhasználó már tag.</span><span class="sxs-lookup"><span data-stu-id="8ec90-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="8ec90-126">A tulajdonságok között szerepel a címsor, a "Feliratkozás" hivatkozás, valamint a "hűségprogram megtekintése" hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="8ec90-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="8ec90-127">A „Hűségprogram megtekintése” hivatkozást úgy kell konfigurálni, hogy a hűségprogram lapra irányítson át.</span><span class="sxs-lookup"><span data-stu-id="8ec90-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="8ec90-128">A „Feliratkozás” hivatkozást úgy kell beállítani, hogy egy olyan lapra irányítson át, amelyen a felhasználók csatlakozhatnak a hűségprogramhoz.</span><span class="sxs-lookup"><span data-stu-id="8ec90-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="8ec90-129">Rendeléselőzmények lap</span><span class="sxs-lookup"><span data-stu-id="8ec90-129">Order history page</span></span>

<span data-ttu-id="8ec90-130">A rendeléselőzmények lap a rendeléselőzmények modulban jeleníti meg a felhasználó által a közelmúltban leadott összes rendelést.</span><span class="sxs-lookup"><span data-stu-id="8ec90-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="8ec90-131">Rendelés részleteit tartalmazó oldal</span><span class="sxs-lookup"><span data-stu-id="8ec90-131">Order details page</span></span>

<span data-ttu-id="8ec90-132">A rendelés részletei lap részletes adatokat tartalmaz minden rendelésről, és elérhető a rendeléselőzmények lapról.</span><span class="sxs-lookup"><span data-stu-id="8ec90-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="8ec90-133">A rendelés részletei modult használja, amely az értékesítési azonosító vagy a tranzakció azonosítója segítségével kéri le a rendelés részleteit.</span><span class="sxs-lookup"><span data-stu-id="8ec90-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="8ec90-134">Felhasználói profil lap</span><span class="sxs-lookup"><span data-stu-id="8ec90-134">User profile page</span></span>

<span data-ttu-id="8ec90-135">A felhasználói profil lap a felhasználói fiók adatait jeleníti meg, például a felhasználó nevét és e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="8ec90-135">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="8ec90-136">A felhasználói profil adatait és a felhasználói profilok szerkesztési modulját használja.</span><span class="sxs-lookup"><span data-stu-id="8ec90-136">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="8ec90-137">Annak ellenére, hogy az e-mail-cím nem távolítható el, lehetőség van a szerkesztésére.</span><span class="sxs-lookup"><span data-stu-id="8ec90-137">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="8ec90-138">A felhasználói profiloldal megjeleníti a felhasználói beállításokat is, amelyek lehetővé teszik, hogy a felhasználó fel- vagy leiratkozzon bizonyos szolgáltatásokról, mint a testreszabás vagy a javaslatok listája.</span><span class="sxs-lookup"><span data-stu-id="8ec90-138">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="8ec90-139">Felhasználó címe lap</span><span class="sxs-lookup"><span data-stu-id="8ec90-139">User address page</span></span>

<span data-ttu-id="8ec90-140">A felhasználó címe lapon látható a felhasználói fiókhoz társított címek listája.</span><span class="sxs-lookup"><span data-stu-id="8ec90-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="8ec90-141">A felhasználó vagy a fizetés során adta meg a címeit, vagy közvetlenül ezen az oldalon.</span><span class="sxs-lookup"><span data-stu-id="8ec90-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="8ec90-142">A felhasználói cím modul a címek hozzáadására és szerkesztésére, az elsődleges cím beállítására, valamint a meglévő címek megjelenítésére szolgál a lapon.</span><span class="sxs-lookup"><span data-stu-id="8ec90-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="8ec90-143">Kívánságlista lap</span><span class="sxs-lookup"><span data-stu-id="8ec90-143">Wish list page</span></span>

<span data-ttu-id="8ec90-144">A kívánságlista lap megjeleníti azokat a cikkeket, amelyeket hozzáadtak a vevői kívánságlistához.</span><span class="sxs-lookup"><span data-stu-id="8ec90-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="8ec90-145">A kívánságlista modult használja a kívánságlistán szereplő cikkek megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8ec90-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="8ec90-146">Hűségprogram oldala</span><span class="sxs-lookup"><span data-stu-id="8ec90-146">Loyalty page</span></span>

<span data-ttu-id="8ec90-147">A hűségprogram lapon a vevők megtekinthetik a hűségprogramjuk részleteit, ha már tagok egy hűségprogramban.</span><span class="sxs-lookup"><span data-stu-id="8ec90-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="8ec90-148">Megtekinthetik a legutóbbi tranzakciók során az általuk gyűjtött és beváltott pontokat is.</span><span class="sxs-lookup"><span data-stu-id="8ec90-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="8ec90-149">A lap a hűségprogram részletei modulban bemutatja a hűségprogram adatait.</span><span class="sxs-lookup"><span data-stu-id="8ec90-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="8ec90-150">A hűségprogramhoz való csatlakozáshoz létre lehet hozni egy marketinges lapot a hűségprogramra való feliratkozás és a hűségprogram feltételei modulokkal.</span><span class="sxs-lookup"><span data-stu-id="8ec90-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="8ec90-151">Ha a felhasználó nem tagja egy hűségprogramnak, akkor ezek a modulok lehetővé teszik a felhasználó számára a feliratkozást.</span><span class="sxs-lookup"><span data-stu-id="8ec90-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ec90-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8ec90-152">Additional resources</span></span>

[<span data-ttu-id="8ec90-153">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="8ec90-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8ec90-154">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="8ec90-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8ec90-155">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="8ec90-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8ec90-156">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="8ec90-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8ec90-157">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="8ec90-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8ec90-158">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="8ec90-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8ec90-159">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="8ec90-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8ec90-160">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="8ec90-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]