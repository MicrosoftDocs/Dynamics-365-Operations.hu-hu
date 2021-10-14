---
title: A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása
description: Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f86625821f8a01a6d4949f9dca538a279f52ce9c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565588"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása

[!include [banner](../../includes/banner.md)]

Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében. Az első 4 rögzítés beállítja azt az adatot, ami szükséges az eljárás végrehajtásához. Ez az eljárás az USMF bemutatócéget használja. Ezt a feladatot általában a termék tervező kezeli.

## <a name="select-the-product"></a>Válassza ki a terméket

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A listában jelölje meg a kiválasztott sort.
    * Keresse meg azt a dimenzión alapuló konfiguráció technológiájával kiadott alapterméket, amelyet az itt látható sorrendben hozott létre az első feladat útmutatójában.  
1. A Műveleti ablaktáblán kattintson a **Mérnök** elemre.
1. **DBJ-verziók** kiválasztása.

## <a name="create-new-bom-and-bom-version"></a>Hozzon létre új anyagjegyzéket és anyagjegyzék-verziót

1. Válassza az **Új** lehetőséget.
1. Válassza ki a **DBJ és DBJ-verzió** elemet.
1. Írjon be egy értéket a **Név** mezőbe.
    * Hely beállítása  
    * Ebben az eljárásban nem állítunk be egy adott helyet az anyagjegyzékre vonatkozóan.  
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Új** lehetőséget.
    * Ebben az eljárásban négy sort adunk az Anyagjegyzékhez. Két sor a kábel beállításokat és két sor pedig kabinetfájl beállításokat jelöli.  
1. A listában jelölje meg a kiválasztott sort.
1. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a A0001 -es cikkszámot, HDMI 6'-os kábelt.  
1. A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a 4-es útmutatóban létrehozott Kábel konfigurációs csoportot ebben a sorozatban.  
1. Válassza az **Új** lehetőséget.
    * Válassza ki a A0002-es cikkszámot, HDMI 12'-os kábelt.  
1. A listában jelölje meg a kiválasztott sort.
1. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
1. A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki újból a Kábel konfigurációs csoportot.  
1. Válassza az **Új** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a D0002 cikkszámú kabinetfájlt.  
1. A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a kabinetfájl konfigurációs csoportot ezen anyagjegyzék sorára vonatkozóan.  
1. Válassza az **Új** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki az M0007 cikkszámú StandardCabinet elemet az utolsó Anyagjegyzék soraként.  
1. A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a Kabinetfájl konfigurációs csoportot az utolsó anyagjegyzék sorára vonatkozóan.  

## <a name="approve-and-activate"></a>Jóváhagyás és aktiválás

1. Zárja be a lapot.
1. Válassza a **Jóváhagyás** lehetőséget.
1. A **Jóváhagyó** mezőben adjon meg vagy válasszon ki egy értéket.
1. A **Szeretné az anyagjegyzéket is jóváhagyni?** kérdésre válaszolva válassza ki az *Igen* lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Aktiválás** lehetõséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]