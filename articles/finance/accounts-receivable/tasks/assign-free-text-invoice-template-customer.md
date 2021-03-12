---
title: Szabadszöveges számlasablon hozzárendelése egy ügyfélhez
description: A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb5dd96cb71dcee6db97ad1074e7e75565ac4101
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969628"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Szabadszöveges számlasablon hozzárendelése egy ügyfélhez

[!include [banner](../../includes/banner.md)]

A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni. Ez a feladat az USMF bemutató vállalatot veszi alapul, és az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.

1. A **Navigációs ablaktáblán** ugorjon a **Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A **Művelet panelen** kattintson a **Számla** elemre.
4. Kattintson az **Ismétlődő számlák** lehetőségre. Ezen a lapon szabadszöveges számlasablonokat rendelhet hozzá a vevőkhöz, és megadhatja, hogy milyen gyakran történjen számlázás a vevő részére.  
5. Az **Új** gombra kattintva új sablont rendel a vevőhöz.
6. A **Sablon** mezőben válassza ki a szabadszöveges számlasablont, amelyet hozzá kíván rendelni a vevőhöz.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A **Számlázási kezdési dátum** mezőben adja meg azt a dátumot, amikor az első számla létrejön.
10. Az **Ismétlődés vége** szakaszban írjon be egy ismétlődő záró dátumot.  
    * Válassza ki a következők valamelyikét: Nincs záró dátum – A számlázás folyamatosan történik, amíg a sablont el nem távolítja a vevői fiókból.
    * Számlázás záró dátuma – Válassza ezt az opciót, ha szeretné megadni, mi az a legutolsó dátum, amikor még generálható számla.  
11. A **Maximális halmozott összeg** mezőbe írja be azt a maximális halmozott összeget, amely után a számla generálása leáll. Adja meg a maximális halmozott összeget, amely a kiválasztott sablon használatával elérhető. Ha például 1000,00-t ad meg és havonta 100,00-ról állít ki számlát, a tizedik számla után nem jön létre több számla.  
12. Az **Ismétlődő számlák létrehozása a következő alapértelmezett értékeivel:** szakaszban válassza a szabadszöveges számlasablon vagy a vevői fiók lehetőséget. Válassza ki, hogy a rendszer a szabadszöveges számlasablon vagy a vevői számla alapján határozza meg a nyelvet, a feladási profilt, az áfacsoportot, a cikkáfacsoportot, a listakód, a szállítási országot/területet, a pénznemet, a fizetési feltételeket, a fizetési módot, a fizetési specifikációt, a részletfizetést, a készpénzfizetési engedményt, a pénzügyi dimenziókat, illetve a zsíró alapú pénzátutalási bizonylatot a számlák létrehozásakor.  
13. Az **Ismétlődési szabály** mezőben válassza ki a kívánt ismétlődési mintát.
    + Napi – Válassza ezt az opciót, majd adja meg a napok számát a / mezőben. Ha például a 15 értéket adja meg, akkor a rendszer 15 naponta generál számlát ehhez a vevőhöz.
    + Hetente – Válassza a Hetente opciót, majd adja meg a hetek számát a / mezőben. Ha például a 2 értéket adja meg, akkor a rendszer kéthetente generál számlát ehhez a vevőhöz.
    + Havonta – Válassza a Havonta opciót, majd adja meg a hónapok számát a / mezőben. Ha például a 6 értéket adja meg, akkor a rendszer félévente generál számlát ehhez a vevőhöz.
    + Évente – Válassza az Évente opciót, majd adja meg az évek számát a / mezőben. Ha például a 2 értéket adja meg, akkor a rendszer kétévente generál számlát ehhez a vevőhöz.  
14. A **/** mezőben adjon meg egy számot.

