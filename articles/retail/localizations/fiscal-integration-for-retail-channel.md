---
title: "A kiskereskedelmi csatorna pénzügyi integrálása"
description: "Ez a témakör a Retail POS pénzügyi integrálásáról nyújt áttekintést."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: hu-hu
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a><span data-ttu-id="af050-103">A kiskereskedelmi csatorna pénzügyi integrálása</span><span class="sxs-lookup"><span data-stu-id="af050-103">Fiscal integration for Retail channel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af050-104">Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 for Retail pénzügyi integráció funkciójáról.</span><span class="sxs-lookup"><span data-stu-id="af050-104">This topic is an overview of the fiscal integration functionality that is available in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="af050-105">A pénzügyi integráció funkció keretrendszer, amely támogatja a helyi pénzügyi törvényeket, amelyek célja a csalások elleni harc a kiskereskedelemben.</span><span class="sxs-lookup"><span data-stu-id="af050-105">The fiscal integration functionality is a framework designed to support local fiscal laws that are aimed to prevent fraud in the Retail industry.</span></span> <span data-ttu-id="af050-106">A tipikus, pénzügyi integráció használatával megoldható esetek:</span><span class="sxs-lookup"><span data-stu-id="af050-106">Typical scenarios that could be covered by using fiscal integration include:</span></span>

- <span data-ttu-id="af050-107">Pénzügyi nyugta nyomtatása, és odaadása a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="af050-107">Printing a fiscal receipt and giving it to the customer.</span></span>
- <span data-ttu-id="af050-108">A pénztárban végrehajtott értékesítéshez és visszáruhoz kapcsolódó adatok benyújtásának biztonságossá egy külső, az adóhatóság által nyújtott szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="af050-108">Securing the submission of the information related to sales and returns performed on POS to an external service provided by the authority.</span></span>
- <span data-ttu-id="af050-109">A hatóság engedélyezte digitális aláírással adatvédelem használata.</span><span class="sxs-lookup"><span data-stu-id="af050-109">Using data protection with a digital signature authorized by the authority.</span></span>

<span data-ttu-id="af050-110">Ez a témakör bemutatja, hogyan kell a pénzügyi integrációt beállítani, hogy a felhasználók végrehajthassák a következő feladatokat.</span><span class="sxs-lookup"><span data-stu-id="af050-110">This topic provides guidelines for setting up fiscal integration so users can perform the following tasks.</span></span> 

- <span data-ttu-id="af050-111">Állítsa be a pénzügyi összekötőket, amelyek pénzügyi eszközök és szolgáltatások pénzügyi regisztrációs célokra, például ezekhez: mentés, digitális aláírások és a pénzügyi adatok biztonságos benyújtása.</span><span class="sxs-lookup"><span data-stu-id="af050-111">Configure fiscal connectors, which are fiscal devices or services used for fiscal registration purposes like saving, digital signatures, and secured submission of fiscal data.</span></span>
- <span data-ttu-id="af050-112">Állítsa be a dokumentum-szolgáltatót, amely meghatároz egy kimeneti módszert, valamint a pénzügyi bizonylat létrehozásának algoritmusát.</span><span class="sxs-lookup"><span data-stu-id="af050-112">Configure the document provider, which defines an output method and an algorithm of fiscal document generation.</span></span>
- <span data-ttu-id="af050-113">Konfigurálja a pénzügyi regisztráció folyamatát, amely meghatározza lépések sorát, és minden egyes lépéshez a használt összekötők csoportját.</span><span class="sxs-lookup"><span data-stu-id="af050-113">Configure the fiscal registration process, which is defines a sequence of steps and a group of connectors used on each step.</span></span>
- <span data-ttu-id="af050-114">POS-funkcióprofilokhoz rendeljen pénzügyi regisztrációs eljárást.</span><span class="sxs-lookup"><span data-stu-id="af050-114">Assign fiscal registration processes to POS functionality profiles.</span></span>
- <span data-ttu-id="af050-115">Rendeljen összekötő műszaki profilokat vagy hardverprofilokhoz (a helyi pénzügyi összekötőkhöz) vagy POS-funkcióprofilokhoz (más pénzügyiösszekötő-típusokhoz).</span><span class="sxs-lookup"><span data-stu-id="af050-115">Assign connector technical profiles, either to hardware profiles (for the local fiscal connectors) or to POS functionality profiles (for other fiscal connector types).</span></span>

