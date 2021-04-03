---
title: Vevők kezelése az üzletekben
description: Ez a témakör bemutatja, hogyan engedélyezhetik a kiskereskedők a vevőkezelési képességeket a pénztárnál (POS) a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8a1b360ba6a2d32e38e101f25f108094a00190c8
ms.sourcegitcommit: 8a14eac1c27f10c2b1b02ac9ad82339f5e127602
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2021
ms.locfileid: "5555047"
---
# <a name="customer-management-in-stores"></a><span data-ttu-id="08156-103">Vevők kezelése az üzletekben</span><span class="sxs-lookup"><span data-stu-id="08156-103">Customer management in stores</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="08156-104">Ez a témakör bemutatja, hogyan engedélyezhetik a kiskereskedők a vevőkezelési képességeket a pénztárnál (POS) a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="08156-104">This topic explains how retailers can enable customer management capabilities at the point of sale (POS) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="08156-105">Fontos, hogy az üzlet munkatársai vevőrekordokat hozhassanak létre és szerkeszthessenek a pénztárban.</span><span class="sxs-lookup"><span data-stu-id="08156-105">It's important that store associates can create and edit customer records at the POS.</span></span> <span data-ttu-id="08156-106">Ily módon rögzíthetik a vevői adatok esetleges frissítéseit, például az e-mail-címet, a telefonszámot és a címet.</span><span class="sxs-lookup"><span data-stu-id="08156-106">In that way, they can capture any updates to customer information such as the email address, phone number, and address.</span></span> <span data-ttu-id="08156-107">Ez az információ hasznos az olyan alsóbb rétegbeli rendszerekben, mint a marketing, mivel ezeknek a rendszereknek a hatékonysága az ügyféladatok pontosságától függ.</span><span class="sxs-lookup"><span data-stu-id="08156-107">This information is helpful in downstream systems such as marketing, because the effectiveness of those systems depends on the accuracy of their customer data.</span></span>

<span data-ttu-id="08156-108">Az értékesítési munkatársak két pénztári belépési pontból tudják aktiválni a vevő létrehozásának munkafolyamatát.</span><span class="sxs-lookup"><span data-stu-id="08156-108">Sales associates can trigger the customer creation workflow from two POS entry points.</span></span> <span data-ttu-id="08156-109">Kiválaszthat egy, a **Vevő hozzáadása** nevű művelethez hozzárendelt gombot, vagy k Keresési eredmények oldalon az alkalmazássávon a **Vevő létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08156-109">They can select a button that is mapped to the **Customer add** operation, or they can select **Create customer** on the app bar on the search results page.</span></span> <span data-ttu-id="08156-110">Mindkét esetben megjelenik az **Új vevő** párbeszédpanel, ahol az értékesítési munkatárs megadhatja a vevő szükséges adatait, például a vevő nevét, e-mail-címét, telefonszámát, címét és az üzleti tevékenység számára esetleges további, releváns információkat.</span><span class="sxs-lookup"><span data-stu-id="08156-110">In both cases, the **New customer** dialog box appears, where sales associates can enter required customer details, such as the customer's name, email address, phone number, address, and any additional information that is relevant to the business.</span></span> <span data-ttu-id="08156-111">Ezek a kiegészítő információk a vevőhöz társított vevőattribútumok segítségével is rögzítethetők.</span><span class="sxs-lookup"><span data-stu-id="08156-111">That additional information can be captured by using the customer attributes that are associated with the customer.</span></span> <span data-ttu-id="08156-112">A vevőattribútumokkal kapcsolatos további tudnivalókat lásd: [Vevőattribútumok](dev-itpro/customer-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="08156-112">For more information about customer attributes, see [Customer attributes](dev-itpro/customer-attributes.md).</span></span>

