---
title: "A toborzási folyamat kezelése"
description: "Ez a cikk egy fogalom recruiters segítségével nyomon követheti a lépéseket a toborzási folyamatban, többek között a nyitott pozíciók hirdetése és a pályázók felvételéhez szükséges, pályázó és az alkalmazás nyomon követésére, kikérdezése pályázók és egy vagy több jelöltek ki kell töltenie a szervezeten belüli nyitott pozíciók kiválasztása."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7a1db481105a5b3422414c3b4e53ddee0a563df
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="manage-a-recruiting-process"></a><span data-ttu-id="395b6-103">A toborzási folyamat kezelése</span><span class="sxs-lookup"><span data-stu-id="395b6-103">Manage a recruiting process</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="395b6-104">Ez a témakör egy olyan koncepciót ismertet, amellyel a toborzók követhetik a toborzási folyamat lépéseit, köztük a nyitott beosztások meghirdetését és a pályázók felvételét, követhetik a pályázók és pályázatok adatait, pályázókat interjúztathatnak, és kiválaszthatak egy vagy több jelöltet a szervezet nyitott beosztásainak betöltésére.</span><span class="sxs-lookup"><span data-stu-id="395b6-104">This topic describes a concept that recruiters can use to track the steps in a recruiting process, including efforts to advertise open positions and recruit applicants, tracking applicant and application information, interviewing applicants, and selecting one or more candidates to fill the open positions in your organization.</span></span>

<a name="overview"></a><span data-ttu-id="395b6-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="395b6-105">Overview</span></span>
--------

<span data-ttu-id="395b6-106">Toborzási projektek is megkönnyítik a lépéseket is hajtsa végre a jogi személyben nyitott pozíciók kitöltésekor.</span><span class="sxs-lookup"><span data-stu-id="395b6-106">Recruitment projects can help you organize the steps you'll complete when filling open positions in a legal entity.</span></span> <span data-ttu-id="395b6-107">A pályázó olyan személy, aki állásra pályázik a vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="395b6-107">An applicant is a person who applies for employment to your enterprise.</span></span>  <span data-ttu-id="395b6-108">A pályázat a pályázó érdeklődésének kifejezése, amely szerint szeretne dolgozni egy vállalatnál; ez egy konkrét nyitott pozícióhoz kapcsolódó toborzási projekthez tartozhat.</span><span class="sxs-lookup"><span data-stu-id="395b6-108">An application is an applicant's expression of interest in being employed by a company and may be tied to a recruitment project to express interest in a specific opening.</span></span>  <span data-ttu-id="395b6-109">Egy pályázó több pályázatot is leadhat ugyanazon jogi személyhez, illetve több vállalathoz a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="395b6-109">A single applicant may have multiple applications within the same legal entity or across multiple companies in your organization.</span></span>

<a name="recruitment-projects"></a><span data-ttu-id="395b6-110">Toborzási projektek</span><span class="sxs-lookup"><span data-stu-id="395b6-110">Recruitment projects</span></span>
--------------------

<span data-ttu-id="395b6-111">A toborzási projektek lehetővé teszik a felvétellel foglalkozók számára egy vagy több nyitott pozíció betöltési folyamatának követését.</span><span class="sxs-lookup"><span data-stu-id="395b6-111">Recruitment projects allow recruiters to track progress against filling one or more open positions.</span></span>  <span data-ttu-id="395b6-112">A toborzási projekt azonosítja a részleget és a munkát, amelyre nézve egy vagy több beosztás nyitva van.</span><span class="sxs-lookup"><span data-stu-id="395b6-112">The recruitment project identifies the department and job for which one or more positions are open.</span></span> <span data-ttu-id="395b6-113">Toborzási projektek is nyomon követhető következő nyitott pozíciók vonatkozó információkat:</span><span class="sxs-lookup"><span data-stu-id="395b6-113">Recruitment projects also track following information for open positions:</span></span>
-   <span data-ttu-id="395b6-114">Nyitott pozíciók egyedi száma</span><span class="sxs-lookup"><span data-stu-id="395b6-114">The specific number of open positions</span></span>
-   <span data-ttu-id="395b6-115">A felvételi vezető és a beosztás egy másodlagos kapcsolattartó</span><span class="sxs-lookup"><span data-stu-id="395b6-115">The hiring manager and an alternative contact for the position</span></span>
-   <span data-ttu-id="395b6-116">A tranzakció jóváhagyásának dátuma</span><span class="sxs-lookup"><span data-stu-id="395b6-116">The date that the requisition was approved</span></span>
-   <span data-ttu-id="395b6-117">Jelentkezési határidő</span><span class="sxs-lookup"><span data-stu-id="395b6-117">The application deadline</span></span>
-   <span data-ttu-id="395b6-118">Becsült kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="395b6-118">The estimated start date</span></span>

