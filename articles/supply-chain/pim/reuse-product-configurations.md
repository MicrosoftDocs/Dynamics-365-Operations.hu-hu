---
title: "Termékkonfigurációk újrahasználása"
description: "Megadhatja, hogy szeretne-e automatikusan újrahasználni egy meglévő konfigurációt egy termékhez. Miután a felhasználó befejezte a konfigurációs munkamenetet, a rendszer ellenőrzi, hogy létezik-e már a felhasználói beállításokkal megegyező konfiguráció. Ha a rendszer talál megfelelő konfigurációt, újból felhasználásra kerül a Konfigurációazonosító, a megfelelő anyagjegyzék (AJ) és az útvonal."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4d61c869577a3e18d1ac951f32dae286937a51c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="reuse-product-configurations"></a><span data-ttu-id="7ce89-105">Termékkonfigurációk újrahasználása</span><span class="sxs-lookup"><span data-stu-id="7ce89-105">Reuse product configurations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7ce89-106">Megadhatja, hogy szeretne-e automatikusan újrahasználni egy meglévő konfigurációt egy termékhez.</span><span class="sxs-lookup"><span data-stu-id="7ce89-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="7ce89-107">Miután a felhasználó befejezte a konfigurációs munkamenetet, a rendszer ellenőrzi, hogy létezik-e már a felhasználói beállításokkal megegyező konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="7ce89-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="7ce89-108">Ha a rendszer talál megfelelő konfigurációt, újból felhasználásra kerül a Konfigurációazonosító, a megfelelő anyagjegyzék (AJ) és az útvonal.</span><span class="sxs-lookup"><span data-stu-id="7ce89-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="7ce89-109">Konfigurációk újbóli használatának feltételei</span><span class="sxs-lookup"><span data-stu-id="7ce89-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="7ce89-110">A konfigurációk újbóli felhasználásához meg kell adnia az összetevőkre és az attribútumokra vonatkozó következő adatokat a **Termékkonfigurálási modell részletei**lapon:</span><span class="sxs-lookup"><span data-stu-id="7ce89-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="7ce89-111">**Összetevők és alösszetevők** – az **Általános** gyorslapon a **Konfigurációk újbóli használata** mezőben válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ce89-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="7ce89-112">**Attribútumok** – az **Attribútumok** gyorslapon jelölje be a **Felvétel az újrahasználhatók közé** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ce89-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="7ce89-113">Ez a lehetőség csak akkor jelenik meg, ha a kapcsolódó összetevő újbóli felhasználása engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="7ce89-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="7ce89-114">Amennyiben nem választ ki újból felhasználandó attribútumokat, a konfigurációt mindig újból felhasználja a rendszer, függetlenül a konfigurációs munkamenet során végzett felhasználói beállításoktól.</span><span class="sxs-lookup"><span data-stu-id="7ce89-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="7ce89-115">A meglévő konfiguráció termékattribútum-értékeinek meg kell egyeznie a felhasználói beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="7ce89-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="7ce89-116">Ha például egy felhasználó a konfigurációs munkamenet során a **Kék** színt választja ki, a rendszer ellenőrzi, hogy az összetevő meglévő konfigurációjában jelen van-e a kék szín.</span><span class="sxs-lookup"><span data-stu-id="7ce89-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="7ce89-117">Konfigurációk újbóli használatának alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="7ce89-117">Resetting configuration reuse</span></span>
<span data-ttu-id="7ce89-118">Amikor a konfigurációk újbóli használatát alaphelyzetbe állítja, a korábban létrehozott konfigurációk nem számítanak használhatónak.</span><span class="sxs-lookup"><span data-stu-id="7ce89-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="7ce89-119">Érdemes a konfigurációk újbóli használatának alaphelyzetbe állítása, ha az Anyagjegyzék vagy útvonal módosult, de a kapcsolódó attribútumok nem módosultak.</span><span class="sxs-lookup"><span data-stu-id="7ce89-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="7ce89-120">A konfigurációk újbóli használatának alaphelyzetbe állítását az összetevő **Általános** gyorslapján végezheti el.</span><span class="sxs-lookup"><span data-stu-id="7ce89-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>