<span data-ttu-id="08156-113">Az értékesítési munkatárs másodlagos e-mail-címeket és telefonszámokat is rögzíthet.</span><span class="sxs-lookup"><span data-stu-id="08156-113">Sales associates can also capture secondary email addresses and phone numbers.</span></span> <span data-ttu-id="08156-114">Ezenkívül rögzítheti, hogy a vevő a másodlagos e-mail-címek vagy telefonszámok egyikén fogad-e marketinginformációkat.</span><span class="sxs-lookup"><span data-stu-id="08156-114">Additionally, they can capture the customer's preference about receiving marketing information via any of those secondary email addresses or phone numbers.</span></span> <span data-ttu-id="08156-115">A funkció engedélyezéséhez a kiskereskedőknek be kell kapcsolniuk a **Több e-mail és telefonszám rögzítése és a marketinghez való hozzájárulás ezen kapcsolatok esetén** funkciót a Commerce központi felületének **Funkciókezelés** munkaterületén (**Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés**).</span><span class="sxs-lookup"><span data-stu-id="08156-115">To enable this capability, retailers must turn on the **Capture multiple emails and phone numbers and consent for marketing on these contacts** feature in the **Feature management** workspace in Commerce headquarters (**Systems administration \> Workspaces \> Feature management**).</span></span>

## <a name="default-customer-properties"></a><span data-ttu-id="08156-116">Alapértelmezett vevőtulajdonságok</span><span class="sxs-lookup"><span data-stu-id="08156-116">Default customer properties</span></span>

<span data-ttu-id="08156-117">A kiskereskedők használhatják az **Összes üzlet** oldalt a Commerce központi felületén (**Retail és Commerce \> Csatornák \> Üzletek**) arra, hogy egy alapértelmezett vevőt társítsanak az egyes üzletekhez.</span><span class="sxs-lookup"><span data-stu-id="08156-117">Retailers can use the **All stores** page in Commerce headquarters (**Retail and Commerce \> Channels \> Stores**) to associate a default customer with each store.</span></span> <span data-ttu-id="08156-118">A Commerce rendszer ezután átmásolja az alapértelmezett vevőhöz meghatározott tulajdonságokat az összes létrehozott új vevőrekordba.</span><span class="sxs-lookup"><span data-stu-id="08156-118">Commerce then copies the properties that are defined for the default customer to all new customer records that are created.</span></span> <span data-ttu-id="08156-119">Például a **Vevő létrehozása** párbeszédpanelen azok a tulajdonságok jelennek meg, amelyek az üzlethez társított alapértelmezett vevőhöz vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="08156-119">For example, the **Create customer** dialog box shows properties that are inherited from the default customer that is associated with the store.</span></span> <span data-ttu-id="08156-120">Ilyen tulajdonságok például a vevő típusa, a vevőcsoport, a kívánt nyugta, a pénznem és a nyelv.</span><span class="sxs-lookup"><span data-stu-id="08156-120">Those properties include the customer type, customer group, receipt preference, currency, and language.</span></span> <span data-ttu-id="08156-121">A fiókok (vevői csoportok) is az alapértelmezett vevőtől öröklődnek.</span><span class="sxs-lookup"><span data-stu-id="08156-121">Any affiliations (groupings of customers) are also inherited from the default customer.</span></span> <span data-ttu-id="08156-122">A pénzügyi dimenziók azonban attól a vevői csoporttól öröklődnek, amely az alapértelmezett vevőhöz van társítva, nem pedig magától az alapértelmezett vevőtől.</span><span class="sxs-lookup"><span data-stu-id="08156-122">However, financial dimensions are inherited from the customer group that is associated with the default customer, not from the default customer itself.</span></span>

