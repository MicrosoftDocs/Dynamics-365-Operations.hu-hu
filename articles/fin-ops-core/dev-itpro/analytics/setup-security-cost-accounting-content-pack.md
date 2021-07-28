---
title: Biztonság beállítása a Power BI-tartalmú költségkönyvelés elemzéséhez
description: Ez a témakör azt mutatja be, hogy miként alkalmazhatja a hozzáférésszintű biztonságot a Költségkönyvelésnél a sorszintű biztonságnál, a Microsoft Power BI szolgáltatásban.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2e51c6914aab7261862a7ce180376b67d01711e3
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359459"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Biztonság beállítása a költségkönyvelés elemzéséhez – Power BI-tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogy miként alkalmazhatja a hozzáférésszintű biztonságot a Költségkönyvelésnél a sorszintű biztonságnál, a Microsoft Power BI szolgáltatásban. Ez a funkció segít garantálni, hogy a felhasználók csak azokat a Power BI adatokat láthassák, amelyekhez hozzáférést kaptak.

## <a name="overview"></a>Áttekintés

A **Költségkönyvelés elemzése** Microsoft Power BI tartalom a Power BI sorszintű biztonsága révén korlátozza a felhasználói hozzáféréseket. A biztonság azon a hozzáférésszintű szervezeti hierarchián alapszik, amelynek beállítása a Költségkönyvelés paramétereinél történik. Ha további információt szeretne a **Költségkönyvelési elemzés** Power BI tartalomról, lásd: [Költségkönyvelési elemzés Power BI-tartalom](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Beállítás
A hozzáférésszintű biztonság Power BI szolgáltatásban való alkalmazásához Power BI tartalom tulajdonosának követnie kell az alábbi lépéseket.

> [!NOTE]
> A **Költségkönyvelési elemzés** Power BI tartalom közzétevője automatikusan tulajdonossá válik. Csak a tulajdonosok állíthatják be a biztonságot a Power BI szolgáltatásban. Továbbá addig, amíg egy tulajdonos további felhasználókat nem vesz fel a PowerBI.com webhelyen, addig a tulajdonoson kívül senki sem láthat adatokat a **Költségkönyvelési elemzés** Power BI tartalomnál.

1. Tegye közzé a definíciós fájlt a Power BI szolgáltatásban.
2. Jelentkezzen be a PowerBI.com webhelyre.
3. Keresse ki a **Költségkönyvelési elemzés** adatkészletét a Power BI-tartalomhoz.
4. Nyissa meg a Biztonság lapot.

    ![A Biztonság lap megnyitása.](./media/CA-picture-1.png)

5. A **Költségobjektum-ellenőr** szerepkör már létre van hozva. Vegyen fel további olyan tagokat, akik részesei a Költségkönyvelés hozzáférésszintű szervezeti hierarchiájának.

    ![Tagok hozzáadása.](./media/CA-picture-2.png)

A **Költségobjektum-ellenőr** szerepkörhöz hozzárendelt felhasználók csak a számukra engedélyezett adatokat láthatják, amelyeket engedélyeztek a Költségkönyvelés hozzáférésszintű szervezeti hierarchiában.

> [!NOTE]
> Sorszintű biztonság vonatkozik a csempékre és jelentésekre is, amelyek a Power BI-ből vannak beágyazva.

## <a name="updating-security"></a>Biztonság frissítése
Ha frissítéseket véget a hozzáférés szintű biztonságnál a Költségnyilvántartásnál, és azt szeretné, hogy a Power BI is tükrözze a módosításokat, akkor frissítenie kell az entitástárat a **Költségkönyvelési elemzés** Power BI tartalomnál. Miután befejezte az entitástár frissítését, frissítenie kell a műterméket a PowerBI.com webhelyen. Ha további információt szeretne az entitástár frissítéséről, lásd: [Power BI-integráció az entitástárral](power-bi-integration-entity-store.md#update-entity-store). A **Költségkönyvelési elemzés** Power BI tartalom tulajdonosának entitástár-frissítést kell végeznie, ha új felhasználók hozzáférést kapnak a szervezeti hierarchiához. Továbbá a tulajdonosnak hozzá kell adnia az új felhasználókat a **Költségobjektum-ellenőr** szerepkörhöz a PowerBI.com webhelyen annak érdekében, hogy rétegszintű biztonságot alkalmazzanak rájuk.

## <a name="disabling-security"></a>A biztonság letiltása
Feltételezzük, hogy szervezete korlátozni szeretné az adatokhoz való hozzáférést. Ha valamilyen okból a biztonsági paraméterek le vannak tiltva a Költségkönyvelés futtatásakor, akkor a tulajdonosnak felhasználókat kell hozzáadnia a **Költségkönyvelő munkatárs** szerepkörhöz a Power BI felületén. Ha a biztonságot engedélyezett állapotról letiltott állapotra váltja, akkor érdemes lehet eltávolítania felhasználókat a **Költségobjektum-ellenőr** szerepből. És ez fordítva is igaz, ha újra engedélyezi a biztonságot. A felhasználók mindkét szerepkörhöz is tartozhatnak. A közös hozzáférés a két szerepkör egységét jelenti. A **Költségkönyvelési elemzés** Power BI tartalom esetében a közös hozzáféréssel rendelkező felhasználók adatokhoz való hozzáférése korlátozás nélküli. Ha célja a korlátozott hozzáférés alkalmazása, akkor a felhasználókat csak a **Költségobjektum-ellenőr** szerepkörhöz szabad hozzárendelni. Ezek a sorszintű biztonsági frissítések azonnal hatályba lépnek. Az érintett felhasználóknak frissíteniük kell a böngészőprogramjukat.

## <a name="additional-resources"></a>További erőforrások
Ha további információt szeretne a Power BI sorszintű biztonságáról, lásd: [Biztonság kezelése a modelljén a Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/#manage-security-on-your-model) szolgáltatással.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]