<span data-ttu-id="395b6-119">A toborzási projektben a **Álláshirdetés** használja a **Alkalmazotti önkiszolgáló áruház** számára, hogy a nyitó.</span><span class="sxs-lookup"><span data-stu-id="395b6-119">The recruitment project contains the **Job ad** used on the **Employee self service** to advertise the opening.</span></span> <span data-ttu-id="395b6-120">Meg szeretné jeleníteni a nyitó hozzá az alkalmazottakhoz, a toborzási projekt rendelkeznie kell egy **álláshirdetés**, a **megjelenítése az alkalmazotti önkiszolgáló szolgáltatás** mezőt be kell állítani az Igen, a **Jelentkezési határidő** egy jövőbeli dátumot kell megadni, és a toborzási projekt kell egy **projekt állapota** elindítva.</span><span class="sxs-lookup"><span data-stu-id="395b6-120">To display the opening to employees, the recruitment project must have a **Job ad**, the **Display on employee self service** field must be set to Yes, the **Application deadline** must be set to a future date, and the recruitment project must have a **Project status** of Started.</span></span> <span data-ttu-id="395b6-121">Az alábbi táblázat felsorolja toborzási projektek lehetséges állapotait és azok leírását.</span><span class="sxs-lookup"><span data-stu-id="395b6-121">The following table lists the possible recruitment project statuses and their description.</span></span>

| <span data-ttu-id="395b6-122">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="395b6-122">**Status**</span></span>    | <span data-ttu-id="395b6-123">**Értelmezés...**</span><span class="sxs-lookup"><span data-stu-id="395b6-123">**Indicates that…**</span></span>                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| <span data-ttu-id="395b6-124">Ütemezve</span><span class="sxs-lookup"><span data-stu-id="395b6-124">Scheduled</span></span> | <span data-ttu-id="395b6-125">Toborzás erőfeszítések előkészítés alatt.</span><span class="sxs-lookup"><span data-stu-id="395b6-125">Recruiting efforts are being prepared.</span></span>  <span data-ttu-id="395b6-126">A toborzás még nem indult meg ennél a projektnél.</span><span class="sxs-lookup"><span data-stu-id="395b6-126">Recruiting has not yet started for this project.</span></span> |
| <span data-ttu-id="395b6-127">Elkezdve</span><span class="sxs-lookup"><span data-stu-id="395b6-127">Started</span></span>   | <span data-ttu-id="395b6-128">Alkalmazások most éppen elfogadható a betöltendő pozíciók ebbe a projektbe.</span><span class="sxs-lookup"><span data-stu-id="395b6-128">Applications are now being accepted for the openings in this project.</span></span>                    |
| <span data-ttu-id="395b6-129">Befejezve</span><span class="sxs-lookup"><span data-stu-id="395b6-129">Finished</span></span>  | <span data-ttu-id="395b6-130">Minden betöltendő pozíciók, a projekt ki van töltve.</span><span class="sxs-lookup"><span data-stu-id="395b6-130">All openings for this project have been filled.</span></span>                                          |
| <span data-ttu-id="395b6-131">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="395b6-131">Canceled</span></span>  | <span data-ttu-id="395b6-132">A tábla szinkronizálása megszakadt.</span><span class="sxs-lookup"><span data-stu-id="395b6-132">Recruiting has been canceled for this project.</span></span>                                           |

<span data-ttu-id="395b6-133">Recruiters is lehet rögzíteni a **Media** hirdetése a nyitó külső értékesítési keresztül, valamint a nyomon követésére használt **Fejlesztések** a projekt vagy alkalmazások szemben.</span><span class="sxs-lookup"><span data-stu-id="395b6-133">Recruiters can also record the **Media** used to advertise the opening through external outlets as well as track **Developments** against the project or applications.</span></span>

<a name="applicants"></a><span data-ttu-id="395b6-134">Pályázók</span><span class="sxs-lookup"><span data-stu-id="395b6-134">Applicants</span></span>
----------

