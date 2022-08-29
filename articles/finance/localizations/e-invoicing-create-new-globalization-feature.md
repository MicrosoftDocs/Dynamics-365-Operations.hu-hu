---
title: Globalizációs funkció létrehozása
description: Ez a témakör bemutatja a globalizációs funkciók létrehozásához szükséges funkciókat.
author: gionoder
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5432de8f8a70a4e6a0facd546083b37fd8690556
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283175"
---
# <a name="create-a-globalization-feature"></a>Globalizációs funkció létrehozása

[!include [banner](../includes/banner.md)]

Létre lehet hozni egy elektronikus számlázási funkciót az elsőből, vagy egy meglévő szolgáltatásra lehet alapozni. Amikor egy funkciót az első lépésből hoz létre, manuálisan kell hozzáadnia az Elektronikus jelentés (ER) konfigurációkat és más összetevőket, például a funkcióbeállítás és az alkalmazásbeállítás részletes adatait. Ha egy meglévő szolgáltatáson alapuló szolgáltatást hoz létre, akkor az új funkció örökli az alap funkció összes konfigurációját és paramétereit. Áttekintheti, hogy mi van átmásolva az alap szolgáltatásból az új funkcióba.

## <a name="create-a-feature-from-scratch"></a>Funkció létrehozása az akkretból

Ez a szakasz bemutatja, hogyan lehet elektronikus számlázási funkciót létrehozni, ha a globális tárházban nem érhető el globalizációs funkció az üzleti esetekhez.

Az alábbi lépésekkel lehet elektronikus számlázási funkciókat létrehozni.

1. Jelentkezzen be a saját RCS-fiókjába.
2. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. Válassza **a** Hozzáadás lehetőséget, majd a legördülő párbeszédpanelen válassza az Új **funkció** lehetőséget.
4. Adja meg az elektronikus számlázási funkció nevét és leírását.
5. Válassza a **Létrehozás lehetőséget**. Az új funkció első verziója a **lap jobb oldalán jelenik meg, állapota Vázlat**.

    Ezután er-konfigurációkat és funkcióbeállításokat kell hozzáadnia. Mielőtt új vagy meglévő ER-formátumkonfigurációkat ad hozzá, győződjön meg róla, hogy léteznek a helyi RCS-tárházban.

6. Válassza ki azt az elektronikus számlázási funkciót, amelyen dolgozik.
7. A **Konfigurációk** lapon válassza a **Hozzáadás** lehetőséget.
8. A Konfigurációk **rácsban** tallózással keresse meg és válassza ki a feldolgozási folyamathoz szükséges formátumkonfigurációkat (például elektronikus számlafájlok generálása vagy a külső webszolgáltatásoktól származó válaszok feldolgozása).
9. Válassza ki az **OK** lehetőséget. Most használhatja a konfigurációkat a feldolgozási folyamat műveletei során. További tájékoztatás a konfigurációkban [való munkáról.](e-invoicing-work-configurations.md)
10. Ha elektronikus számlázási funkcióbeállítást szeretne hozzáadni, **·** **hozza létre az Új funkciólap Beállítások lapján.** A további tudnivalókat lásd [a Funkcióbeállítások használata funkcióval kapcsolatban](e-invoicing-feature-setup.md).
11. A beállítás befejezése és az elektronikus számlázás szolgáltatás telepítése a szolgáltatási környezetbe. A további tudnivalókat lásd [a Globalizációs funkció befejezése, közzététele és telepítése során](e-invoicing-complete-publish-deploy-globalization-feature.md).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>A meglévő számlamodellből származtatott fájlformátum-konfigurációk létrehozása

Ezt a szakaszt kihagyhatja, ha nem kell ER-konfigurációkat létrehoznia, de a meglévő verziókat felhasználhatja alapként.