<span data-ttu-id="08156-123">Az értékesítési munkatársak több címet is rögzíthetnek egy vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="08156-123">Sales associates can capture multiple addresses for a customer.</span></span> <span data-ttu-id="08156-124">A vevő neve és telefonszáma az egyes címekhez társított kapcsolattartási adatokból öröklődik.</span><span class="sxs-lookup"><span data-stu-id="08156-124">The customer's name and phone number are inherited from the contact information that is associated with each address.</span></span> <span data-ttu-id="08156-125">A vevőrekord **Címek** gyorslapja tartalmaz egy **Cél** mezőt, amelyet az értékesítési munkatársak módosíthatnak.</span><span class="sxs-lookup"><span data-stu-id="08156-125">The **Addresses** FastTab of a customer record includes a **Purpose** field that sales associates can edit.</span></span> <span data-ttu-id="08156-126">Ha a vevő típusa **Személy**, az alapértelmezett érték a **Kezdőlap**.</span><span class="sxs-lookup"><span data-stu-id="08156-126">If the customer type is **Person**, the default value is **Home**.</span></span> <span data-ttu-id="08156-127">Ha a vevő típusa **Szervezet**, az alapértelmezett érték a **Vállalat**.</span><span class="sxs-lookup"><span data-stu-id="08156-127">If the customer type is **Organization**, the default value is **Business**.</span></span> <span data-ttu-id="08156-128">A mező által támogatott egyéb értékek közé tartozik a **Kezdőlap**, az **Iroda** és a **Postaláda**.</span><span class="sxs-lookup"><span data-stu-id="08156-128">Other values that this field supports include **Home**, **Office**, and **Post box**.</span></span> <span data-ttu-id="08156-129">A cím **Ország** mezőjének értéke abból az elsődleges címből öröklődik, amely a Commerce központi felületében az **Üzemi egység** oldalon van megadva a **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek** pontban.</span><span class="sxs-lookup"><span data-stu-id="08156-129">The value of the **Country** field for an address is inherited from the primary address that is specified on the **Operating unit** page in Commerce headquarters at **Organization administration \> Organizations \> Operating units**.</span></span>

## <a name="sync-customers-and-async-customers"></a><span data-ttu-id="08156-130">Szinkron vevők és Aszinkron vevők</span><span class="sxs-lookup"><span data-stu-id="08156-130">Sync customers and Async customers</span></span>

<span data-ttu-id="08156-131">A Commerce rendszerben két lehetőség van vevők létrehozására: a szinkron (vagy Sync) és az aszinkron (vagy Async).</span><span class="sxs-lookup"><span data-stu-id="08156-131">In Commerce, there are two modes of customer creation: Synchronous (or Sync) and Asynchronous (or Async).</span></span> <span data-ttu-id="08156-132">Alapértelmezés szerint a vevők létrehozása szinkronban történik.</span><span class="sxs-lookup"><span data-stu-id="08156-132">By default, customers are created synchronously.</span></span> <span data-ttu-id="08156-133">Más szóval a Commerce központi felületén jönnek létre valós időben.</span><span class="sxs-lookup"><span data-stu-id="08156-133">In other words, they are created in Commerce headquarters in real time.</span></span> <span data-ttu-id="08156-134">A Szinron vevő létrehozása módja azért előnyös, mert az új vevők azonnal kereshetők a különböző csatornákon keresztül.</span><span class="sxs-lookup"><span data-stu-id="08156-134">The Sync customer creation mode is beneficial because new customers are immediately searchable across channels.</span></span> <span data-ttu-id="08156-135">Ennek azonban van egy hátránya is.</span><span class="sxs-lookup"><span data-stu-id="08156-135">However, it also has a drawback.</span></span> <span data-ttu-id="08156-136">Mivel [Commerce Data Exchange Valós idejű szolgáltatás](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) típusú hívásokat generál a Commerce központi felülete irányába, befolyásolhatja a teljesítményt, ha a rendszer sok egyidejű vevői létrehozási hívást kezdeményez.</span><span class="sxs-lookup"><span data-stu-id="08156-136">Because it generates [Commerce Data Exchange: Real-time Service](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) calls to Commerce headquarters, performance can be affected if many concurrent customer creation calls are made.</span></span>

