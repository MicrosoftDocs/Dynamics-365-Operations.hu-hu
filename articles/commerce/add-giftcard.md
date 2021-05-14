---
title: Ajándékutalvány-modul
description: Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962763"
---
# <a name="gift-card-module"></a><span data-ttu-id="937b7-103">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="937b7-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="937b7-104">Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="937b7-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="937b7-105">Az ajándékutalvány egy gyakori fizetési mód, és az ajándékutalvány modulok használható az e-kereskedelmi tranzakciókban az ajándékutalványok elfogadására.</span><span class="sxs-lookup"><span data-stu-id="937b7-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="937b7-106">Az ajándékutalvány modul támogatja a Dynamics 365, SVS és a Givex ajándékutalványokat.</span><span class="sxs-lookup"><span data-stu-id="937b7-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="937b7-107">A SVS és a Givex ajándékutalványok a Adyen fizetési szolgáltatón keresztül válthatók be.</span><span class="sxs-lookup"><span data-stu-id="937b7-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="937b7-108">A külső ajándékutalványok (például SVS és Givex) támogatásával kapcsolatos további tudnivalókat lásd: [Támogatás a külső ajándékutalványokhoz](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="937b7-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="937b7-109">A pénztári folyamat során történő SVS- és Givex-ajándékutalvány beváltásához nyújtott támogatás a Dynamics 365 Commerce 10.0.11-es kiadásban érhető el.</span><span class="sxs-lookup"><span data-stu-id="937b7-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="937b7-110">Két ajándékutalvány-modul érhető el:</span><span class="sxs-lookup"><span data-stu-id="937b7-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="937b7-111">**Ajándékutalvány** – Ez a modul a pénztár oldalon használható egy ajándékutalvány fizetőeszközként történő beváltására.</span><span class="sxs-lookup"><span data-stu-id="937b7-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="937b7-112">**Ajándékutalvány egyenlegének ellenőrzése** – Ez a modul bármilyen oldalon használható az ajándékutalvány egyenlegének ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="937b7-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="937b7-113">Ez a modul elérhető a Commerce alkalmazás 10.0.14 vagy újabb verziójában.</span><span class="sxs-lookup"><span data-stu-id="937b7-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="937b7-114">Az ajándékutalvány-egyenleget ellenőrző modul támogatása a Dynamics 365 Commerce 10.0.14-es kiadásában érhető el.</span><span class="sxs-lookup"><span data-stu-id="937b7-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="937b7-115">A következő kép egy Pénztár oldalon használt ajándékutalvány modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="937b7-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Példa egy ajándékutalvány modulra](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="937b7-117">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="937b7-117">Module properties</span></span>

- <span data-ttu-id="937b7-118">**További mezők megjelenítése** – Ez a tulajdonság határozza meg, hogy milyen mezőket kell megjeleníteni az ajándékutalványokhozaz ajándékutalvány számán túl, amely alapértelmezés szerint mindig látható.</span><span class="sxs-lookup"><span data-stu-id="937b7-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="937b7-119">Például egyes ajándékutalványok támogatják a személyes azonosítószám (PIN-kód) megjelenítését, mások a PIN-kód és a lejárati dátum megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="937b7-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="937b7-120">Másik lehetőségként a tulajdonság értéke „Nincs” lehet, amely csak az ajándékutalvány számát jeleníti meg, és további mezőket nem.</span><span class="sxs-lookup"><span data-stu-id="937b7-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="937b7-121">Támogatott értékek:</span><span class="sxs-lookup"><span data-stu-id="937b7-121">Supported values:</span></span>
-   <span data-ttu-id="937b7-122">PIN-kód</span><span class="sxs-lookup"><span data-stu-id="937b7-122">PIN</span></span>
-   <span data-ttu-id="937b7-123">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="937b7-123">Expiration date</span></span>
-   <span data-ttu-id="937b7-124">PIN és lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="937b7-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="937b7-125">None</span><span class="sxs-lookup"><span data-stu-id="937b7-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="937b7-126">Ajándékutalvány-modulok webhely-beállításai</span><span class="sxs-lookup"><span data-stu-id="937b7-126">Site settings for gift card modules</span></span>

