---
title: Forrásnál levont indiai adó (TDS) áttekintése
description: Ez a témakör részletes információkat nyújt a forrásnál levont indiai adóról (TDS). A TDS dokumentáció lefedi ennek a képességnek a funkcionalitását.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023311"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="7820b-104">Forrásnál levont indiai adó (TDS) áttekintése</span><span class="sxs-lookup"><span data-stu-id="7820b-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7820b-105">Ez a témakör részletes információkat nyújt a forrásnál levont indiai adóról (TDS).</span><span class="sxs-lookup"><span data-stu-id="7820b-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="7820b-106">A TDS dokumentáció lefedi ennek a képességnek a funkcionalitását.</span><span class="sxs-lookup"><span data-stu-id="7820b-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="7820b-107">Azt is elmagyarázza, hogyan kell elvégezni a TDS alapbeállítását, kiszámítani a TDS-t a tranzakciókon, befejezni a TDS-elszámolási folyamatot, rögzíteni a TDS-tanúsítványszámokat, és TDS-lekérdezéseket, TDS-kimutatásokat és TDS-tanúsítványokat generálni.</span><span class="sxs-lookup"><span data-stu-id="7820b-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="7820b-108">A dokumentáció a következő témaköröket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="7820b-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="7820b-109">Az TDS alapbeállításai</span><span class="sxs-lookup"><span data-stu-id="7820b-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="7820b-110">A TDS kiszámításához használt képlettervező és küszöbértékkorlát funkció</span><span class="sxs-lookup"><span data-stu-id="7820b-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="7820b-111">TDS kiszámítása számlákon, kifizetéseken, kötelezvényeken és vállalatközi tranzakciókon</span><span class="sxs-lookup"><span data-stu-id="7820b-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="7820b-112">A TDS-adatok időszakos kiegyenlítési folyamata és elszámolása a TDS-hatóság szállítói számára</span><span class="sxs-lookup"><span data-stu-id="7820b-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="7820b-113">TDS-tanúsítványszámok és dátumok rögzítése és frissítése</span><span class="sxs-lookup"><span data-stu-id="7820b-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="7820b-114">Bevezetés a TDS-be</span><span class="sxs-lookup"><span data-stu-id="7820b-114">Introduction to TDS</span></span>

<span data-ttu-id="7820b-115">A jövedelemadóról szóló 1961. évi törvény értelmében a jövedelemadót a szolgáltatás igénybevevője levonja a forrásnál az előlegfizetés vagy a jóváírás elkönyvelésekor, attól függően, hogy melyik következik be először.</span><span class="sxs-lookup"><span data-stu-id="7820b-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="7820b-116">A fizetést végző személynek le kell vonnia az adó összegét, és csak a nettó egyenleget kell kifizetnie a szolgáltatónak.</span><span class="sxs-lookup"><span data-stu-id="7820b-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="7820b-117">A TDS-t a kormány által meghatározott szolgáltatásokra alkalmazzák, és az adót a kormány által meghatározott adómértékek alkalmazásával vonják le egy időszakra.</span><span class="sxs-lookup"><span data-stu-id="7820b-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="7820b-118">A levonás mértéke a kifizetést kapó vagy a szolgáltatást nyújtó entitás állapotán alapul.</span><span class="sxs-lookup"><span data-stu-id="7820b-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="7820b-119">A státuszok közé tartozik az **Egyéni**, **Hindu osztatlan család** (**HUF**), **Vállalat**, **Cég**, **Személyügyi szövetség** (**AOP**), **Magánszemélyek testülete** (**BOI**) és az **Önkormányzat**.</span><span class="sxs-lookup"><span data-stu-id="7820b-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="7820b-120">A következő szakaszok felsorolják azokat a szolgáltatásokat, amelyeken a TDS-t alkalmazzák, az indiai kormány által meghatározottak szerint.</span><span class="sxs-lookup"><span data-stu-id="7820b-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="7820b-121">**Lakosok**</span><span class="sxs-lookup"><span data-stu-id="7820b-121">**Residents**</span></span>