## <a name="fiscal-integration-execution-flow"></a><span data-ttu-id="af050-116">Pénzügyi integráció végrehajtási folyamat</span><span class="sxs-lookup"><span data-stu-id="af050-116">Fiscal integration execution flow</span></span>
<span data-ttu-id="af050-117">A következő helyzet a közös pénzügyi integráció végrehajtási folyamatát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="af050-117">The following scenario shows the common fiscal integration execution flow.</span></span>

1. <span data-ttu-id="af050-118">A pénzügyi regisztrációs folyamat elkezdése.</span><span class="sxs-lookup"><span data-stu-id="af050-118">Initialization of the fiscal registration process.</span></span>
  
   <span data-ttu-id="af050-119">Bizonyos pénzügyi regisztrálást igénylő műveletek végrehajtása után (például kiskereskedelmi tranzakciók lezárása) a pénzügyi regisztrációs folyamat társítva van a jelenlegi pénztár funkcióprofillal.</span><span class="sxs-lookup"><span data-stu-id="af050-119">After performing some actions where fiscal registration is required, such as after a retail transaction has been concluded, the fiscal registration process is associated with the current POS functionality profile.</span></span>

1. <span data-ttu-id="af050-120">Pénzügyi összekötő keresése.</span><span class="sxs-lookup"><span data-stu-id="af050-120">Search for a fiscal connector.</span></span>
   
   <span data-ttu-id="af050-121">Minden egyes pénzügyi regisztrációs lépéshez, amely szerepel a pénzügyi regisztráció folyamatban, a rendszer megfelelteti a pénzügyi összekötők listáját.</span><span class="sxs-lookup"><span data-stu-id="af050-121">For each fiscal registration step included in the fiscal registration process, the system matches the list of fiscal connectors.</span></span> <span data-ttu-id="af050-122">Az összekötőknek van egy funkcióprofiljuk a megadott összekötőcsoportban, összekötők egy csoportjával, amelyeknek a műszaki profilja társítva van a jelenlegi hardverprofillal (a csak **helyi** típusú összekötő esetében), illetve az aktuális pénztár funkcióprofillal (a többi összekötőtípusnál).</span><span class="sxs-lookup"><span data-stu-id="af050-122">These connectors have a functional profile included in the specified connector group, with a list of connectors that have a technical profile associated with the current hardware profile (for a connector type that equals **Local** only) or with the current POS functionality profile (for other connector types).</span></span>
   
1. <span data-ttu-id="af050-123">Hajtsa végre a pénzügyi integrációt.</span><span class="sxs-lookup"><span data-stu-id="af050-123">Perform the fiscal integration.</span></span>

   <span data-ttu-id="af050-124">A rendszer végrehajt minden szükséges műveletet, amelyeket megad a megtalált összekötőhöz kapcsolódó szerelvény.</span><span class="sxs-lookup"><span data-stu-id="af050-124">The system executes all necessary actions defined by an assembly linked with the found connector.</span></span> <span data-ttu-id="af050-125">Ez a működési profil és a műszaki profil beállításainak megfelelően történik, amelyeket az előző lépésben találtunk meg az összekötőhöz.</span><span class="sxs-lookup"><span data-stu-id="af050-125">This is done in accordance with the settings of the functional profile and technical profile that were found on the previous step for this connector.</span></span>

## <a name="setup-needed-before-using-fiscal-integration"></a><span data-ttu-id="af050-126">A pénzügyi integráció használatát megelőzően szükséges beállítás</span><span class="sxs-lookup"><span data-stu-id="af050-126">Setup needed before using fiscal integration</span></span>
<span data-ttu-id="af050-127">Mielőtt a pénzügyi integráció funkciót használná, adja meg a következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="af050-127">Before using the fiscal integration functionality, you should define the following settings:</span></span>

- <span data-ttu-id="af050-128">A számsorozatot adja meg a **Kiskereskedelmi paraméterek** lapon a pénzügyi funkcionális profilszám számára.</span><span class="sxs-lookup"><span data-stu-id="af050-128">Define the number sequence on the **Retail parameters** page for the fiscal functional profile number.</span></span>
  
