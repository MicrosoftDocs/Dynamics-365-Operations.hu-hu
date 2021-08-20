---
title: Új Elektronikus számlázási funkció létrehozása
description: Ez a témakör ismerteti, hogyan lehet új Elektronikus számlázási funkciót létrehozni, ha nincs konfigurálható gyári funkció az adott ország vagy régió számára.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744935"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Új Elektronikus számlázási funkció létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan lehet új Elektronikus számlázási funkciót létrehozni, ha nincs konfigurálható gyári funkció az adott ország vagy régió számára.

Új Elektronikus számlázási funkció létrehozásához végezze el a következő feladatokat:

1. Hozzon létre új fájlformátum-konfigurációt a megadott számlamodell-konfiguráció használatával, és használja ki a létrehozni kívánt funkció meglévő számlaleképezésének előnyeit.
2. Adja hozzá a fájlformátum-konfigurációkat az Elektronikus számlázás funkció konfigurációihoz.
3. Hozza létre az Elektronikus számlázás funkció beállítását.
4. Fejezze be az új Elektronikus számlázás funkciót, és tegye közzé szervezete Globális adattárában.
5. Telepítse az új Elektronikus számlázás szolgáltatást a Szolgáltatási környezetbe.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>A meglévő számlamodellből származtatott új fájlformátum-konfigurációk létrehozása

Ebben az eljárásban hozza létre a létrehozni kívánt új Elektronikus számlázási funkcióhoz szükséges fájlformátum-konfigurációkat. Létrehozhatja az elektronikus számla fájlformátumának konfigurációját és az új Elektronikus számlázási funkció által esetleg megkövetelt egyéb fájlformátum-konfigurációkat is.

Mielőtt elkezdené ezt az eljárást, jelentkezzen be a Regulatory Configuration Service (RCS) fiókba.

1. A Microsoft Dynamics 365 Finance-ben, az **Elektronikus jelentéskészítés** munkaterületen válassza a **Tárházak** lehetőséget a **Microsoft** konfigurációs szolgáltatóhoz.
2. Válassza a **Globális** lehetőséget, a **Megnyitás** lehetőséget, majd a bal oldali ablaktáblán válassza ki a **Számlamodell** konfigurációját.

    > [!IMPORTANT]
    > Brazília esetében ehelyett a **Pénzügyi dokumentumok** modellkonfigurációját válassza ki.

3. A **Konfigurációk** lapon válassza az **Importálás** lehetőséget.
4. Zárja be a lapot.
5. Zárja be a lapot.
6. Válassza ki a **Jelentéskészítési konfigurációk** csempét, majd az importált számlamodellt.
7. Válassza a **Konfiguráció létrehozása**, majd a **Számla környezetmodelljén alapuló formátum** lehetőséget.
8. Írja be a formátumkonfiguráció nevét és a leírását.
9. A **Formátumtípus** mezőben válassza ki a fájlkiterjesztés típusát.
10. Válassza a **Konfiguráció létrehozása** lehetőséget, majd válassza ki a létrehozott formátumkonfigurációt.
11. Válassza a **Tervezőt**, és a Formátumtervező eszközzel konfigurálja a fájlelrendezést úgy, hogy az megfeleljen a fájlformátumra vonatkozó előírásoknak.
12. Zárja be a lapot.
13. A **Verziók** lapon válassza az **Állapot módosítása** \> **Befejezés** lehetőséget.
14. Válassza az **Állapot módosítása** \> **Megosztás** lehetőséget a formátumkonfiguráció Globális tárházban való közzétételéhez.

Az új fájlformátum-konfigurációt meg kell osztani a Microsoft tartományával, mielőtt a konfigurációt az Elektronikus számlázási szolgáltatás felhasználhatja.

1. Válassza ki azt a formátumkonfigurációt, amelyen dolgozik. A konfiguráció állapotának **Megosztott** értékűnek kell lennie.
2. A **Verziók** lapon válassza a **Speciális megosztás** \> **Globális tárház** lehetőséget.
3. A **Megosztva a következővel** lapon válassza a **Szervezet** lehetőséget.
4. A **Paraméterek** mezőbe írja be a **Microsoft.com** címet, hogy a formátumkonfigurációt megossza a Microsoft tartományával.
5. Válassza ki az **OK** lehetőséget.

## <a name="create-the-new-electronic-invoicing-feature"></a>Az új Elektronikus számlázási funkció létrehozása

1. Az RCS-ben, a **Globalizációs funkciók** munkaterületen, a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
2. Válassza a **Hozzáadás**, majd az **Új funkció** lehetőséget.
3. Adjon nevet és leírást az Elektronikus számlázás funkcióhoz.
4. Válassza a **Létrehozás lehetőséget**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Elektronikus számlázás funkció konfigurációinak hozzáadása

1. Válassza ki azt az Elektronikus számlázás funkciót, amelyen dolgozik.
2. A **Konfigurációk** lapon válassza a **Hozzáadás** lehetőséget.
3. A **Konfigurációk** rácsban keresse meg és válassza ki azokat a fájlformátum-konfigurációkat, amelyeket az Elektronikus számlázás funkció az elektronikus számlafájl létrehozásához igényel.
4. Válassza ki az **OK** lehetőséget.

## <a name="add-electronic-invoicing-feature-setups"></a>Elektronikus számlázási funkció beállításainak hozzáadása

1. A **Beállítások** lapon válassza a **Hozzáadás**, majd az **Egyéni beállítás** lehetőséget.
2. Adja meg a funkció beállításának nevét és leírását.
3. A **Beállítás típusa** mezőben válassza a **Feldolgozási folyamat** lehetőséget.
4. Válassza a **Létrehozása** lehetőséget.
5. Válassza ki a beállítást, amelyen dolgozik, majd válassza a **Szerkesztés** lehetőséget.
6. A **Feldolgozási folyamat** lapon válassza az **Új** lehetőséget egy folyamatművelet hozzáadásához. A folyamatokkal kapcsolatos további információkért lásd: [Műveletek](e-invoicing-configuration-rcs.md#actions).
7. Válassza az **Alkalmazhatósági szabályok** lapon az **Új** lehetőséget alkalmazhatósági szabályzáradékok hozzáadásához. A további tudnivalókat az alkalmazhatósági szabályokról lásd: [Alkalmazhatósági szabályok](e-invoicing-configuration-rcs.md#applicability-rules).
8. A **Változók** lapon válassza az **Új** lehetőséget a változók hozzáadásához szükség szerint.
9. Válassza a **Mentés** lehetőséget, majd válassza az **Ellenőrzés** lehetőséget a konfiguráció konzisztenciájának ellenőrzéséhez.
10. Zárja be a lapot.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Az elektronikus számlázási funkció telepítése a szolgáltatási környezetbe

A feladat elvégzésével kapcsolatos információkat lásd: [Az elektronikus számlázási funkció telepítése a szolgáltatási környezetbe](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Az Elektronikus számlázás funkció telepítése egy csatlakoztatott alkalmazásba

A feladat elvégzésével kapcsolatos információkat lásd: [Az alkalmazás beállításának konfigurálása](e-invoicing-get-started.md#configure-the-application-setup) és [Az elektronikus számlázás funkció telepítése a csatlakoztatott alkalmazásba](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