- <span data-ttu-id="7820b-122">Fizetésből származó jövedelem (192. szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="7820b-123">Értékpapírkamatból származó jövedelem (193. szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="7820b-124">Osztalékból származó jövedelem (194. szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="7820b-125">Kamatból származó jövedelem (194A szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="7820b-126">Lottóból vagy rejtvényekből származó jövedelem (194B szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="7820b-127">Lóversenyek megnyerése stb. (194BB szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="7820b-128">Vállalkozók és alvállalkozók (194C szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="7820b-129">Biztosítási jutalék (194D szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="7820b-130">A nemzeti megtakarítási rendszer keretében elhelyezett betétből származó jövedelem (194EE szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="7820b-131">Befektetési alapból vagy UTI-ból származó jövedelem (194F szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="7820b-132">Jutalék, díjazás, nyeremény stb., eladás vagy lottó (194G szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="7820b-133">Jutalék vagy közvetítői kifizetés (a 194H szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="7820b-134">Bérleti díj (194I szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="7820b-135">Szakmai szolgáltatás (194J szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="7820b-136">Egységekből származó jövedelem (194K szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="7820b-137">Egyes ingatlanok megszerzéséért járó kártérítés kifizetése (194LA szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="7820b-138">**Nem rezidensek**</span><span class="sxs-lookup"><span data-stu-id="7820b-138">**Non-residents**</span></span>

- <span data-ttu-id="7820b-139">Kifizetések nem rezidens sportolók vagy sportegyesületek részére (194E szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="7820b-140">Egyéb összegek (195. szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="7820b-141">A nem rezidensek egységeiből származó jövedelem (196A szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="7820b-142">Az Indiai Társaság devizakötvényeiből vagy részvényeiből származó jövedelem (196C szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="7820b-143">Külföldi intézményi befektetők értékpapírból származó jövedelmei (196D szakasz szerint)</span><span class="sxs-lookup"><span data-stu-id="7820b-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="7820b-144">Fizetés és minden egyéb pozitív jövedelem bármely jövedelem alatt (192. szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="7820b-145">Értékpapírok kamata (193. szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="7820b-146">Értékpapírok kamatán kívüli kamat (194A szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="7820b-147">Vállalkozók és alvállalkozók kifizetései (194C szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="7820b-148">Nyeremények lottóból vagy keresztrejtvényekből (194B szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="7820b-149">Lóversenyek nyereményei (194BB szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="7820b-150">Biztosítási Bizottság, amely fedezi a biztosítási tevékenység megszerzéséért járó összes kifizetést (194D szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="7820b-151">A nem vállalati nem rezidensek vagy külföldi társaság részére fizetendő értékpapírok kamatán kívüli kamatok (195. szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="7820b-152">Kifizetés nem rezidens sportolónak, beleértve a sportolót, a sportegyesületet vagy az intézményt.</span><span class="sxs-lookup"><span data-stu-id="7820b-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="7820b-153">A nem rezidens sportoló esetében a kifizetések tekintetében hirdetések, valamint az indiai újságokban, magazinokban stb. megjelenő összes játék/sport cikk.</span><span class="sxs-lookup"><span data-stu-id="7820b-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="7820b-154">szerepel (194E szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="7820b-155">Kifizetés az NSS \[Nemzeti Megtakarítási Rendszer\] (194EE szakasz) szerinti betétek tekintetében</span><span class="sxs-lookup"><span data-stu-id="7820b-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="7820b-156">Kifizetés befektetési alapok, azaz UTI által történő visszavásárlás miatt (194F szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="7820b-157">Jutalékért vagy közvetítésért járó kifizetés (194H szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="7820b-158">Bérleti díj megfizetése (194I szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="7820b-159">Szakmai vagy műszaki szolgáltatások díjának megfizetése (194J szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="7820b-160">A lottójegy részvényesek, forgalmazók, vevők és eladók jutaléka, beleértve az ilyen jegyek fizetését vagy díját (194G szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="7820b-161">Devizában vásárolt befektetési jegyekből származó jövedelem vagy a devizában vásárolt ilyen egységek átruházásából származó hosszú távú tőkenyereség (196B szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="7820b-162">A nem rezidensek részére a kötvényekre és részvényekre vonatkozó kamat vagy osztalék tekintetében származó jövedelem kifizetése (196C szakasz)</span><span class="sxs-lookup"><span data-stu-id="7820b-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="7820b-163">A TDS kiszámítása a vásárlások, eladások, értékesítési hozamok, jóváírások, tárgyi eszközök beszerzései, előtörlesztések, előlegek, kötelezvények, munkák utáni adó és vállalatközi tranzakciók alapján történik.</span><span class="sxs-lookup"><span data-stu-id="7820b-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="7820b-164">A jelenlegi indiai adózási forgatókönyv szerint a TDS-t nem számítják ki az értékesítési tranzakciókra.</span><span class="sxs-lookup"><span data-stu-id="7820b-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="7820b-165">A rendszer azonban tartalmaz egy rendelkezést az értékesítési tranzakciókra visszaigényelhető TDS kiszámítására, különösen a vállalatközi tranzakciók esetében.</span><span class="sxs-lookup"><span data-stu-id="7820b-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="7820b-166">A TDS kiszámítása mindig figyelembe veszi a TDS-összetevőre meghatározott küszöbértéket és kivételi küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="7820b-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="7820b-167">Az időszakos TDS-elszámolási folyamatot le kell futtatni, és a TDS-kifizetéseket el kell rendezni a TDS-hatóság szállítóinak.</span><span class="sxs-lookup"><span data-stu-id="7820b-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="7820b-168">A szállítóktól vagy ügyfelektől kapott TDS-tanúsítványok tanúsítványszámai és dátumai rögzíthetők és frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="7820b-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="7820b-169">Ezenkívül a Pénzügyekben a 26Q és a 27Q űrlap negyedéves kimutatásai, valamint a TDS 16A űrlapbizonyítványa is generálható.</span><span class="sxs-lookup"><span data-stu-id="7820b-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="7820b-170">A TDS beállítása és működése</span><span class="sxs-lookup"><span data-stu-id="7820b-170">Setting up and working with TDS</span></span>

<span data-ttu-id="7820b-171">Az alábbiakban áttekintést adunk a TDS beállításának és működésének folyamatáról:</span><span class="sxs-lookup"><span data-stu-id="7820b-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="7820b-172">**TDS-beállítás:**</span><span class="sxs-lookup"><span data-stu-id="7820b-172">**TDS setup:**</span></span>

    - <span data-ttu-id="7820b-173">Paraméterek beállítása:</span><span class="sxs-lookup"><span data-stu-id="7820b-173">Parameter setup:</span></span>

        - <span data-ttu-id="7820b-174">A Főkönyvi paraméterekben aktiválja a TDS-hez kapcsolódó paramétereket.</span><span class="sxs-lookup"><span data-stu-id="7820b-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="7820b-175">A Főkönyvi paraméterekben állítsa be az adóelőleg-fizetések számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="7820b-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="7820b-176">Paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében.</span><span class="sxs-lookup"><span data-stu-id="7820b-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="7820b-177">Alapbeállítás:</span><span class="sxs-lookup"><span data-stu-id="7820b-177">Basic setup:</span></span>

        - <span data-ttu-id="7820b-178">TDS-regisztrációs számok beállítása egy vállalat, ügyfelek és szállítók számára.</span><span class="sxs-lookup"><span data-stu-id="7820b-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="7820b-179">TDS-összetevő csoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="7820b-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="7820b-180">TDS-összetevők beállítása, TDS-összetevők csoportjainak csatolása hozzájuk, és a küszöbérték és a kivételi küszöbérték meghatározása.</span><span class="sxs-lookup"><span data-stu-id="7820b-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="7820b-181">TDS-hatóságok felállítása.</span><span class="sxs-lookup"><span data-stu-id="7820b-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="7820b-182">TSD-elszámolási időszakok beállítása.</span><span class="sxs-lookup"><span data-stu-id="7820b-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="7820b-183">Állítsa be a TDS-adókódokat, és csatolja hozzájuk a TDS-összetevőket.</span><span class="sxs-lookup"><span data-stu-id="7820b-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="7820b-184">Állítsa be a TDS-adócsoportokat, és csatolja hozzájuk a TDS-adókódokat.</span><span class="sxs-lookup"><span data-stu-id="7820b-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="7820b-185">A képlettervezőben definiáljon egy képletet egy TDS-csoport TDS-ének kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="7820b-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="7820b-186">TDS koncessziós tanúsítvány számának rögzítése.</span><span class="sxs-lookup"><span data-stu-id="7820b-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="7820b-187">Főkönyvi számlák és a vállalat beállítása:</span><span class="sxs-lookup"><span data-stu-id="7820b-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="7820b-188">TDS beállítása főkönyvi kötelezettségekhez és kinnlevőségekhez.</span><span class="sxs-lookup"><span data-stu-id="7820b-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="7820b-189">Hozzon létre egy adólevonási és beszedési számlaszámot (TAN) és egy levonó típuskategóriát a vállalat számára.</span><span class="sxs-lookup"><span data-stu-id="7820b-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="7820b-190">Egyéb beállítás:</span><span class="sxs-lookup"><span data-stu-id="7820b-190">Other setup:</span></span>

        - <span data-ttu-id="7820b-191">Állítson be egy fizetési ütemezést, amely tartalmazza a TDS-felosztást.</span><span class="sxs-lookup"><span data-stu-id="7820b-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="7820b-192">Kifizetésidíj-típus beállítása a TDS-hatóságnak történő fizetések esetében.</span><span class="sxs-lookup"><span data-stu-id="7820b-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="7820b-193">A TDS-csoportokra, az állandó számlaszámokra (PAN-ok) és a szállítók és vevők TAN-jaira vonatkozó információk beállítása.</span><span class="sxs-lookup"><span data-stu-id="7820b-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="7820b-194">**TDS-számítás a tranzakciókban:**</span><span class="sxs-lookup"><span data-stu-id="7820b-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="7820b-195">Számlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="7820b-195">Invoices and payments</span></span>
    - <span data-ttu-id="7820b-196">Kötelezvények</span><span class="sxs-lookup"><span data-stu-id="7820b-196">Promissory notes</span></span>
    - <span data-ttu-id="7820b-197">Előlegfizetések</span><span class="sxs-lookup"><span data-stu-id="7820b-197">Advance payments</span></span>
    - <span data-ttu-id="7820b-198">Előlegek</span><span class="sxs-lookup"><span data-stu-id="7820b-198">Prepayments</span></span>

3. <span data-ttu-id="7820b-199">**TDS-elszámolás:**</span><span class="sxs-lookup"><span data-stu-id="7820b-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="7820b-200">Időszakos TDS-elszámolási folyamat</span><span class="sxs-lookup"><span data-stu-id="7820b-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="7820b-201">TDS-kifizetések elszámolása TDS-hatósági szállítóknak és TDS-challan generálása</span><span class="sxs-lookup"><span data-stu-id="7820b-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="7820b-202">**TDS-vizsgálatok, nyilatkozatok és tanúsítványok:**</span><span class="sxs-lookup"><span data-stu-id="7820b-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="7820b-203">TDS-tanúsítványszámok és dátumok rögzítése és frissítése.</span><span class="sxs-lookup"><span data-stu-id="7820b-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="7820b-204">TDS-lekérdezés és kiküldött TDS-lekérdezés létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7820b-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="7820b-205">A 27A, a 26Q űrlap és a 27Q TDS űrlap és az e-TDS negyedéves kimutatásainak létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7820b-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="7820b-206">16A űrlap TDS-tanúsítvány létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7820b-206">Generate a Form 16A TDS certificate.</span></span>