- <span data-ttu-id="af050-129">A számsorozatokat adja meg a **Megosztott kiskereskedelmi paraméterek** lapon a következő hivatkozásokhoz:</span><span class="sxs-lookup"><span data-stu-id="af050-129">Define the number sequences on the **Retail shared parameters** page for the following references:</span></span>
  
  - <span data-ttu-id="af050-130">Pénzügyi technikai profil száma</span><span class="sxs-lookup"><span data-stu-id="af050-130">Fiscal technical profile number</span></span>
  - <span data-ttu-id="af050-131">Pénzügyi csatlakozócsoport száma</span><span class="sxs-lookup"><span data-stu-id="af050-131">Fiscal connector group number</span></span>
  - <span data-ttu-id="af050-132">Regisztrációs folyamat száma</span><span class="sxs-lookup"><span data-stu-id="af050-132">Registration process number</span></span>

- <span data-ttu-id="af050-133">Hozzon létre egy **Pénzügyi összekötőt** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Pénzügyi összekötők** elemnél minden eszközre vagy szolgáltatásra, amelyet pénzügyi integrációs célokra tervez használni.</span><span class="sxs-lookup"><span data-stu-id="af050-133">Create a **Fiscal connector** in **Retail > Channel setup > Fiscal integration > Fiscal connectors** for each device or service that you plan to use for fiscal integration purposes.</span></span>

-  <span data-ttu-id="af050-134">Hozzon létre egy **Pénzügyi bizonylat szolgáltatót** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Pénzügyi bizonylat szolgáltatók** elemnél az összes pénzügyi összekötőre.</span><span class="sxs-lookup"><span data-stu-id="af050-134">Create a **Fiscal document provider** in **Retail > Channel setup > Fiscal integration > Fiscal document providers** for all fiscal connectors.</span></span> <span data-ttu-id="af050-135">Az adatleképezést a pénzügyi bizonylat szolgáltató részének kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="af050-135">Data mapping is considered a part of the fiscal document provider.</span></span> <span data-ttu-id="af050-136">Azonos összekötőhöz különböző adatleképezések beállításához (például államspecifikus előírások) eltérő pénzügyi bizonylat szolgáltatókat kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="af050-136">To set up different data mappings for the same connector (like state-specific regulations), you should create different fiscal document providers.</span></span>

- <span data-ttu-id="af050-137">Hozzon létre egy **Összekötő funkcionális profilt** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Összekötő funkcionális profilok** elemnél az egyes pénzügyi bizonylat szolgáltatókhoz.</span><span class="sxs-lookup"><span data-stu-id="af050-137">Create a **Connector functional profile** in **Retail > Channel setup > Fiscal integration > Connector functional profiles** for each fiscal document provider.</span></span>
  - <span data-ttu-id="af050-138">Válasszon ki egy összekötőnevet.</span><span class="sxs-lookup"><span data-stu-id="af050-138">Select a connector name.</span></span>
  - <span data-ttu-id="af050-139">Válasszon ki egy bizonylatszolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="af050-139">Select a document provider.</span></span>
  - <span data-ttu-id="af050-140">Adja meg az áfaszázalékok beállításait a **Szolgáltatásbeállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="af050-140">Specify VAT rates settings on the **Service setup** tab.</span></span>
  - <span data-ttu-id="af050-141">Adja meg az áfakódok leképezését és a fizetőeszköz-típus leképezését az **Adatleképezés** lapon.</span><span class="sxs-lookup"><span data-stu-id="af050-141">Specify VAT codes mapping and tender type mapping on the **Data mapping** tab.</span></span>

  #### <a name="examples"></a><span data-ttu-id="af050-142">Példák</span><span class="sxs-lookup"><span data-stu-id="af050-142">Examples</span></span> 

  |  | <span data-ttu-id="af050-143">Formátum</span><span class="sxs-lookup"><span data-stu-id="af050-143">Format</span></span> | <span data-ttu-id="af050-144">Példa</span><span class="sxs-lookup"><span data-stu-id="af050-144">Example</span></span> | 
  |--------|--------|--------|
  | <span data-ttu-id="af050-145">Áfaszázalékok beállítása</span><span class="sxs-lookup"><span data-stu-id="af050-145">VAT rates settings</span></span> | <span data-ttu-id="af050-146">value : VATrate</span><span class="sxs-lookup"><span data-stu-id="af050-146">value : VATrate</span></span> | <span data-ttu-id="af050-147">1 : 2000, 2 : 1800</span><span class="sxs-lookup"><span data-stu-id="af050-147">1 : 2000, 2 : 1800</span></span> |
  | <span data-ttu-id="af050-148">Áfakódok leképezése</span><span class="sxs-lookup"><span data-stu-id="af050-148">VAT codes mapping</span></span> | <span data-ttu-id="af050-149">VATcode : value</span><span class="sxs-lookup"><span data-stu-id="af050-149">VATcode : value</span></span> | <span data-ttu-id="af050-150">vat20 : 1, vat18 : 2</span><span class="sxs-lookup"><span data-stu-id="af050-150">vat20 : 1, vat18 : 2</span></span> |
  | <span data-ttu-id="af050-151">Fizetőeszköz-típusok leképezése</span><span class="sxs-lookup"><span data-stu-id="af050-151">Tender types mapping</span></span> | <span data-ttu-id="af050-152">TenderTyp : value</span><span class="sxs-lookup"><span data-stu-id="af050-152">TenderTyp : value</span></span> | <span data-ttu-id="af050-153">Cash : 1, Card : 2</span><span class="sxs-lookup"><span data-stu-id="af050-153">Cash : 1, Card : 2</span></span> |