<span data-ttu-id="937b7-127">A Commerce webhelykészítő **Webhelybeállítások \> Bővítmények** területén van egy ajándékutalvány-modul, amelynek neve **Támogatott ajándékutalvány-típus**.</span><span class="sxs-lookup"><span data-stu-id="937b7-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="937b7-128">Ez a beállítás három értéket támogat:</span><span class="sxs-lookup"><span data-stu-id="937b7-128">This setting supports three values:</span></span>
- <span data-ttu-id="937b7-129">**Dynamics 365 ajándékutalvány** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Dynamics 365 utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="937b7-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="937b7-130">Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="937b7-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="937b7-131">**SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Givex és SVS utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="937b7-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="937b7-132">Ez a beállítás az e-Commerce webhely bejelentkezett és névtelen felhasználói esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="937b7-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="937b7-133">**Dynamics 365, SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul a Dynamics 365, Givex és SVS utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="937b7-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="937b7-134">Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="937b7-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="937b7-135">Ezek a beállítások a Dynamics 365 Commerce 10.0.11-es verziójában érhetők el, és csak akkor szükségesek, ha támogatásra van szüksége az SVS- vagy Givex-ajándékutalványok használatakor.</span><span class="sxs-lookup"><span data-stu-id="937b7-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="937b7-136">Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt.</span><span class="sxs-lookup"><span data-stu-id="937b7-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="937b7-137">Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben.</span><span class="sxs-lookup"><span data-stu-id="937b7-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="937b7-138">Belső ajándékutalványok kiterjesztése az e-kereskedelmi áruházakban való használatra</span><span class="sxs-lookup"><span data-stu-id="937b7-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="937b7-139">Alapértelmezés szerint a belső ajándékutalványok nincsenek az e-kereskedelmi üzletben való használatra optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="937b7-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="937b7-140">Ezért mielőtt engedélyezné, hogy a belső ajándékutalványok használhatók legyenek fizetésre, be kell állítania azokat a bővítményeket, amelyek biztonságossá teszik őket.</span><span class="sxs-lookup"><span data-stu-id="937b7-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="937b7-141">Itt vannak azok az ajándékutalvány-területek, amelyek a belső ajándékutalványok termelésben való használatának engedélyezése előtt bővítenie kell:</span><span class="sxs-lookup"><span data-stu-id="937b7-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="937b7-142">**Ajándékutalvány száma** – A számsorozatok a belső ajándékutalványok ajándékutalvány-számának előállítására használhatók.</span><span class="sxs-lookup"><span data-stu-id="937b7-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="937b7-143">Mivel a számsorozatok könnyen kitalálhatók, ki kell terjesztenie az ajándékutalvány-számok létrehozását úgy, hogy a kiadott ajándékutalvány-számokhoz véletlenszerű, kriptográfiai szempontból biztonságos sztringeket használjon.</span><span class="sxs-lookup"><span data-stu-id="937b7-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="937b7-144">**GetBalance** – a **GetBalance** API használatával lehet megkeresni az ajándékutalvány-egyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="937b7-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="937b7-145">Alapértelmezés szerint ez az API nyilvános.</span><span class="sxs-lookup"><span data-stu-id="937b7-145">By default, this API public.</span></span> <span data-ttu-id="937b7-146">Ha nincs szükség PIN-kódra az ajándékutalvány-egyenlegek kereséséhez, kockázatot jelent, hogy a találgatásos támadások a **GetBalance** API-t használják az egyenleget tartalmazó ajándékutalványok számainak megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="937b7-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="937b7-147">A belső ajándékutalványokra és API-szabályozásra vonatkozó PIN-követelmények megvalósításával csökkenthető a kockázat.</span><span class="sxs-lookup"><span data-stu-id="937b7-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="937b7-148">**PIN** - Alapértelmezés szerint a belső ajándékutalványok nem támogatják a PIN-kódokat.</span><span class="sxs-lookup"><span data-stu-id="937b7-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="937b7-149">A belső ajándékutalványokat ki kell terjeszteni, hogy az egyenlegek ellenőrzéséhez PIN-kód legyen szükséges.</span><span class="sxs-lookup"><span data-stu-id="937b7-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="937b7-150">Ez a funkció az ajándékutalványok zárolására is használható, ha egymás után több helytelen kísérlet történt a PIN-kód megadására.</span><span class="sxs-lookup"><span data-stu-id="937b7-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="937b7-151">Ajándékutalványos fizetések engedélyezése vendégkifizetéshez</span><span class="sxs-lookup"><span data-stu-id="937b7-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="937b7-152">Alapértelmezés szerint a vendég (névtelen) fizetésnél az ajándékutalványos fizetések nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="937b7-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="937b7-153">Kövesse az alábbi lépéseket az engedélyezésükhöz.</span><span class="sxs-lookup"><span data-stu-id="937b7-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="937b7-154">A Commerce központi felületén lépjen a **Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="937b7-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="937b7-155">Válassza ki és tartsa lenyomva a rács fejlécét (vagy kattintson rá a jobb gombbal), majd válassza az **Oszlopok beszúrása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="937b7-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="937b7-156">Az **Oszlopok beszúrása** párbeszédpanelen jelölje be az **AllowAnonymousAccess** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="937b7-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="937b7-157">Válassza ki a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="937b7-157">Select **Update**.</span></span>
1. <span data-ttu-id="937b7-158">Az **520** (Ajándékutalván egyenlege) és **214** műveleteknél állítsa az **AllowAnonymousAccess** értékét **1**-re.</span><span class="sxs-lookup"><span data-stu-id="937b7-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="937b7-159">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="937b7-159">Select **Save**.</span></span>
1. <span data-ttu-id="937b7-160">Futtassa az **1090** ütemezési feladatot a módosítások szinkronizálására a csatornaadatbázisba.</span><span class="sxs-lookup"><span data-stu-id="937b7-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="937b7-161">Ajándékutalvány-modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="937b7-161">Add a gift card module to a page</span></span>

<span data-ttu-id="937b7-162">Az ajándékutalvány-modulnak a pénztár lapra történő hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetésmodul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="937b7-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="937b7-163">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="937b7-163">Additional resources</span></span>

[<span data-ttu-id="937b7-164">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="937b7-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="937b7-165">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="937b7-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="937b7-166">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="937b7-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="937b7-167">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="937b7-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="937b7-168">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="937b7-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="937b7-169">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="937b7-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="937b7-170">Átvételi információk modul</span><span class="sxs-lookup"><span data-stu-id="937b7-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="937b7-171">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="937b7-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="937b7-172">Támogatás külső ajándékutalványokhoz</span><span class="sxs-lookup"><span data-stu-id="937b7-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="937b7-173">SDK- és modulkönyvtár-frissítések</span><span class="sxs-lookup"><span data-stu-id="937b7-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
