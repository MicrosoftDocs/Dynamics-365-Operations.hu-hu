---
title: Ajándékutalvány-modul
description: Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b7d28e041b8adc828a2447ab09a0c1d28cc2aec0
ms.sourcegitcommit: 69075e001d1fb4ef69282667052cd8d082273094
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022005"
---
# <a name="gift-card-module"></a><span data-ttu-id="d4d1a-103">Ajándékutalvány-modul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d4d1a-104">Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d4d1a-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d4d1a-105">Overview</span></span>

<span data-ttu-id="d4d1a-106">Az ajándékutalvány egy gyakori fizetési mód, és az ajándékutalvány modulok használható az e-kereskedelmi tranzakciókban az ajándékutalványok elfogadására.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="d4d1a-107">Az ajándékutalvány modul támogatja a Dynamics 365, SVS és a Givex ajándékutalványokat.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="d4d1a-108">A SVS és a Givex ajándékutalványok a Adyen fizetési szolgáltatón keresztül válthatók be.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="d4d1a-109">A külső ajándékutalványok (például SVS és Givex) támogatásával kapcsolatos további tudnivalókat lásd: [Támogatás a külső ajándékutalványokhoz](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="d4d1a-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d4d1a-110">A pénztári folyamat során történő SVS- és Givex-ajándékutalvány beváltásához nyújtott támogatás a Dynamics 365 Commerce 10.0.11-es kiadásban érhető el.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="d4d1a-111">Két ajándékutalvány-modul érhető el:</span><span class="sxs-lookup"><span data-stu-id="d4d1a-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="d4d1a-112">**Ajándékutalvány** – Ez a modul a pénztár oldalon használható egy ajándékutalvány fizetőeszközként történő beváltására.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="d4d1a-113">**Ajándékutalvány egyenlegének ellenőrzése** – Ez a modul bármilyen oldalon használható az ajándékutalvány egyenlegének ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="d4d1a-114">Ez a modul elérhető a Commerce alkalmazás 10.0.14 vagy újabb verziójában.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="d4d1a-115">Az ajándékutalvány-egyenleget ellenőrző modul támogatása a Dynamics 365 Commerce 10.0.14-es kiadásában érhető el.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="d4d1a-116">A következő kép egy Pénztár oldalon használt ajándékutalvány modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Példa egy ajándékutalvány modulra](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="d4d1a-118">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="d4d1a-118">Module properties</span></span>

- <span data-ttu-id="d4d1a-119">**További mezők megjelenítése** – Ez a tulajdonság határozza meg, hogy milyen mezőket kell megjeleníteni az ajándékutalványokhozaz ajándékutalvány számán túl, amely alapértelmezés szerint mindig látható.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="d4d1a-120">Például egyes ajándékutalványok támogatják a személyes azonosítószám (PIN-kód) megjelenítését, mások a PIN-kód és a lejárati dátum megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="d4d1a-121">Másik lehetőségként a tulajdonság értéke „Nincs” lehet, amely csak az ajándékutalvány számát jeleníti meg, és további mezőket nem.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="d4d1a-122">Támogatott értékek:</span><span class="sxs-lookup"><span data-stu-id="d4d1a-122">Supported values:</span></span>
-   <span data-ttu-id="d4d1a-123">PIN-kód</span><span class="sxs-lookup"><span data-stu-id="d4d1a-123">PIN</span></span>
-   <span data-ttu-id="d4d1a-124">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="d4d1a-124">Expiration date</span></span>
-   <span data-ttu-id="d4d1a-125">PIN és lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="d4d1a-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="d4d1a-126">None</span><span class="sxs-lookup"><span data-stu-id="d4d1a-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="d4d1a-127">Ajándékutalvány-modulok webhely-beállításai</span><span class="sxs-lookup"><span data-stu-id="d4d1a-127">Site settings for gift card modules</span></span>

<span data-ttu-id="d4d1a-128">A Commerce webhelykészítő **Webhelybeállítások \> Bővítmények** területén van egy ajándékutalvány-modul, amelynek neve **Támogatott ajándékutalvány-típus**.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-128">In Commerce site builder under **Site Settings \> Extensions** , there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="d4d1a-129">Ez a beállítás három értéket támogat:</span><span class="sxs-lookup"><span data-stu-id="d4d1a-129">This setting supports three values:</span></span>
- <span data-ttu-id="d4d1a-130">**Dynamics 365 ajándékutalvány** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Dynamics 365 utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="d4d1a-131">Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="d4d1a-132">**SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Givex és SVS utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="d4d1a-133">Ez a beállítás az e-Commerce webhely bejelentkezett és névtelen felhasználói esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="d4d1a-134">**Dynamics 365, SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul a Dynamics 365, Givex és SVS utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="d4d1a-135">Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4d1a-136">Ezek a beállítások a Dynamics 365 Commerce 10.0.11-es verziójában érhetők el, és csak akkor szükségesek, ha támogatásra van szüksége az SVS- vagy Givex-ajándékutalványok használatakor.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="d4d1a-137">Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="d4d1a-138">Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben.</span><span class="sxs-lookup"><span data-stu-id="d4d1a-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="d4d1a-139">Ajándékutalvány-modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="d4d1a-139">Add a gift card module to a page</span></span>

<span data-ttu-id="d4d1a-140">Az ajándékutalvány-modulnak a pénztár lapra történő hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetésmodul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="d4d1a-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4d1a-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d4d1a-141">Additional resources</span></span>

[<span data-ttu-id="d4d1a-142">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d4d1a-143">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="d4d1a-144">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d4d1a-145">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="d4d1a-146">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="d4d1a-147">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="d4d1a-148">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="d4d1a-148">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="d4d1a-149">Támogatás külső ajándékutalványokhoz</span><span class="sxs-lookup"><span data-stu-id="d4d1a-149">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="d4d1a-150">SDK- és modulkönyvtár-frissítések</span><span class="sxs-lookup"><span data-stu-id="d4d1a-150">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