- <span data-ttu-id="af050-154">Hozzon létre **Pénzügyi összekötő csoportokat** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Összekötő pénzügyi csoport** elemnél.</span><span class="sxs-lookup"><span data-stu-id="af050-154">Create **Fiscal connector groups** in **Retail > Channel setup > Fiscal integration > Fiscal connector group**.</span></span> <span data-ttu-id="af050-155">Az összekötőcsoport a funkcionális profil része, amely össze van kötve az azonos funkciókat végrehajtó pénzügyi összekötőkkel, és a pénzügyi regisztrációs folyamat azonos szakaszában használt.</span><span class="sxs-lookup"><span data-stu-id="af050-155">A connector group is a subset of functional profiles linked with fiscal connectors that perform identical functions and are used at the same stage within a fiscal registration process.</span></span>

   - <span data-ttu-id="af050-156">Működési profilok hozzáadása az összekötőcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="af050-156">Add functional profiles to the connector group.</span></span> <span data-ttu-id="af050-157">Kattintson a **Hozzáadás** lehetőségre a **Funkcionális profilok** lapon, majd válassza ki a profil számát.</span><span class="sxs-lookup"><span data-stu-id="af050-157">Click **Add** on the **Functional profiles** page and select a profile number.</span></span>
   - <span data-ttu-id="af050-158">Ha fel szeretné függeszteni a működési profil használatát, a **Letiltás** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="af050-158">If you want to suspend usage of the functional profile, set **Disable** to **Yes**.</span></span> 
   
     <span data-ttu-id="af050-159">Ez a módosítás csak az aktuális összekötőcsoportot érinti.</span><span class="sxs-lookup"><span data-stu-id="af050-159">This change affects the current connector group only.</span></span> <span data-ttu-id="af050-160">Ugyanazt a funkcionális profilt az egyéb összekötőcsoportokban továbbra is használhatja.</span><span class="sxs-lookup"><span data-stu-id="af050-160">You can continue using the same functional profile in other connector groups.</span></span>

     >[!NOTE]
     > <span data-ttu-id="af050-161">Egy összekötőcsoporton belül minden egyes pénzügyi összekötő csak egy funkcionális profillal rendelkezhet.</span><span class="sxs-lookup"><span data-stu-id="af050-161">Within a connector group, each fiscal connector can only have one functional profile.</span></span>

