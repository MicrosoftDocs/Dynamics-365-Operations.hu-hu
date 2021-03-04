---
title: A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása
description: Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7961cfb4ad0e20c49d327d83f56c08811598ac1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429524"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása

[!include [banner](../../includes/banner.md)]

Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében. Az első 4 rögzítés beállítja azt az adatot, ami szükséges az eljárás végrehajtásához. Ez az eljárás az USMF bemutatócéget használja. Ezt a feladatot általában a termék tervező kezeli.


## <a name="select-the-product"></a>Válassza ki a terméket
1. Kattintson a Kiadott termék karbantartása lehetőségre.
2. Kattintson a Kibocsátott termék lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
    * Keresse meg azt a dimenzión alapuló konfiguráció technológiájával kiadott alapterméket, amelyet az itt látható sorrendben hozott létre az első feladat útmutatójában.  
4. A Művelet panelen kattintson a Mérnök elemre.
5. Kattintson az Anyagjegyzék verziókra.

## <a name="create-new-bom-and-bom-version"></a>Hozzon létre új anyagjegyzéket és anyagjegyzék-verziót
1. Kattintson az Új lehetőségre.
2. Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.
3. Írjon be egy értéket a Név mezőbe.
    * Hely beállítása  
    * Ebben az eljárásban nem állítunk be egy adott helyet az anyagjegyzékre vonatkozóan.  
4. Kattintson az OK gombra.
5. Kattintson az Új lehetőségre.
    * Ebben az eljárásban négy sort adunk az Anyagjegyzékhez. Két sor a kábel beállításokat és két sor pedig kabinetfájl beállításokat jelöli.  
6. A listában jelölje meg a kiválasztott sort.
7. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a A0001 -es cikkszámot, HDMI 6'-os kábelt.  
8. A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a 4-es útmutatóban létrehozott Kábel konfigurációs csoportot ebben a sorozatban.  
9. Kattintson az Új lehetőségre.
    * Válassza ki a A0002-es cikkszámot, HDMI 12'-os kábelt.  
10. A listában jelölje meg a kiválasztott sort.
11. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
12. A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki újból a Kábel konfigurációs csoportot.  
13. Kattintson az Új lehetőségre.
14. A listában jelölje meg a kiválasztott sort.
15. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a D0002 cikkszámú kabinetfájlt.  
16. A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a Kabinetfájl konfigurációs csoportot ezen anyagjegyzék sorára vonatkozóan.  
17. Kattintson az Új lehetőségre.
18. A listában jelölje meg a kiválasztott sort.
19. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki az M0007 cikkszámú StandardCabinet elemet az utolsó Anyagjegyzék soraként.  
20. A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a Kabinetfájl konfigurációs csoportot az utolsó anyagjegyzék sorára vonatkozóan.  

## <a name="approve-and-activate"></a>Jóváhagyás és aktiválás
1. Zárja be a lapot.
2. Kattintson a Jóváhagyás lehetőségre.
3. A Jóváhagyó mezőben adjon meg vagy válasszon ki egy értéket.
4. A „Szeretné az anyagjegyzéket is jóváhagyni?” kérdésre válaszolva válassza ki az Igen lehetőséget.
5. Kattintson az OK gombra.
6. Kattintson az Aktiválás gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]