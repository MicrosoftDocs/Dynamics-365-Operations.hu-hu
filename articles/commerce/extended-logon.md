---
title: A kiterjesztett bejelentkezési képesség beállítása és használata
description: Ez a témakör azt ismerteti, Microsoft Dynamics 365 Commerce hogyan lehet beállítani és használni a pénztári alkalmazás kiterjesztett bejelentkezési képességét.
author: boycez
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d211ecfe1550f6093e1d35e7c2b37c036b50dd4a
ms.sourcegitcommit: 5aebb181004eb63210503fb566dcda5c55032bee
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491439"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>A kiterjesztett bejelentkezési képesség beállítása és használata

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, Microsoft Dynamics 365 Commerce hogyan lehet beállítani és használni a pénztári alkalmazás kiterjesztett bejelentkezési képességét.

A Cloud POS (CPOS) és a Modern POS (MPOS) egy kiterjesztett bejelentkezési funkciót biztosít, amely lehetővé teszi a kiskereskedelmi üzlet dolgozóinak, hogy egy vonalkód beolvasásával vagy egy kártya mágnescsíkolvasóval történő leolvasásával jelentkezzenek be a POS-alkalmazásba.

## <a name="set-up-extended-logon"></a>Kiterjesztett bejelentkezés beállítása

A következő lépések szerint állíthatja be a kiskereskedelmi üzlet POS-pénztárgépeibe való kiterjesztett bejelentkezést.

1. A Commerce Headquarters alkalmazás a **Retail and Commerce \> Channel setup \> POS beállítási \> POS-profilok funkcióprofiljainál \> használható**. 
2. A bal oldali navigációs ablakban válassza ki a kiskereskedelmi üzlethez társított funkcióprofilt.
3. A Funkciók **gyorséta a További** **·** **bejelentkezési** hitelesítési beállításoknál állítsa a következő Igen vagy Nem **gombra:**

    - **Személyzeti vonalkódos bejelentkezés** – **Akkor** állítsa Igen beállításra ezt a lehetőséget, ha azt szeretné, hogy a dolgozók vonalkód beolvasással jelentkezzenek be a POS-be. 
    - **A személyzeti vonalkódos** bejelentkezéshez jelszó szükséges – **Akkor** állítsa Igen beállításra ezt a beállítást, ha azt szeretné, hogy a dolgozók egy jelszót adjanak meg, amikor vonalkód beolvasásával jelentkeznek be a POS-be.
    - **Munkatársak kártyás bejelentkezése** – Akkor állítsa **Igen** beállításra ezt a lehetőséget, ha azt szeretné, hogy a dolgozók kártya letöltésével jelentkezzenek be a POS-be.
    - **A személyzeti kártyás** bejelentkezéshez jelszó szükséges – **Akkor** állítsa Igen beállításra ezt a lehetőséget, ha azt szeretné, hogy a dolgozók jelszót adjanak meg, amikor kártya le.

A vonalkód vagy kártya olyan hitelesítő adatokhoz van társítva, amelyek hozzárendelhetőek egy dolgozóhoz. A hitelesítő adatoknak legalább hat karakterből kell állni. Az első öt karaktert tartalmazó karakterláncnak egyedinek kell lennie, és a rendszer olyan *hitelesítőadat*-azonosítónak számít, amely a dolgozók ki keresse őket. A fennmaradó karaktereket a rendszer a biztonság ellenőrzéséhez használja. Van például két kártya, amelyek egyike a 12345DGYDEYTDW hitelesítő adatokkal rendelkezik, és amelyek egyike a 12345EWBDAJH hitelesítő adatokkal rendelkezik. Mivel ennek a két kártyanek ugyanaz a hitelesítőadat-azonosítója (12345, nem lehet mindkettőt sikeresen hozzárendelni a dolgozókhoz).

## <a name="assign-extended-logon"></a>Kiterjesztett bejelentkezés hozzárendelése

Alapesetben csak a menedzser tud kiterjesztett bejelentkezést hozzárendelni a dolgozókhoz. Kiterjesztett bejelentkezés hozzárendeléséhez, kattintson a **Kiterjesztett bejelentkezés** opcióra a pénztárban. Ezután keressen rá a dolgozóra úgy, hogy begépeli annak dolgozói azonosítóját a keresőmezőbe. Válassza ki a dolgozót, majd kattintson az **Hozzáadás** gombra. A következő oldalon húzza le vagy olvassa be a kiterjesztett belépést, hogy hozzárendelhesse azt a dolgozóhoz. Ha a lehúzás vagy a beolvasás sikeresen megtörtént, az **OK** gomb elérhetővé válik. Kattintson a **OK** gombra, hogy elmentse az adott dolgozóhoz kapcsolódó kiterjesztett bejelentkezést.

## <a name="delete-extended-logon"></a>Kiterjesztett bejelentkezés törlése

A dolgozó kiterjesztett bejelentkezésének törléséhez keresse meg a dolgozót a **Kiterjesztett bejelentkezés** művelet használatával. Válassza ki a dolgozót, majd kattintson az **Törlés** gombra. Minden (az adott dolgozóhoz tartozó) kiterjesztett bejelentkezési hitelesítő adat törlődik.

## <a name="use-extended-logon"></a>Kiterjesztett bejelentkezés használata

Ha be van állítva a kiterjesztett bejelentkezés, és a dolgozóhoz vonalkód vagy mágnescsík van hozzárendelve, akkor a dolgozónak egyszerűen le kell húzza vagy be kell olvasnia a kártyáját, miközben a POS bejelentkezési lapja megjelenik. Ha a bejelentkezés folytatása előtt jelszó is szükséges, a dolgozónak meg kell adnia a jelszavát.

## <a name="extend-extended-logon"></a>Kiterjesztett bejelentkezés kiterjesztése

A kiterjesztett bejelentkezési képesség azonnali megvalósítása megköveteli, hogy a hitelesítő adatok minimális hossza hat karakter legyen, és az első öt karakter (a hitelesítő azonosító) egyedi legyen. Eredetileg olyan mintaként készült, amelyet a fejlesztők testreszabhatnak egy adott megvalósítás követelményeinek megfelelően. (Például testreszabható, hogy több karaktert támogat, vagy különböző biztonsági ellenőrzési szabályokat használjon.) A kiterjesztett bejelentkezéshez [használható bővítmények felépítéséről az MPOS és a Felhő POS](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/) kiterjesztett bejelentkezési funkcióinak bővítése nyújt tájékoztatást.

A bejelentkezési szolgáltatás kiterjeszthető további kiterjesztett bejelentkezési eszközök, például a tenyérolvasók támogatására. A további tudnivalókat lásd [a POS extensibility dokumentációjában](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
