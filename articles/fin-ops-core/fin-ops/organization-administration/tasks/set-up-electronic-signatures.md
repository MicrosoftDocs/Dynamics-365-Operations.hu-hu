---
title: Az elektronikus aláírások beállítása
description: Ezzel a folyamattal beállíthatja az Elektronikus aláírási eljárásokat.
author: maertenm
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d78ecd0606f3b1d5d7b5f3cd470beecfcdd5077
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747345"
---
# <a name="set-up-electronic-signatures"></a>Az elektronikus aláírások beállítása

[!include [banner](../../includes/banner.md)]

Ezzel a folyamattal beállíthatja az Elektronikus aláírási eljárásokat. Az elektronikus aláírás igazolja annak a személynek a személyazonosságát, aki egy számítási folyamat elindítása vagy jóváhagyása előtt áll. Ez az eljárás a DAT bemutatócéggel jött létre.


## <a name="enable-the-electronic-signature-configuration-key"></a>Elektronikus aláírás konfigurációs kulcs engedélyezése
1. Ugorjon a Rendszerfelügyelet > Beállítás > Licenckonfiguráció elemre.
2. A fában bontsa ki az „Adminisztráció” elemet.
    * Ellenőrizze, hogy be legyen jelölve az Elektronikus aláírás jelölőnégyzet.  
    * Ha az Elektronikus aláírás jelölőnégyzet nincs bejelölve, engedélyeznie kell a karbantartási módot. A karbantartási módot úgy engedélyezheti ebben a környezetben, hogy az LCS rendszerben futtat egy karbantartási feladatot, vagy helyben használja a Deployment.Setup eszközt.  
3. Zárja be a lapot.

## <a name="set-up-electronic-signature-parameters"></a>Az elektronikus aláírás paramétereinek beállítása
1. Ugorjon a Szervezeti felügyelet > Beállítás > Elektronikus aláírás > Elektronikus aláírás paraméterei pontra.
2. Kattintson a Szerkesztés lehetőségre.
3. Írjon be egy értéket az Értesítés mezőbe.
    * Adja meg azt az értesítést, amelyet akkor kapnak az aláírók, amikor szükség van az aláírásukra. Itt bármilyen szöveg megadható. Ez a szöveg általában azt közli a felhasználóval, hogy mit jelent a dokumentumok elektronikus aláírása.  
    * Ha szeretne megadni egy Értesítési szöveget további nyelveken is, kattintson a Fordítások gombra.  
4. Kattintson a Mentés gombra.
5. Zárja be a lapot.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Okkódok beállítása az elektronikus aláírásokhoz
1. Ugorjon a Szervezeti felügyelet > Beállítás > Elektronikus aláírás > Elektronikus aláírás okkódjai pontra.
2. Kattintson az Új lehetőségre.
    * Az okkódokat az elektronikus aláírás használatba vétele előtt be kell állítani. A dokumentumok aláírásához szükség van egy érvényes okkódra.     Az aláíró egy okkód kiválasztásával jelzi az elektronikus aláírás célját. Például egy okkóddal jelezhető a jogi jóváhagyás.  
3. Az Okkód mezőbe írjon be egy értéket.
4. A Leírás mezőben adjon meg egy értéket.
    * Ha szükséges, adjon meg további okkódokat.  
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.

## <a name="require-electronic-signatures-for-existing-processes"></a>Elektronikus aláírás kötelezővé tétele meglévő folyamatokban
1. Ugrojon a Szervezeti felügyelet > Beállítás > Elektronikus aláírás > Elektronikus aláírás követelményei pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válasszon ki egy elektronikus aláírást igénylő folyamatot.  
3. Jelölje be az Aláírás kötelező jelölőnégyzetet, vagy törölje belőle a jelet.
    * Ismételje meg ezeket a lépéseket minden olyan folyamatnál, amely megköveteli az elektronikus aláírásokat.  
4. Kattintson a Mentés gombra.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Elektronikus aláírásokra vonatkozó egyedi követelmény létrehozása
1. Kattintson az Új lehetőségre.
2. Jelölje be az Aláírás kötelező jelölőnégyzetet, vagy törölje belőle a jelet.
3. Adja meg az elektronikus aláírást előíró eljárást a Név mezőben.
4. A Táblázat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában keresse meg és válassza ki azt a táblázatot, amely az aláírandó adatokat tárolja.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A Mező neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában keresse meg és válassza ki a megfigyelni kívánt táblázat mezőjét.
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Határozza meg, hogy mikor kötelező az aláírás.     A Mindig lehetőség kiválasztása esetén a mezőben szereplő adatok minden módosításakor kötelező az aláírás.     Válassza a Csak lehetőséget, ha az aláírásra csak bizonyos feltételek esetén van szükség. A Csak választása esetén is be kell jelölnie a következő lehetőségek közül egyet: Rekord beillesztésekor, Rekord frissítésekor vagy Rekord törlésekor.  
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]