- <span data-ttu-id="af050-162">Hozzon létre egy **Összekötő műszaki profilt** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Összekötő funkcionális profilok** elemnél az egyes pénzügyi összekötőkhöz.</span><span class="sxs-lookup"><span data-stu-id="af050-162">Create a **Connector technical profile** in **Retail > Channel setup > Fiscal integration > Connector technical profiles** for each fiscal connector.</span></span>
  - <span data-ttu-id="af050-163">Válasszon ki egy összekötőnevet.</span><span class="sxs-lookup"><span data-stu-id="af050-163">Select a connector name.</span></span>
  - <span data-ttu-id="af050-164">Válasszon ki egy összekötőtípust.</span><span class="sxs-lookup"><span data-stu-id="af050-164">Select a connector type:</span></span> 
      - <span data-ttu-id="af050-165">**Helyi** – Állítsa be ezt a típust a fizikai eszközökhöz vagy a helyi számítógépen telepített alkalmazásokhoz.</span><span class="sxs-lookup"><span data-stu-id="af050-165">**Local** - Set this type for physical devices or applications installed on a local machine.</span></span>
      - <span data-ttu-id="af050-166">**Belső** – Állítsa be ezt a típust a kiskereskedelmi kiszolgálóhoz kapcsolódó pénzügyi eszközökhöz és szolgáltatásokhoz.</span><span class="sxs-lookup"><span data-stu-id="af050-166">**Internal** - Set this type for fiscal devices and services connected to Retail Server.</span></span>
      - <span data-ttu-id="af050-167">**Külső** – Állítsa be ezt a típust a külső pénzügyi szolgáltatásokhoz, például az adóhatóság által megadott külső webportálokhoz.</span><span class="sxs-lookup"><span data-stu-id="af050-167">**External** - For external fiscal services like a web-portal provided by a tax authority.</span></span>
    
  - <span data-ttu-id="af050-168">A beállításokat adja meg a **Kapcsolat** lapon.</span><span class="sxs-lookup"><span data-stu-id="af050-168">Specify settings on the **Connection** tab.</span></span>

      
 >[!NOTE]
 > <span data-ttu-id="af050-169">Egy korábban betöltött konfiguráció frissített változata lesz betöltve a funkcionális és a műszaki profilokhoz is.</span><span class="sxs-lookup"><span data-stu-id="af050-169">An updated version of a configuration that was loaded earlier will be loaded for both functional and technical profiles.</span></span> <span data-ttu-id="af050-170">Ha egy megfelelő összekötő vagy dokumentum szolgáltató már használatban van, akkor értesítést kap.</span><span class="sxs-lookup"><span data-stu-id="af050-170">If an appropriate connector or document provider is already in use, you will be notified.</span></span> <span data-ttu-id="af050-171">Alapértelmezés szerint a funkcionális és a műszaki profilokban saját kezűleg végrehajtott összes módosítás tárolva lesz.</span><span class="sxs-lookup"><span data-stu-id="af050-171">By default, all changes that have been made manually in functional and technical profiles will be stored.</span></span> <span data-ttu-id="af050-172">Annak érdekében, hogy ezeket a profilok a konfigurációból származó paraméterek alapértelmezett csoportjával felülbírálja, kattintson a **Frissítés** elemre az **Összekötő funkcionális profil** lapon és az **Összekötő műszaki profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="af050-172">In order to override these profiles with the default set of parameters from a configuration, click **Update** on the **Connector functional profiles** page and **Connector technical profiles** page.</span></span>
 