<span data-ttu-id="395b6-135">A pályázó olyan személy, aki munkára pályázik a vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="395b6-135">An applicant is a person who applies for a job in your enterprise.</span></span>  <span data-ttu-id="395b6-136">A pályázók a szervezet összes jogi személye között megoszlanak, így Ön nagy kínálatban kereshet.</span><span class="sxs-lookup"><span data-stu-id="395b6-136">Applicants are shared among all legal entities in your organization giving you a large pool of talent to search from.</span></span> <span data-ttu-id="395b6-137">Megadhat és karban tarthat személyes információkat, állásinterjú dátumokat és időpontokat, referenciákat, kompetenciákat és a pályázó kérvényeit.</span><span class="sxs-lookup"><span data-stu-id="395b6-137">You can maintain competencies, references, accommodation requests, and personal information for applicants.</span></span> <span data-ttu-id="395b6-138">Ha létrehoz egy pályázói rekordot, egy személyes rekord jön létre a pályázószámára a globális címjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="395b6-138">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span> <span data-ttu-id="395b6-139">Használhatja a **Jelentkező** lap frissítése a következő globális címjegyzék adatait a pályázók számára:</span><span class="sxs-lookup"><span data-stu-id="395b6-139">You can use the **Applicant** page to update the following global address book information for people who are applicants:</span></span>
-   <span data-ttu-id="395b6-140">Címadatok</span><span class="sxs-lookup"><span data-stu-id="395b6-140">Address information</span></span>
-   <span data-ttu-id="395b6-141">Kapcsolattartási adatok</span><span class="sxs-lookup"><span data-stu-id="395b6-141">Contact information</span></span>
-   <span data-ttu-id="395b6-142">Azonosító adatok megtekintése</span><span class="sxs-lookup"><span data-stu-id="395b6-142">Identification information</span></span>
-   <span data-ttu-id="395b6-143">Név részletei</span><span class="sxs-lookup"><span data-stu-id="395b6-143">Name details</span></span>
-   <span data-ttu-id="395b6-144">Személyes információk</span><span class="sxs-lookup"><span data-stu-id="395b6-144">Personal information</span></span>

## <a name="applications"></a><span data-ttu-id="395b6-145">Alkalmazások</span><span class="sxs-lookup"><span data-stu-id="395b6-145">Applications</span></span>
<span data-ttu-id="395b6-146">A megkapott alkalmazotti pályázatokból rögzíthet adatokat a **Jelentkezés** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="395b6-146">You can record information from employment applications that you receive in the **Application** page.</span></span> <span data-ttu-id="395b6-147">A pályázat a pályázó érdeklődését fejezi ki a szervezetben megnyílt valamilyen munka iránt.</span><span class="sxs-lookup"><span data-stu-id="395b6-147">The application is the applicant's expression of interest in a job opening in your organization.</span></span>  <span data-ttu-id="395b6-148">Pályázat létrehozásához a pályázónak már léteznie kell pályázóként vagy személyként a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="395b6-148">To create an application, the applicant must already exist as an applicant or person in your system.</span></span>
<span data-ttu-id="395b6-149">Webes pályázó által beküldött alkalmazotti pályázatokat vagy kért azon alkalmazásai, amelyek egy Álláshirdetésre reagálva vittek be, illetve kéretlen pályázatok.</span><span class="sxs-lookup"><span data-stu-id="395b6-149">Employment applications submitted by applicants on the web are either solicited applications that were entered in response to a job ad, or are unsolicited applications.</span></span> <span data-ttu-id="395b6-150">A kért pályázatok automatikusan ahhoz a felvételi projekthez kerülnek, amelyikből a hirdetés létrejött.</span><span class="sxs-lookup"><span data-stu-id="395b6-150">Solicited applications are automatically associated with the recruitment project that the job ad was created from.</span></span> <span data-ttu-id="395b6-151">A toborzási projekt megadott kéretlen pályázatok tartoznak a **Toborzási** területe a **Emberierőforrás-paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="395b6-151">Unsolicited applications are associated with the recruitment project that is specified in the **Recruitment** area of the **Human resources parameters** page.</span></span>
### <a name="application-status"></a><span data-ttu-id="395b6-152">Pályázat állapota</span><span class="sxs-lookup"><span data-stu-id="395b6-152">Application status</span></span>

<span data-ttu-id="395b6-153">A pályázat állapota jelzi, hogy a pályázat hol áll a toborzási folyamatban.</span><span class="sxs-lookup"><span data-stu-id="395b6-153">The application status indicates where an application is in the recruitment process.</span></span> <span data-ttu-id="395b6-154">Az alábbi táblázat felsorolja a lehetséges toborzási projekt állapota, és azok leírását.</span><span class="sxs-lookup"><span data-stu-id="395b6-154">The following table lists the possible application statuses and their description.</span></span>

