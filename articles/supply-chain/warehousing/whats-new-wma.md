---
title: Újdonságok és változások a Warehouse Management mobilalkalmazásban
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management rendszerhez használatos Warehouse Management mobilalkalmazás egyes kiadásainak új és módosult funkcióit ismerteti.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261780"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="250ab-103">Újdonságok és változások a Warehouse Management mobilalkalmazásban</span><span class="sxs-lookup"><span data-stu-id="250ab-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="250ab-104">Ez a témakör a Microsoft Dynamics 365 Supply Chain Management rendszerhez használatos Warehouse Management mobilalkalmazás egyes kiadásainak új funkcióit, hibajavításait, fejlesztéseit és ismert hibáit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="250ab-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="250ab-105">2.0.6.0-s verzió</span><span class="sxs-lookup"><span data-stu-id="250ab-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="250ab-106">Új funkciók, hibajavítások és fejlesztések a 2.0.6.0 verzióban</span><span class="sxs-lookup"><span data-stu-id="250ab-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="250ab-107">Ez a kiadás az alábbi új funkciókat, hibajavításokat és fejlesztéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="250ab-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="250ab-108">A Bemutató módban mostantól az összes címke az eszköz nyelvén jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="250ab-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="250ab-109">Kevésbé valószínű, hogy megjelenik a következő hibaüzenet: „A megadott mérethez nem található megfelelő nézet”.</span><span class="sxs-lookup"><span data-stu-id="250ab-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="250ab-110">A munkakártyák minimális magassága megnőtt (azokban az esetekben, amikor legfeljebb három mező van beállítva a munkalistában való megjelenésre).</span><span class="sxs-lookup"><span data-stu-id="250ab-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="250ab-111">A részletkártyák alján található margókat (elhalványulva) tökéletesítettük.</span><span class="sxs-lookup"><span data-stu-id="250ab-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="250ab-112">A kiszolgálóval cserélt XML-fájlok érvénytelen szimbólumainak kezelése megfelelően történik.</span><span class="sxs-lookup"><span data-stu-id="250ab-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="250ab-113">(A nem nyomtatható karakterek kezelése például megfelelő, és az ilyen karakterek már nem okozzák az alkalmazás leállását.)</span><span class="sxs-lookup"><span data-stu-id="250ab-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="250ab-114">A kiszolgálói kérések elküldésekor jelentkező HTTP-hibák (például „503-as hiba”) kezelése megfelelően történik.</span><span class="sxs-lookup"><span data-stu-id="250ab-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="250ab-115">Amikor egy hiba megjelenik, a beállítások listája már nem jelenik meg automatikusan a kombinált lista vezérlőkhöz.</span><span class="sxs-lookup"><span data-stu-id="250ab-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="250ab-116">Az alkalmazás már nem áll le a felhasználói beállítások között kiválasztott megjelenítési tájolás miatt.</span><span class="sxs-lookup"><span data-stu-id="250ab-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="250ab-117">A termékek képe mostantól önkiszolgáló környezetben jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="250ab-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="250ab-118">(Ez a módosítás csak a kis felbontású verziókra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="250ab-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="250ab-119">A fájlkezelő szolgáltatás nem támogatja a teljes méretű képek önkiszolgáló környezetben való használatát.)</span><span class="sxs-lookup"><span data-stu-id="250ab-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="250ab-120">Kijavítottuk a nulla mennyiségű rövid kiválasztásokkal kapcsolatos problémát.</span><span class="sxs-lookup"><span data-stu-id="250ab-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="250ab-121">Az alkalmazás már nem áll le, ha egy részletkártya több azonos mezőt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="250ab-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="250ab-122">Ismert problémák a 2.0.6.0 verzióban</span><span class="sxs-lookup"><span data-stu-id="250ab-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="250ab-123">Ebben a verzióban a következő problémák ismertek:</span><span class="sxs-lookup"><span data-stu-id="250ab-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="250ab-124">Az alkalmazás (különösen a munkalista) az idő múlásával lelassul.</span><span class="sxs-lookup"><span data-stu-id="250ab-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="250ab-125">**Windows-verzió:** Ha USB-fegyvert használnak a Windowson történő szkenneléshez, az inkonzisztens eredmények miatt a beolvasott szimbólumok összekeveredésnek.</span><span class="sxs-lookup"><span data-stu-id="250ab-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="250ab-126">2.0.5.0-s verzió</span><span class="sxs-lookup"><span data-stu-id="250ab-126">Version 2.0.5.0</span></span>

<span data-ttu-id="250ab-127">Ez a kiadás az alábbi új funkciókat, hibajavításokat és fejlesztéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="250ab-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="250ab-128">Az ügyfél titkos kódja már nem rejtett a kapcsolat beállításaira szolgáló részen.</span><span class="sxs-lookup"><span data-stu-id="250ab-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="250ab-129">Mostantól a bármelyik szöveg hosszú lenyomásával teljesen megjeleníthető.</span><span class="sxs-lookup"><span data-stu-id="250ab-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="250ab-130">Tökéletesítettük a tárolási engedélyek hiányzása esetén megjelenő hibaüzenetet.</span><span class="sxs-lookup"><span data-stu-id="250ab-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="250ab-131">Egyes folyamatokhoz új vezérlősorozatokat adtunk hozzá.</span><span class="sxs-lookup"><span data-stu-id="250ab-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="250ab-132">A Küldés gomb már nem jelenik meg helytelenül az ablakméret miatt.</span><span class="sxs-lookup"><span data-stu-id="250ab-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="250ab-133">A csúszkák nagyobb gombméret használata esetén kisebb képernyőkön is használhatók.</span><span class="sxs-lookup"><span data-stu-id="250ab-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="250ab-134">A négygombos átfedés már nincs levágva.</span><span class="sxs-lookup"><span data-stu-id="250ab-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="250ab-135">A billentyűzet már támogatja a törlési gombot.</span><span class="sxs-lookup"><span data-stu-id="250ab-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="250ab-136">Kijavítottuk a billentyűzet használatakor előforduló fényerősség-problémát.</span><span class="sxs-lookup"><span data-stu-id="250ab-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="250ab-137">A bemutató adatokkal kapcsolatos különböző problémákat kijavítottuk.</span><span class="sxs-lookup"><span data-stu-id="250ab-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="250ab-138">Kijavítottunk egy, a részletek lapon lévő numerikus mezőket érintő problémát.</span><span class="sxs-lookup"><span data-stu-id="250ab-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="250ab-139">A képernyőbillentyűzet már nem tűnik el időnként egyes eszközökön.</span><span class="sxs-lookup"><span data-stu-id="250ab-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="250ab-140">Kijavítottunk különböző felhasználói felületi hibákat, például azokat, amelyek a háttérszínre és a pozicionálásra voltak hatással.</span><span class="sxs-lookup"><span data-stu-id="250ab-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="250ab-141">Az orosz nyelvű felhasználói felületet tökéletesítettük.</span><span class="sxs-lookup"><span data-stu-id="250ab-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="250ab-142">Számos olyan problémát javítottunk, amely a rendszer leállását okozta.</span><span class="sxs-lookup"><span data-stu-id="250ab-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="250ab-143">A számológép újbóli megnyitásával kapcsolatos problémát kijavítottuk.</span><span class="sxs-lookup"><span data-stu-id="250ab-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="250ab-144">**Android-verzió:** Kijavítottunk egy olyan problémát, amely miatt az Android 4.4 leállt az indításkor.</span><span class="sxs-lookup"><span data-stu-id="250ab-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="250ab-145">**Android-verzió:** A minimális méretezés 50 százalékra csökkent.</span><span class="sxs-lookup"><span data-stu-id="250ab-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="250ab-146">2.0.4.0-s verzió</span><span class="sxs-lookup"><span data-stu-id="250ab-146">Version 2.0.4.0</span></span>

<span data-ttu-id="250ab-147">A 2.0.4.0 verzió volt a Warehouse Management mobilalkalmazás első általánosan elérhető kiadása.</span><span class="sxs-lookup"><span data-stu-id="250ab-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="250ab-148">Új funkciók, hibajavítások és fejlesztések a 2.0.4.0 verzióban</span><span class="sxs-lookup"><span data-stu-id="250ab-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="250ab-149">Ez a verzió az előzetes verzió el nem érhető következő új funkciókat, hibajavításokat és fejlesztéseket kínálja:</span><span class="sxs-lookup"><span data-stu-id="250ab-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="250ab-150">Ha egy részleteket tartalmazó kártya két azonos adatokat mutató címkét tartalmaz, az egyik címke rejtve marad.</span><span class="sxs-lookup"><span data-stu-id="250ab-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="250ab-151">A speciális karakterek alapértelmezés szerint már megjelennek, és az elrejtésükre szolgáló beállítás kikerült a felhasználói beállítások közül.</span><span class="sxs-lookup"><span data-stu-id="250ab-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="250ab-152">A letiltott küldési gombok mostantól nem érhetők el a kompakt, karon használt nézetben.</span><span class="sxs-lookup"><span data-stu-id="250ab-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="250ab-153">A vezérlők sorrendbe állítási logikájának módosítása gördülékenyebb méretezést biztosít az eszközök között.</span><span class="sxs-lookup"><span data-stu-id="250ab-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="250ab-154">Ennek megfelelően a betűtípusok és a gombok méretezését ritkábban kell korrigálni.</span><span class="sxs-lookup"><span data-stu-id="250ab-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="250ab-155">Az alapértelmezett színtéma a *Sötét* lett.</span><span class="sxs-lookup"><span data-stu-id="250ab-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="250ab-156">A letiltott küldési gomb hiányzó ikonját hozzáadtuk a szalagnézetből.</span><span class="sxs-lookup"><span data-stu-id="250ab-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="250ab-157">Az időkorlát túllépése miatti kivételek esetén a felhasználó mostantól a kapcsolat oldalára kerül, és nem hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="250ab-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="250ab-158">Ha nincs használható küldési művelet (pl. **OK**, **Igen**, **Elfogadás**, **Kész** vagy **Befejezve**), akkor a küldésre szolgáló gomb le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="250ab-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="250ab-159">Az alkalmazás stabilabb lett.</span><span class="sxs-lookup"><span data-stu-id="250ab-159">App stability has been improved.</span></span>
- <span data-ttu-id="250ab-160">A [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) biztonsági rést javítottuk.</span><span class="sxs-lookup"><span data-stu-id="250ab-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="250ab-161">**Windows-verzió:** Kijavították azt a windowsos problémát, amely miatt a menük az ablak átméretezése után nem reagáltak.</span><span class="sxs-lookup"><span data-stu-id="250ab-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="250ab-162">Ismert probléma a 2.0.4.0 verzióban</span><span class="sxs-lookup"><span data-stu-id="250ab-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="250ab-163">Ebben a verzióban a következő probléma ismert:</span><span class="sxs-lookup"><span data-stu-id="250ab-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="250ab-164">A verzió Android 4.4-en való használata problémát okozott.</span><span class="sxs-lookup"><span data-stu-id="250ab-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="250ab-165">Problémák merülhettek fel, ha az alkalmazást ezzel az Android-verzióval használja.</span><span class="sxs-lookup"><span data-stu-id="250ab-165">You might experience issues when you use the app on this Android version.</span></span>
