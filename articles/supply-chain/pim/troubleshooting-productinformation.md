---
title: Termékinformációk – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani a termékinformáció használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a9db8e0081a0d47ec8d74680fe99a0934b99bb5c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223362"
---
# <a name="troubleshoot-product-information"></a><span data-ttu-id="916a8-103">Termékinformációk – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="916a8-103">Troubleshoot product information</span></span>

<span data-ttu-id="916a8-104">Ez a témakör azt mutatja be, hogyan lehet javítani a termékinformáció használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="916a8-104">This topic describes how to fix issues that you might encounter while you work with product information.</span></span>

## <a name="i-cant-delete-a-released-product"></a><span data-ttu-id="916a8-105">Nem tudok törölni egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="916a8-105">I can't delete a released product.</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-106">Issue description</span></span>

<span data-ttu-id="916a8-107">A kiadott termékeket és annak összes változatát csak akkor törölheti, ha a kiadott termékhez nem kapcsolódnak tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="916a8-107">You can delete a released product and all its variants only if the released product doesn't have any related transactions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-108">Issue resolution</span></span>

<span data-ttu-id="916a8-109">A kiadott termék vagy alaptermék törléséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="916a8-109">Follow these steps to delete a released product or product master.</span></span>

1. <span data-ttu-id="916a8-110">A cikkek összes nyitott tranzakciójának lezárása.</span><span class="sxs-lookup"><span data-stu-id="916a8-110">Close all open transactions for the items.</span></span>
1. <span data-ttu-id="916a8-111">Csökkentse a készletet 0-ra (nulla).</span><span class="sxs-lookup"><span data-stu-id="916a8-111">Reduce the inventory to 0 (zero).</span></span>
1. <span data-ttu-id="916a8-112">Készletzárás végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="916a8-112">Perform inventory closing.</span></span>
1. <span data-ttu-id="916a8-113">Törölje a törölni kívánt alaptermék összes termékváltozatát.</span><span class="sxs-lookup"><span data-stu-id="916a8-113">Delete all product variants for the product master that you want to delete.</span></span>

## <a name="can-i-change-the-item-number-of-a-released-product"></a><span data-ttu-id="916a8-114">Módosíthatom a kiadott termék cikkszámát?</span><span class="sxs-lookup"><span data-stu-id="916a8-114">Can I change the item number of a released product?</span></span>

<span data-ttu-id="916a8-115">A legtöbb esetben nem szerkesztheti a kiadott termékek cikkszámait, mert ez a módosítás az adatok sérülését okozza.</span><span class="sxs-lookup"><span data-stu-id="916a8-115">In most cases, you can't edit item numbers for released products, because that change will cause data to become corrupted.</span></span> <span data-ttu-id="916a8-116">A cikkszámot csak akkor szerkesztheti, ha ki kell javítania azokat az adatsérüléseket, amelyeket a kiadott termék elsődleges kulcsának korábbi átnevezése okozott, ahogy az az [eltávolított vagy elavult Finance and Operations 10.0.0-s platformfrissítés 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24) funkciók listájában szerepel.</span><span class="sxs-lookup"><span data-stu-id="916a8-116">You can edit the item number only if you must repair data corruption that was caused by a previous rename of the primary key of that released product, as mentioned in the list of [removed or deprecated features for Finance and Operations 10.0.0 with Platform update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span></span>