<span data-ttu-id="08156-137">Ha a **Vevő létrehozása aszinkron módban** beállítás értéke **Igen** az üzlet funkcióprofiljában (**Retail és Commerce \> Csatorna beállítás \> Online áruház beállítása \> Funkcióprofilok**), akkor a valós idejű szolgáltatás típusú hívások nem használhatók vevőrekordok létrehozásához a csatorna-adatbázisban.</span><span class="sxs-lookup"><span data-stu-id="08156-137">If the **Create customer in async mode** option is set to **Yes** in the store's functionality profile (**Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**), Real-time Service calls aren't used to create customer records in the channel database.</span></span> <span data-ttu-id="08156-138">A Vevők aszinkron létrehozása mód nincs hatással a Commerce központi felületének teljesítményére.</span><span class="sxs-lookup"><span data-stu-id="08156-138">The Async customer creation mode doesn't affect the performance of Commerce headquarters.</span></span> <span data-ttu-id="08156-139">A globálisan egyedi azonosítót (GUID) a rendszer minden új aszinkron vevői rekordhoz hozzárendeli és vevői számlaazonosítóként használja.</span><span class="sxs-lookup"><span data-stu-id="08156-139">A temporary globally unique identifier (GUID) is assigned to every new Async customer record and used as the customer account ID.</span></span> <span data-ttu-id="08156-140">Ez a GUID nem jelenik meg a pénztári felhasználóknak.</span><span class="sxs-lookup"><span data-stu-id="08156-140">This GUID isn't shown to POS users.</span></span> <span data-ttu-id="08156-141">Ehelyett ezek a felhasználók a **Függőben lévő szinkronizálás** lehetőséget látják vevői számlaazonosítóként.</span><span class="sxs-lookup"><span data-stu-id="08156-141">Instead, those users will see **Pending sync** as the customer account ID.</span></span> <span data-ttu-id="08156-142">Bár ez a konfiguráció a vevők aszinkron létrehozására kényszerít, a vevői rekordok szerkesztése mindig szinkron módon történik.</span><span class="sxs-lookup"><span data-stu-id="08156-142">Although this configuration forces customers to be created asynchronously, note that edits to customer records are always done synchronously.</span></span>

### <a name="convert-async-customers-to-sync-customers"></a><span data-ttu-id="08156-143">Aszinkron vevők szinkron vevőkké történő konvertálása</span><span class="sxs-lookup"><span data-stu-id="08156-143">Convert Async customers to Sync customers</span></span>

<span data-ttu-id="08156-144">Ahhoz, hogy az aszinkron vevőket szinkronizált vevőkké konvertálja, előbb futtatnia kell a P-feladatot, hogy az aszinkron vevőket a Commerce központi felületére küldje.</span><span class="sxs-lookup"><span data-stu-id="08156-144">To convert Async customers to Sync customers, you must first run the P-job to send the Async customers to Commerce headquarters.</span></span> <span data-ttu-id="08156-145">Ezt követően futtassa a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladatot a vevői számlaazonosítók létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="08156-145">Then run the **Synchronize customers and business partners from async mode** job to create customer account IDs.</span></span> <span data-ttu-id="08156-146">Végül futtassa az **1010** feladatot, hogy szinkronizálja az új vevői számlaazonosítókat a csatornákkal.</span><span class="sxs-lookup"><span data-stu-id="08156-146">Finally, run the **1010** job to sync the new customer account IDs to the channels.</span></span>

### <a name="async-customer-limitations"></a><span data-ttu-id="08156-147">Az aszinkron vevőkkel kapcsolatos korlátozások</span><span class="sxs-lookup"><span data-stu-id="08156-147">Async customer limitations</span></span>

<span data-ttu-id="08156-148">Az aszinkron vevő funkcióra jelenleg a következő korlátozások vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="08156-148">The Async customer functionality currently has the following limitations:</span></span>