- <span data-ttu-id="af050-173">Hozzon létre egy **Pénzügyi regisztráció folyamatot** itt: **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Pénzügyi regisztrációs eljárás**, a pénzügyi integráció minden egyedi folyamatához.</span><span class="sxs-lookup"><span data-stu-id="af050-173">Create a **Fiscal registration process** in **Retail > Channel setup > Fiscal integration > Fiscal registration processes** for each unique process of the fiscal integration.</span></span> <span data-ttu-id="af050-174">A regisztrációs folyamatot a regisztrációs lépések sorrendje, és az egyes lépéseknél használt összekötőcsoport határozza meg.</span><span class="sxs-lookup"><span data-stu-id="af050-174">A registration process is defined by the sequence of the registration steps and the connector group used on each step.</span></span> 
  
  - <span data-ttu-id="af050-175">Regisztráció lépéseket adjon hozzá a folyamathoz:</span><span class="sxs-lookup"><span data-stu-id="af050-175">Add registration steps to the process:</span></span>
      - <span data-ttu-id="af050-176">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="af050-176">Click **Add**.</span></span>
      - <span data-ttu-id="af050-177">Válasszon ki egy összekötőtípust.</span><span class="sxs-lookup"><span data-stu-id="af050-177">Select a connector type.</span></span>
      
      >[!NOTE]
      > <span data-ttu-id="af050-178">Ez a mező határozza meg, hogy a rendszer hol keresi az összekötőt a műszaki profilban, vagy a hardverprofilokban a **helyi** összekötőtípusnál, vagy a POS-funkcióprofilokban az egyéb pénzügyiösszekötő-típusoknál.</span><span class="sxs-lookup"><span data-stu-id="af050-178">This field defines where the system will search in a technical profile for the connector, either in hardware profiles for connector type **Local**, or in POS functionality profiles for other fiscal connector types.</span></span>
      
   - <span data-ttu-id="af050-179">Válasszon ki egy összekötőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="af050-179">Select a connector group.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="af050-180">Kattintson az **Érvényesítés** elemre a regisztrációs folyamat szerkezeti integritásának ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="af050-180">Click **Validate** to check the integrity of the registration process structure.</span></span> <span data-ttu-id="af050-181">Ellenőrzéseket végezni a következő esetekben ajánlott:</span><span class="sxs-lookup"><span data-stu-id="af050-181">It’s recommended that validations be made in the following cases:</span></span>
       >- <span data-ttu-id="af050-182">Egy új regisztrációs folyamathoz, miután minden beállítás befejeződött, többek között a POS-funkcióprofilok és hardverprofilok kötése.</span><span class="sxs-lookup"><span data-stu-id="af050-182">For a new registration process after all the settings are completed, including binding to POS functionality profiles and hardware profiles.</span></span>
       >- <span data-ttu-id="af050-183">Miután frissítéseket hajtottak végre egy meglévő regisztrációs folyamaton.</span><span class="sxs-lookup"><span data-stu-id="af050-183">After making updates to an existing registration process.</span></span>

-  <span data-ttu-id="af050-184">A pénzügyi regisztrációs folyamatok kötése a POS-funkcióprofilokhoz: **Kiskereskedelem > Csatorna beállítása > POS-beállítás > POS-profilok > Funkcióprofilok**.</span><span class="sxs-lookup"><span data-stu-id="af050-184">Bind fiscal registration processes to POS functionality profiles in **Retail > Channel setup > POS setup > POS profiles > Functionality profiles**.</span></span>
   - <span data-ttu-id="af050-185">Kattintson a **Szerkesztés** elemre, és válassza ki a **Folyamatszám** elemet a **Pénzügyi regisztrációs folyamat** lapon.</span><span class="sxs-lookup"><span data-stu-id="af050-185">Click **Edit** and select a **Process number** on the **Fiscal registration process** tab.</span></span>
- <span data-ttu-id="af050-186">Az összekötő műszaki profilok kötése a hardverprofilokhoz: **Kiskereskedelem > Csatorna beállítása > POS-beállítás > POS-profilok > Hardverprofilok**.</span><span class="sxs-lookup"><span data-stu-id="af050-186">Bind the connector technical profiles to the hardware profiles in **Retail > Channel setup > POS setup > POS profiles > Hardware profiles**.</span></span>
   - <span data-ttu-id="af050-187">Kattintson a **Szerkesztés** elemre, majd kattintson az **Új** elemre a **Pénzügyi műszaki profil** lapon.</span><span class="sxs-lookup"><span data-stu-id="af050-187">Click **Edit**, then click **New** on the **Fiscal technical profile** tab.</span></span>
   - <span data-ttu-id="af050-188">Válasszon egy összekötő műszaki profilt a **Profil száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="af050-188">Select a connector technical profile in the **Profile number** field.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="af050-189">Egy hardverprofilhoz több technikai profilt adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="af050-189">You can add several technical profiles to a hardware profile.</span></span> <span data-ttu-id="af050-190">Azonban ez nem támogatott, ha a hardverprofilnak egynél több metszete van bármely összekötőcsoporttal.</span><span class="sxs-lookup"><span data-stu-id="af050-190">However, this is not supported if a hardware profile has more than one intersection with any connector group.</span></span> <span data-ttu-id="af050-191">A helytelen beállítások elkerülése érdekében azt ajánljuk, hogy az összes hardverprofil frissítése után ellenőrizze a regisztrációs folyamatot.</span><span class="sxs-lookup"><span data-stu-id="af050-191">To avoid incorrect settings, it’s recommended that you validate the registration process after updating all the hardware profiles.</span></span>

