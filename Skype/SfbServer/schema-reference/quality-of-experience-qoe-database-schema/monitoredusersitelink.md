---
title: MonitoredUserSiteLink 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807796"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 테이블
 
MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |기본, 외래  <br/> |[Usersite 테이블](usersite.md)에서 참조 합니다.  <br/> |
|**UserSite2Key** <br/> |int  <br/> |기본, 외래  <br/> |[Usersite 테이블](usersite.md)의 참조입니다.  <br/> |
   