| <span data-ttu-id="395b6-155">Állapot</span><span class="sxs-lookup"><span data-stu-id="395b6-155">Status</span></span>    | <span data-ttu-id="395b6-156">Értelmezés...</span><span class="sxs-lookup"><span data-stu-id="395b6-156">Indicates that…</span></span>                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="395b6-157">Bevételezve</span><span class="sxs-lookup"><span data-stu-id="395b6-157">Received</span></span>  | <span data-ttu-id="395b6-158">Pályázat beérkezésének dátuma.</span><span class="sxs-lookup"><span data-stu-id="395b6-158">The application was received.</span></span>                                                             |
| <span data-ttu-id="395b6-159">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="395b6-159">Confirmed</span></span> | <span data-ttu-id="395b6-160">A pályázónak egy értesítés lett elküldve a pályázat beérkezésének visszaigazolásáról.</span><span class="sxs-lookup"><span data-stu-id="395b6-160">A notice can be sent to the applicant to confirm receipt of their application.</span></span>            |
| <span data-ttu-id="395b6-161">Interjú</span><span class="sxs-lookup"><span data-stu-id="395b6-161">Interview</span></span> | <span data-ttu-id="395b6-162">A pályázónak egy interjúmeghívás lett elküldve.</span><span class="sxs-lookup"><span data-stu-id="395b6-162">An interview invitation can be sent to the applicant.</span></span>                                     |
| <span data-ttu-id="395b6-163">Elutasítás</span><span class="sxs-lookup"><span data-stu-id="395b6-163">Rejection</span></span> | <span data-ttu-id="395b6-164">A pályázónak egy elutasító levél lett elküldve.</span><span class="sxs-lookup"><span data-stu-id="395b6-164">A rejection letter can be sent to the applicant.</span></span>                                          |
| <span data-ttu-id="395b6-165">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="395b6-165">Canceled</span></span>  | <span data-ttu-id="395b6-166">A pályázónak egy visszavonási visszaigazolás lett elküldve.</span><span class="sxs-lookup"><span data-stu-id="395b6-166">A withdrawal confirmation can be sent to the applicant.</span></span> <span data-ttu-id="395b6-167">Ezt az értéket kézzel rendelik hozzá.</span><span class="sxs-lookup"><span data-stu-id="395b6-167">This status is assigned manually.</span></span> |
| <span data-ttu-id="395b6-168">Alkalmazott</span><span class="sxs-lookup"><span data-stu-id="395b6-168">Employed</span></span>  | <span data-ttu-id="395b6-169">A pályázónak egy felvételi ajánlat lett elküldve.</span><span class="sxs-lookup"><span data-stu-id="395b6-169">An employment offer can be sent to the applicant.</span></span>                                         |

### <a name="correspondence-actions"></a><span data-ttu-id="395b6-170">Levelezési tevékenységek</span><span class="sxs-lookup"><span data-stu-id="395b6-170">Correspondence actions</span></span>

<span data-ttu-id="395b6-171">Egy **Alkalmazás** kapcsolattartási művelet határozza meg, hogy a dokumentum vagy e-mail sablont használó kommunikálni a a pályázatot benyújtó jelentkező.</span><span class="sxs-lookup"><span data-stu-id="395b6-171">An **Application’s** correspondence action determines the document or e-mail template that you use to communicate with the applicant who submitted the application.</span></span> <span data-ttu-id="395b6-172">A **Pályázat könyvjelzői** levelezési műveletekkel társíthatók, aminek köszönhetően a pályázókkal folytatott kommunikáció során felhasználhat értékeket a Pályázat, Pályázó, Interjú és Toborzás projektoldalakról.</span><span class="sxs-lookup"><span data-stu-id="395b6-172">You can associate **Application bookmarks** with correspondence actions to allow you to use values from the Application, Applicant, Interview, and Recruitment project pages in your communications with applicants.</span></span>  <span data-ttu-id="395b6-173">**Pályázat e-mail sablonjai** hozhatók létre a levelezési műveletekhez, és ezekkel gyorsa küldhetők e-mailek azon pályázók számára, akiknek bizonyos állapotú pályázatuk van folyamatban adott levelezési művelettel párosítva.</span><span class="sxs-lookup"><span data-stu-id="395b6-173">**Application e-mail templates** can be created for the correspondence actions to quickly send e-mails to applicants who have an application with a certain status and correspondence action combination.</span></span> <span data-ttu-id="395b6-174">Például visszaigazoló e-mailt küldhet az összes pályázónak, akiknél az **Állapot** Fogadva, és a **Kapcsolattartási művelet** Fogadva.</span><span class="sxs-lookup"><span data-stu-id="395b6-174">For example, you may send a Confirmation e-mail to all Applications with a **Status** of Received and a **Correspondence action** of Received.</span></span>  <span data-ttu-id="395b6-175">Az e-mail elküldése után lehetősége van a pályázat állapotának automatikus frissítésére.</span><span class="sxs-lookup"><span data-stu-id="395b6-175">After sending the e-mail, you have the option to automatically update the status of the applications.</span></span>