Ezzel az eljárással lehet létrehozni a létrehozni kívánt új elektronikus számlázási funkcióhoz szükséges fájlformátum-konfigurációkat. Hozza létre az elektronikus számla fájlformátum-konfigurációját és az új elektronikus számlázási funkció által megkövetelt egyéb fájlformátum-konfigurációkat.

1. Jelentkezzen be a RCS-fiókba.
2. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. Válassza ki **a számlamodellt**, vagy brazil helyzet esetén a pénzügyi **modellt**.
4. Válassza **a Konfiguráció létrehozása** lehetőséget, majd a **legördülő párbeszédpanelen válassza a Számla adatmodell alapján beállítást a Formátum** mezőben.
5. Írja be a formátumkonfiguráció nevét és a leírását.
6. A **Formátumtípus** mezőben válassza ki a fájlkiterjesztés típusát.
7. Az Adatmodell **definíciós mezőben** válassza ki azt a gyökérstruktúrát, amelybe leképezi a formátumot. Például a **InvoiceCustomer** a vevői számlaformátumokhoz használható.
8. Válassza a **Konfiguráció létrehozása** lehetőséget.
9. Az új formátumkonfiguráció kiválasztása.
10. Válassza a **Tervezőt**, és a Formátumtervező eszközzel konfigurálja a fájlelrendezést úgy, hogy az megfeleljen a fájlformátumra vonatkozó előírásoknak.
11. Zárja be a lapot.
12. A **Verziók** lapon válassza az **Állapot módosítása** \> **Befejezés** lehetőséget.
13. Válassza az **Állapot módosítása** \> **Megosztás** lehetőséget a formátumkonfiguráció Globális tárházban való közzétételéhez.

Az új fájlformátum-konfigurációkat meg kell osztani a Microsoft tartományával, mielőtt az elektronikus számlázási szolgáltatás felhasználja őket.

1. Válassza ki azt a formátumkonfigurációt, amelyen dolgozik. A konfiguráció állapotának **Megosztott** értékűnek kell lennie.
2. A **Verziók** lapon válassza a **Speciális megosztás** \> **Globális tárház** lehetőséget.
3. A **Megosztva a következővel** lapon válassza a **Szervezet** lehetőséget.
4. A Paraméterek **mezőben** adja **microsoft**.com, ha a formátumkonfigurációt meg kell osztania a Microsoft tartományával.
5. Válassza ki az **OK** lehetőséget.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Meglévő szolgáltatáson alapuló funkció létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. A Konfigurációszolgáltató **mezőben** győződjön meg arról, hogy az aktív konfigurációszolgáltató ki van választva. Ily módon az új elektronikus számlázás funkció létrehozás után megjelenik a listában. Ha nincs kiválasztva az aktív konfigurációs szolgáltató, akkor a rendszer kiszűri az új funkciót a listából.
4. Válassza a **Hozzáadás** lehetőséget, majd a legördülő párbeszédpanelen válassza ki a **Meglévő verzió alapján** beállítást.
5. Írja be a funkció nevét és a leírását.
6. Az Alap **funkció mezőben** válassza ki a funkció alapverzióját.
7. Válassza a **Létrehozás lehetőséget**. A funkció létrejön és Vázlat **állapotú**.
8. Tekintse át a szolgáltatások összetevőit annak a megállapításához, hogy szükségesek-e frissítések:

    - Ellenőrizze a konfigurációkat, ha testre kell szabni az ER-formátumokat és a formátum-hozzárendeléseket a funkcióverzió formátum-hozzárendelései alapján.
    - Ellenőrizze a beállítást, **ha** testre kell szabni a funkcióverzió Műveletek, **·** **Alkalmazhatósági** szabályok vagy Változók lapját.

9. A beállítás befejezése és az elektronikus számlázás szolgáltatás telepítése a szolgáltatási környezetbe. A további tudnivalókat lásd [a Globalizációs funkció befejezése, közzététele és telepítése során](e-invoicing-complete-publish-deploy-globalization-feature.md).