<span data-ttu-id="916a8-117">Ha azt szeretné, hogy képes legyen a kiadott termékek cikkszámainak szerkesztésére, [szavazzon erre az ötletre az Ideas portálon](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span><span class="sxs-lookup"><span data-stu-id="916a8-117">If you want to be able to edit item numbers for released products, [vote for this idea in Ideas portal](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span></span>

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a><span data-ttu-id="916a8-118">A termék alapértelmezett ürítési elve nem kerül be az anyagjegyzéksorba.</span><span class="sxs-lookup"><span data-stu-id="916a8-118">The default flushing principle from the product isn't being entered on the bill of materials line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-119">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-119">Issue description</span></span>

<span data-ttu-id="916a8-120">Amikor cikket ad hozzá egy anyagjegyzéksorhoz, a rendszer nem használja a cikkhez beállított alapértelmezett ürítési elv adatokat.</span><span class="sxs-lookup"><span data-stu-id="916a8-120">When you add an item to a bill of materials (BOM) line, the system doesn't use the default flushing principle information that is set up for the item.</span></span> <span data-ttu-id="916a8-121">Más szóval a cikk ürítési elve nem jelenik meg az **anyagjegyzéksor** oldalán.</span><span class="sxs-lookup"><span data-stu-id="916a8-121">In other words, the flushing principle from the item doesn't appear on the **BOM line** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-122">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-122">Issue resolution</span></span>

<span data-ttu-id="916a8-123">Ha egy anyagjegyzéksorban ürítési elvet ad meg, az az adott anyagjegyzéksorra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="916a8-123">If you specify a flushing principle on a BOM line, it will apply to that BOM line.</span></span> <span data-ttu-id="916a8-124">Ha azonban az ürítési elv üres, vagy nincs beállítva anyagjegyzéksorhoz, akkor a cikken beállított ürítési elv továbbra is érvényes lesz az adott anyagjegyzéksorra, még akkor is, ha az nem jelenik meg az anyagjegyzéksorban.</span><span class="sxs-lookup"><span data-stu-id="916a8-124">However, if the flushing principle is blank, or if it isn't set on a BOM line, the flushing principle that is set on the item will still apply to that BOM line, even though it isn't shown on the BOM line.</span></span>

<span data-ttu-id="916a8-125">A Microsoft Dynamics 365 Supply Chain Management egyéb funkcióinak alapértelmezett logikája általában nem így működik.</span><span class="sxs-lookup"><span data-stu-id="916a8-125">The defaulting logic for other features in Microsoft Dynamics 365 Supply Chain Management doesn't usually work in this way.</span></span> <span data-ttu-id="916a8-126">A jelenlegi viselkedés azonban nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="916a8-126">However, the current behavior can't be changed.</span></span> <span data-ttu-id="916a8-127">Ellenkező esetben előfordulhat, hogy egyes meglévő testreszabások, amelyek támaszkodnak rá, megszakadnak.</span><span class="sxs-lookup"><span data-stu-id="916a8-127">Otherwise, some existing customizations that rely on it might be broken.</span></span>

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a><span data-ttu-id="916a8-128">A rendszer lehetővé teszi, hogy ismétlődő vonalkódokat mentsek különböző cikkekhez vagy ugyanarra a különböző méretű cikkre.</span><span class="sxs-lookup"><span data-stu-id="916a8-128">The system lets me save duplicate bar codes for different items or for the same item that has different dimensions.</span></span>

<span data-ttu-id="916a8-129">A rendszer jelenleg nem kényszeríti ki az egyedi vonalkódokat, és a korlátozás hozzáadása kompatibilitástörő változás lenne.</span><span class="sxs-lookup"><span data-stu-id="916a8-129">The system doesn't currently enforce unique bar codes, and the addition of this restriction would be a breaking change.</span></span> <span data-ttu-id="916a8-130">Valójában a Microsoftnak bizonyítéka van arra, hogy néhány meglévő ügyféltelepítést megtörne ez a változás.</span><span class="sxs-lookup"><span data-stu-id="916a8-130">In fact, Microsoft has evidence that some existing customer installations would be broken by this change.</span></span> <span data-ttu-id="916a8-131">Azonban megfontoljuk a szélesebb körű tervezési változtatást, hogy a jövőben lehetővé tegyék ezt a funkciót.</span><span class="sxs-lookup"><span data-stu-id="916a8-131">However, we will consider a broader design change to enable this feature in the future.</span></span>

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a><span data-ttu-id="916a8-132">Cikkbejegyzés-sablonok szerkesztéseknél a következő hibaüzenet jelenik meg: ”A raktár helye nem hozható létre, mert a cikk nincs raktáron.</span><span class="sxs-lookup"><span data-stu-id="916a8-132">I receive the following error message when I edit item record templates: "The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="916a8-133">Cikkek készletezéséhez a kapcsolódó cikkmodellcsoport Készleten lévő termékbeállítását kell kiválasztani.”</span><span class="sxs-lookup"><span data-stu-id="916a8-133">To stock items, the Stocked product option on the associated item model group must be selected."</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-134">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-134">Issue description</span></span>

<span data-ttu-id="916a8-135">Ez a probléma akkor fordul elő, ha az alábbi lépésekkel próbál sablont létrehozni egy nem raktározott cikkhez.</span><span class="sxs-lookup"><span data-stu-id="916a8-135">This issue occurs if you follow these steps to try to create a template for an item that isn't stocked.</span></span>

1. <span data-ttu-id="916a8-136">Nyisson meg egy nem raktározott, kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="916a8-136">Open a released product that isn't stocked.</span></span>
1. <span data-ttu-id="916a8-137">A Művelet panel **Lehetőségek** fülön válassza a **Rekord infó** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="916a8-137">On the Action Pane, on the **Options** tab, select **Record info**.</span></span>
1. <span data-ttu-id="916a8-138">A **Rekordinformáció** párbeszédpanelen válassza a **Vállalati számlák sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="916a8-138">In the **Record information** dialog box, select **Company accounts template**.</span></span>

<span data-ttu-id="916a8-139">Ebben az esetben az alábbi hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="916a8-139">In this case, you receive the following error message:</span></span>

> <span data-ttu-id="916a8-140">A raktár nem hozható létre, mert a cikk nincs raktáron.</span><span class="sxs-lookup"><span data-stu-id="916a8-140">The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="916a8-141">Cikkek készletezéséhez a kapcsolódó cikkmodellcsoport Készleten lévő termékbeállítását kell kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="916a8-141">To stock items, the Stocked product option on the associated item model group must be selected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-142">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-142">Issue resolution</span></span>

<span data-ttu-id="916a8-143">A terméksablonok létrehozásának folyamata további termékspecifikus logikát igényel.</span><span class="sxs-lookup"><span data-stu-id="916a8-143">The process of creating product templates requires extra product-specific logic.</span></span> <span data-ttu-id="916a8-144">Ezért erre a célra nem használhatja az általános **Vállalati számlák sablon** gombot.</span><span class="sxs-lookup"><span data-stu-id="916a8-144">Therefore, you can't use the generic **Company accounts template** button for this purpose.</span></span> <span data-ttu-id="916a8-145">Ehelyett kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="916a8-145">Instead, follow these steps.</span></span>

1. <span data-ttu-id="916a8-146">Nyisson meg egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="916a8-146">Open a released product.</span></span>
1. <span data-ttu-id="916a8-147">A Művelet panelen a **Termék** fülön az **Új** csoportban válassza a **Sablon \> Megosztott sablon létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="916a8-147">On the Action Pane, on the **Product** tab, in the **New** group, select **Template \> Create shared template**.</span></span>

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a><span data-ttu-id="916a8-148">A termékattribútumokban hozzáadott alapértelmezett súgószöveg nem kerül be a kiadott termékbe.</span><span class="sxs-lookup"><span data-stu-id="916a8-148">Default Help text that is added in product attributes isn't entered in a released product.</span></span>

<span data-ttu-id="916a8-149">A termékattribútumokban hozzáadott leírás és súgószöveg nem látható, és alapértelmezés szerint nem szerepel a kiadott termékekben.</span><span class="sxs-lookup"><span data-stu-id="916a8-149">A description and Help text that are added in the product attributes aren't visible or entered by default in the released products.</span></span> <span data-ttu-id="916a8-150">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="916a8-150">This behavior is by design.</span></span>

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a><span data-ttu-id="916a8-151">A megadott alapértelmezett mennyiség akkor változik, ha az anyagjegyzékből, és ha az anyagjegyzék-verzióból van regisztrálva.</span><span class="sxs-lookup"><span data-stu-id="916a8-151">The default quantity that is entered differs when it's registered from a BOM and when it's registered from a BOM version.</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-152">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-152">Issue description</span></span>

<span data-ttu-id="916a8-153">Alapértelmezés szerint, amikor cikket ad hozzá egy anyagjegyzékhez, a mennyiség 1-re van állítva a kiválasztott termék **Alapértelmezett rendelési beállítások** lapjának **Min. rendelési mennyisége** lehetőségben.</span><span class="sxs-lookup"><span data-stu-id="916a8-153">By default, when you add an item to a BOM, the quantity is set to 1 instead of the quantity that is defined in the **Min. order quantity** field on the **Default order settings** page for a selected product.</span></span> <span data-ttu-id="916a8-154">Ha azonban egy anyagjegyzék-verzióból vesz fel cikket, és a cikk és a változat ki van jelölve, az alapértelmezés szerint megadott mennyiség figyelembe veszi az adott dimenziók alapértelmezett rendelési beállításaiban megadott minimális mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="916a8-154">However, when you add an item from a BOM version, and the item and variant are selected, the quantity that is entered by default takes into account the minimum quantity that is set in the default order settings for the specific dimensions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-155">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-155">Issue resolution</span></span>

<span data-ttu-id="916a8-156">Ez a viselkedés várható.</span><span class="sxs-lookup"><span data-stu-id="916a8-156">This behavior is expected.</span></span> <span data-ttu-id="916a8-157">Azonban az a tény, hogy a logika eltér az anyagjegyzékben és az anyagjegyzék-verzióban, az egy ismert probléma.</span><span class="sxs-lookup"><span data-stu-id="916a8-157">However, the fact that the logic differs in the BOM and the BOM version is a known issue.</span></span> <span data-ttu-id="916a8-158">Mindazonáltal ez a viselkedés nem változik, mert a módosítás számos különböző ügyfélforgatókönyvre hatással lehet.</span><span class="sxs-lookup"><span data-stu-id="916a8-158">Nevertheless, this behavior won't be changed, because a change could affect many different customer scenarios.</span></span>

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a><span data-ttu-id="916a8-159">A kiadott termékrészletekben nem tudom módosítani a termékdokumentum mellékleteinek adatentitásból feltöltött csatolt képeket.</span><span class="sxs-lookup"><span data-stu-id="916a8-159">In the released product details, I can't change the attached images that were uploaded from the Product document attachments data entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-160">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-160">Issue description</span></span>

<span data-ttu-id="916a8-161">Ez a probléma akkor fordulhat elő, ha egy képet egy elemhez csatol a *Termékdokumentum mellékletek* adatentitás használatával.</span><span class="sxs-lookup"><span data-stu-id="916a8-161">This issue can occur when you attach an image to an item by using the *Product document attachments* data entity.</span></span> <span data-ttu-id="916a8-162">Ebben az esetben az elem képe jelenik meg az elemnél.</span><span class="sxs-lookup"><span data-stu-id="916a8-162">In this case, the item image is shown for the item.</span></span> <span data-ttu-id="916a8-163">Ha azonban a **Kép módosítása** lehetőséget választja, a feltöltött képek listájában semmi sem jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="916a8-163">However, if you select **Change image**, nothing is shown in the list of uploaded images.</span></span> <span data-ttu-id="916a8-164">Ezenkívül nem jelennek meg mellékletek az elemhez.</span><span class="sxs-lookup"><span data-stu-id="916a8-164">Additionally, no attachments are shown for the item.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-165">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-165">Issue resolution</span></span>

<span data-ttu-id="916a8-166">Az *EcoResProductDocumentAttachmentEntity* entitás (*Termékdokumentum-mellékletek*) importálja a *termékekhez* tartozó, de a *kiadott termékekhez* nem tartalmazó dokumentummellékleteket importál.</span><span class="sxs-lookup"><span data-stu-id="916a8-166">The *EcoResProductDocumentAttachmentEntity* entity (*Product document attachments*) imports document attachments for *products* but not for *released products*.</span></span> <span data-ttu-id="916a8-167">(A kiadott termékeket *cikkeknek* is nevezik.) Ha egy elem mellékleteit a **Kiadott termék részletei** lapon szeretné megtekinteni, az *EcoResReleasedProductDocumentAttachmentEntity* entitást (*Kiadott termékdokumentum-mellékletek*) kell használnia.</span><span class="sxs-lookup"><span data-stu-id="916a8-167">(Released products are also known as *items*.) To view the attachments for an item on the **Released product details** page, you must use the *EcoResReleasedProductDocumentAttachmentEntity* entity (*Released product document attachments*) instead.</span></span>

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a><span data-ttu-id="916a8-168">Az Microsoft Flow összekötő a következő hibaüzenetet jeleníti meg: „Frissítés nem engedélyezett a „ProductNumber” mezőhöz”.</span><span class="sxs-lookup"><span data-stu-id="916a8-168">The Microsoft Flow connector shows the following error message: "Update not allowed for field 'ProductNumber'."</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-169">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-169">Issue description</span></span>

<span data-ttu-id="916a8-170">Ez a probléma akkor fordul elő, ha a **Termékszám** mezőt a *Kiadott termékek* entitás V2 és Microsoft Flow használatával próbálja frissíteni.</span><span class="sxs-lookup"><span data-stu-id="916a8-170">This issue occurs if you try to update the **Product number** field by using the *Released products* entity V2 and Microsoft Flow.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-171">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-171">Issue resolution</span></span>

<span data-ttu-id="916a8-172">Ez a viselkedés várható.</span><span class="sxs-lookup"><span data-stu-id="916a8-172">This behavior is expected.</span></span> <span data-ttu-id="916a8-173">A kiadott termék termékszámának szerkesztési lehetősége a Dynamics 365 Finance and Operations 10.0.0 verzióban a 24-es számú platformfrissítéssel lett eltávolítva az adatsérülés megelőzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="916a8-173">The ability to edit the product number for a released product was removed in Dynamics 365 Finance and Operations 10.0.0 with platform update 24 to help prevent data corruption.</span></span> <span data-ttu-id="916a8-174">Kivételes esetekben ki kell javítania a kiadott termék elsődleges kulcsának egy korábbi átnevezése által okozott adatsérülést, kérdezze meg a Microsoft ügyfélszolgálatát a korlátozás ideiglenes eltávolításának kérése céljából.</span><span class="sxs-lookup"><span data-stu-id="916a8-174">In exceptional cases, where you must repair data corruption that was caused by a previous rename of the primary key of a released product, you can ask Microsoft Support to temporarily remove this restriction.</span></span>

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a><span data-ttu-id="916a8-175">Nem tudok kiadott termékváltozatot létrehozni egy másik jogi személyben.</span><span class="sxs-lookup"><span data-stu-id="916a8-175">I can't create a released product variant in another legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-176">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-176">Issue description</span></span>

<span data-ttu-id="916a8-177">Ha megpróbál kiadni egy alapterméket változatok nélkül, majd szükség szerint létrehozza az egyes jogi személy (vállalat) változatait, akkor a változatokat nem tudja kiadni változatjavaslatok használatával.</span><span class="sxs-lookup"><span data-stu-id="916a8-177">If you try to release a product master without variants, and then create the variants in each legal entity (company) as they are required, you won't be able to release the variants by using variant suggestions.</span></span> <span data-ttu-id="916a8-178">A változatokat sem fogja tudni manuálisan létrehozni.</span><span class="sxs-lookup"><span data-stu-id="916a8-178">You also won't be able to manually create the variants.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-179">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-179">Issue resolution</span></span>

<span data-ttu-id="916a8-180">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="916a8-180">This behavior is by design.</span></span> <span data-ttu-id="916a8-181">Az alaptermék viszonyai és az alap által felvehető dimenziók megosztott szinten maradnak.</span><span class="sxs-lookup"><span data-stu-id="916a8-181">The relations of a product master and the dimensions that the master can take are kept at a shared level.</span></span> <span data-ttu-id="916a8-182">Ezért nem hozhatja létre a rendelkezésre álló dimenziókat egy megosztott termékalaphoz egy adott jogi személynél, ahol ezeket a dimenziókat kiadta, és replikálja a folyamatot minden jogi személy, ahol a dimenziók szükségesek.</span><span class="sxs-lookup"><span data-stu-id="916a8-182">Therefore, you can't create the available dimensions for a shared product master in the specific legal entity where those dimensions are released and then replicate the process in each legal entity where the dimensions are required.</span></span> <span data-ttu-id="916a8-183">Ehelyett módosítania kell a kiadási folyamatot, hogy az alkalmazkodjon a tervezett folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="916a8-183">Instead, you must change your release process to adapt to the designed process.</span></span>

<span data-ttu-id="916a8-184">Itt van a termékek kiadásának folyamata.</span><span class="sxs-lookup"><span data-stu-id="916a8-184">Here is the process for releasing products.</span></span>

1. <span data-ttu-id="916a8-185">Hozza létre a megosztott alapterméket és a jogi személyek számára kiadható dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="916a8-185">Create the shared product master and the dimensions that can be released to the legal entities.</span></span>
1. <span data-ttu-id="916a8-186">Adja ki a termékeket a jogi személyeknek, vagy változatjavaslatok használatával, vagy manuálisan adja hozzá a kiadandó kombinációkat.</span><span class="sxs-lookup"><span data-stu-id="916a8-186">Release the products to the legal entities either by using variant suggestions or by manually adding the combinations that should be released.</span></span>

<span data-ttu-id="916a8-187">Azt is megteheti, hogy közvetlenül létrehozza a kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="916a8-187">Alternatively, you can directly create the released product.</span></span>

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a><span data-ttu-id="916a8-188">Amikor egy másik vállalatnál egy változatot kiadok, a következő hibaüzenet jelenik meg: „A megadott dimenziójú termékváltozat már létrejött.”</span><span class="sxs-lookup"><span data-stu-id="916a8-188">When I release a variant in another company, I receive the following error message: "Product variant with specified dimensions has already been created."</span></span>

### <a name="issue-description"></a><span data-ttu-id="916a8-189">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="916a8-189">Issue description</span></span>

<span data-ttu-id="916a8-190">Ha egy termékváltozat már megjelent egy „A” vállalatnál, és a „B” vállalatnál a **Kiadott termékváltozatok** lap **Új** gombjával próbálja meg kiadni, a következő hibaüzenet jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="916a8-190">If a product variant has already been released in a company A, and you try to release it in company B by using the **New** button on the **Released product variants** page, you will receive the following error message:</span></span>

> <span data-ttu-id="916a8-191">A megadott dimenziókkal rendelkező termékváltozat már létrejött.</span><span class="sxs-lookup"><span data-stu-id="916a8-191">Product variant with specified dimensions has already been created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="916a8-192">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="916a8-192">Issue resolution</span></span>

<span data-ttu-id="916a8-193">A **Kiadott termékváltozatok** lap **Új** gombja létrehozza a változatot, és vállalati környezetben adja ki azt.</span><span class="sxs-lookup"><span data-stu-id="916a8-193">The **New** button on the **Released product variants** page creates the variant and releases it in the company context.</span></span> <span data-ttu-id="916a8-194">Ha a változat már létrejött, nem használhatja az **Új** gombot, hogy kiadja egy másik vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="916a8-194">If the variant has already been created, you can't use the **New** button to release it in another company.</span></span>

<span data-ttu-id="916a8-195">A probléma megoldásához nyissa meg az **Alaptermék** oldalt, és válassza a **Termék kiadása** lehetőséget a meglévő változat kiadásához a kívánt vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="916a8-195">To fix the issue, open the **Product master** page, and select **Release product** to release the existing variant in the desired company.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]