## <a name="application-routing"></a><span data-ttu-id="395b6-176">Pályázat útválasztása</span><span class="sxs-lookup"><span data-stu-id="395b6-176">Application routing</span></span>

<span data-ttu-id="395b6-177">Ha egy pályázatot több alkalmazottnak is át kell néznie, akkor a folyamat kezeléséhez a **Pályázat útválasztása**  oldalon létrehozhat egy alkalmazotti terjesztési listát.</span><span class="sxs-lookup"><span data-stu-id="395b6-177">If an application must be reviewed by several workers, you can use the **Application routing** page to create a worker circulation list in order to manage the process.</span></span>

## <a name="interviews"></a><span data-ttu-id="395b6-178">Interjúk</span><span class="sxs-lookup"><span data-stu-id="395b6-178">Interviews</span></span>

<span data-ttu-id="395b6-179">**Pályázói interjúk** a **Pályázatok** oldalon ütemezhetők.</span><span class="sxs-lookup"><span data-stu-id="395b6-179">**Applicant interviews** can be scheduled from the **Applications** page.</span></span>  <span data-ttu-id="395b6-180">Használja az **Értekezlettel kapcsolatos információk küldése** gombot, ha naptárfájlt kíván küldeni az interjú ütemezésének adataival a pályázónak és az interjúztatónak.</span><span class="sxs-lookup"><span data-stu-id="395b6-180">Use the **Send meeting information** button to send a calendar file with the interview schedule information to the applicant and interviewer.</span></span>

## <a name="skill-mapping"></a><span data-ttu-id="395b6-181">Szakértelem feltérképezése</span><span class="sxs-lookup"><span data-stu-id="395b6-181">Skill mapping</span></span>

<span data-ttu-id="395b6-182">**Szakértelem-feltérképezés** és **szakértelem-feltérképezési profilok** lehet egy nyitólap jó közelítést jelentkezőket azonosítására is használható.</span><span class="sxs-lookup"><span data-stu-id="395b6-182">**Skill mapping** and **Skill mapping profiles** can be used to identify candidates who may be a good fit for an opening.</span></span>

## <a name="hiring-applicants"></a><span data-ttu-id="395b6-183">Pályázók felvétele</span><span class="sxs-lookup"><span data-stu-id="395b6-183">Hiring applicants</span></span>

<span data-ttu-id="395b6-184">Használja a **alkalmazások** pályázó lapra.</span><span class="sxs-lookup"><span data-stu-id="395b6-184">Use the **Applications** page to hire an applicant.</span></span> <span data-ttu-id="395b6-185">Pályázó felvételekor az alkalmazás rekord állapotú lesz, **alkalmazott** és az új dolgozói rekordot a kérelmező személy globáliscímjegyzék rekordja kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="395b6-185">When you hire an applicant, the application record will have a status of **Employed** and the applicant’s global address book person record is associated with the new worker record.</span></span> <span data-ttu-id="395b6-186">A globális címjegyzék adatait az új dolgozó rekord módosításai is megjelennek a pályázó rekordját.</span><span class="sxs-lookup"><span data-stu-id="395b6-186">Modifications to the global address book information for the new worker record are also displayed in the applicant record.</span></span> <span data-ttu-id="395b6-187">Így kevesebb adatot kell bevinni, ha az új dolgozó valaha a vállalaton belüli más munkakörre adna be pályázatot.</span><span class="sxs-lookup"><span data-stu-id="395b6-187">This can help reduce data entry if the new worker ever applies for a different job within your enterprise.</span></span>  <span data-ttu-id="395b6-188">Meglévő dolgozó felvételéhez új beosztásba kattintson a **Pozíció módosítása** elemre a **Pályázat állapota** legördülő listában, és az átviteli folyamat megkezdődik.</span><span class="sxs-lookup"><span data-stu-id="395b6-188">To hire an existing worker into a new position, click **Change position** in the **Application status** drop down to initiate the transfer process.</span></span>





