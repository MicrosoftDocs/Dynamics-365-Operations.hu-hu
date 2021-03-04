---
title: Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez
description: Ez a témakör azt ismerteti, hogy miként hozhat léte Excel-munkafüzetet a kiskereskedelmi tranzakciók szerkesztéséhez a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 73a3387d1e7251168002ff683b5b58e0c82a620c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965377"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogy miként hozhat léte Excel-munkafüzetet a kiskereskedelmi tranzakciók szerkesztéséhez a Microsoft Dynamics 365 Commerce szolgáltatásban.

## <a name="overview"></a>Áttekintés

Létezik egy előre meghatározott Excel-sablon, amelyet az ügyfelek a rendszer különböző részeiből érhetnek el, és a kiskereskedelmi tranzakciók szerkesztésére és auditálására használhatnak. Az ügyfelek azonban erre a célra egyéni Excel-munkafüzetet is létrehozhatnak.

## <a name="create-and-configure-an-excel-workbook"></a>Excel-munkafüzet létrehozása és konfigurálása

Ha Excel-munkafüzetet kíván létrehozni és konfigurálni, hogy szerkeszthesse a kiskereskedelmi tranzakciókat, kövesse az alábbi lépéseket.

1. Nyissa meg az Excelt, és hozzon létre egy üres munkafüzetet.
1. A **Beszúrás** lapon válassza a **Saját bővítmények** lehetőséget.
1. A jobb oldali ablakban válassza a **Kiszolgáló adatainak hozzáadása** hivatkozást.
1. Írja be a kiszolgáló URL-címét, majd kattintson az **OK** gombra.
1. Ha „Nem található kisalkalmazás-regisztráció” hibaüzenet jelenik meg, a probléma megoldásához kövesse az alábbi lépéseket:

    1. A Commerce alkalmazásban lépjen a **Rendszerfelügyelet \> Beállítás \> Office alkalmazás paraméterei** lehetőségre.
    1. Az **Alkalmazás paraméterei** gyorslapon válassza az **Alkalmazásparaméterek inicializálása** lehetőséget.
    1. A megerősítést kérő üzenetmezőben válassza az **OK** gombot.
    1. A **Regisztrált kisalkalmazások** gyorslapon válassza a **Kisalkalmazás regisztrációjának inicializálása** lehetőséget.
    1. Szükség szerint ismételje meg az előző három lépést.

1. Válassza ki a **Tervezés**, majd a **Tábla hozzáadása** lehetőséget.
1. A módosítandó adatok alapján jelölje ki azokat az entitásokat, amelyeket szerkesztésre hozzá kell adni az Excel-munkafüzethez. Használja az alábbi táblát hivatkozásként.

    | Tranzakció típusa | Használandó adatentitások |
    |------------------|----------------------|
    | Készpénzzel fizetett, azonnal átvett tranzakciók, online rendelések, aszinkron vevői rendelések, aszinkron vevői ajánlatok | Tranzakció (auditálható), Értékesítési tranzakció (auditálható), Fizetési tranzakciók (auditálható), Adótranzakciók (auditálható), Engedményes tranzakciók (auditálható), Költségtranzakciók (auditálható) |
    | Banki befizetés | Tranzakció (auditálható), Banki fizetőeszközzel történt tranzakciók (auditálható) |
    | Széfes befizetés | Tranzakció (auditálható), Széfes fizetőeszközzel történt tranzakciók (auditálható) |
    | Fizetőeszköz-elszámolás | Tranzakció (auditálható), Fizetőeszköz-elszámolási tranzakciók (auditálható) |
    | Bevétel, Költség | Tranzakció (auditálható), Bevétel/Költségtranzakciók (auditálható), Fizetési tranzakciók (auditálható) |
    | Kezdőösszeg meghatározása, Fizetőeszköz kivétele, Váltópénz betétele, Visszajáró fizetőeszköze, Számlakifizetés, Vevői letét | Tranzakció (auditálható), Fizetési tranzakciók (auditálható) |

    > [!NOTE]
    > Fontos, hogy minden Excel-munkafüzethez csak egy adatentitást adjon hozzá. Ezenkívül a kulcsszimbólummal jelölt összes mezőt hozzá kell adni a megfelelő munkafüzethez.

1. A munkafüzet konfigurálása után alkalmazza a szükséges szűrőket. Ügyeljen arra, hogy ugyanazokat a szűrőket alkalmazza a fájl összes munkalapjára. Ne töltsön be nagyon nagy mennyiségű adatot az Excel-fájlba. Ellenkező esetben a teljesítmény csökkenhet, valamint az Excel és a rendszer lelassulhat. Azt javasoljuk, hogy mindig a „Vállalat” és a „Kimutatásszám” vagy a „Tranzakciószám” kifejezést használja szűrőként a fájlhoz.
1. A szűrők konfigurálása után válassza a **Frissítés** lehetőséget az adatok betöltéséhez.
1. Szerkessze a szükséges adatokat, majd tegye közzé. Ha a **Közzététel** gomb nem érhető el, valószínűleg néhány kulcsmező nem lett hozzáadva az Excel-munkafüzethez.

## <a name="additional-resources"></a>További erőforrások

[Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása](edit-cash-trans.md)

[Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása](edit-order-trans.md)

[Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése](edit-financial-dim.md)

[Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]