- <span data-ttu-id="08156-149">Az aszinkron vevő rekordjai csak akkor szerkeszthetők, ha a vevőt a Commerce központi felületén hozták létre, és az új vevői számlaazonosítót már visszaszinkronizálták a csatornával.</span><span class="sxs-lookup"><span data-stu-id="08156-149">Async customer records can't be edited unless the customer has been created in Commerce headquarters and the new customer account ID has been synced back to the channel.</span></span>
- <span data-ttu-id="08156-150">Aszinkron vevőkhöz nem társítható fiók.</span><span class="sxs-lookup"><span data-stu-id="08156-150">Affiliations can't be associated with Async customers.</span></span> <span data-ttu-id="08156-151">Emiatt az új aszinkron vevők nem öröklik a fiókokat az alapértelmezett vevőtől.</span><span class="sxs-lookup"><span data-stu-id="08156-151">Therefore, new Async customers don't inherit affiliations from the default customer.</span></span>
- <span data-ttu-id="08156-152">Nem lehet hűségkártyákat kiadni az aszinkron vevőknek, amíg az új vevői számlaazonosító nincs visszaszinkronizálva a csatornával.</span><span class="sxs-lookup"><span data-stu-id="08156-152">Loyalty cards can't be issued to Async customers unless the new customer account ID has been synced back to the channel.</span></span>
- <span data-ttu-id="08156-153">Az aszinkron vevőkhöz nem lehet másodlagos e-mail-címeket és telefonszámokat rögzíteni.</span><span class="sxs-lookup"><span data-stu-id="08156-153">Secondary email addresses and phone numbers can't be captured for Async customers.</span></span>

### <a name="customer-creation-in-pos-offline-mode"></a><span data-ttu-id="08156-154">Vevő létrehozása pénztári offline módban</span><span class="sxs-lookup"><span data-stu-id="08156-154">Customer creation in POS offline mode</span></span>

<span data-ttu-id="08156-155">Ha a pénztár kapcsolat nélküli üzemmódba kerül a Vevő aszinkron létrehozása mód engedélyezése közben, az új vevőrekordok aszinkron módon jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="08156-155">If the POS goes offline while the Async customer creation mode is enabled, new customer records are created asynchronously.</span></span> <span data-ttu-id="08156-156">Ha a pénztár kapcsolat nélküli üzemmódba kerül, miközben a Vevő aszinkron létrehozási módja le van tiltva, a rendszer automatikusan átvált a Vevő aszinkron létrehozási módba.</span><span class="sxs-lookup"><span data-stu-id="08156-156">If the POS goes offline while the Async customer creation mode is disabled, the system automatically switches to the Async customer creation mode.</span></span> <span data-ttu-id="08156-157">Vagyis a vevői rekordok aszinkron létrehozása akkor is lehetséges, ha a Vevő aszinkron létrehozása mód le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="08156-157">In other words, customer records might be created asynchronously even if the Async customer creation mode is disabled.</span></span> <span data-ttu-id="08156-158">Emiatt a Commerce központi felülete rendszergazdáinak ismétlődő kötegelt feladatot kell létrehozniuk és ütemezniük a P-feladathoz, a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladathoz és az **1010** feladathoz, hogy a rendszer az aszinkron vevőket szinkron vevőkké konvertálja a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="08156-158">Therefore, Commerce headquarters administrators must create and schedule a recurring batch job for the P-job, the **Synchronize customers and business partners from async mode** job, and the **1010** job, so that any Async customers are converted to Sync customers in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="08156-159">Ha a **Megosztott vevői adattáblák szűrése** beállítása **Igen** a **Commerce-csatorna sémája** oldalon (**Retail és Commerce \> Központ beállítása \> Kereskedelmi ütemező \> Csatorna-adatbázis-csoport**), a vevőrekordok nem jönnek létre, ha a pénztár offline módban van.</span><span class="sxs-lookup"><span data-stu-id="08156-159">If the **Filter shared customer data tables** option is set to **Yes** on the **Commerce channel schema** page (**Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Channel database group**), customer records aren't created in POS offline mode.</span></span> <span data-ttu-id="08156-160">További tudnivalókért lásd: [Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).</span><span class="sxs-lookup"><span data-stu-id="08156-160">For more information, see [Offline data exclusion](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08156-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="08156-161">Additional resources</span></span>

[<span data-ttu-id="08156-162">Vevőattribútumok</span><span class="sxs-lookup"><span data-stu-id="08156-162">Customer attributes</span></span>](dev-itpro/customer-attributes.md)

[<span data-ttu-id="08156-163">Offline adatok kizárása</span><span class="sxs-lookup"><span data-stu-id="08156-163">Offline data exclusion</span></span>](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)