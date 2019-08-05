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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196549"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 테이블
 
MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |기본, 외래  <br/> |[Usersite 테이블](usersite.md)에서 참조 합니다.  <br/> |
|**UserSite2Key** <br/> |int  <br/> |기본, 외래  <br/> |[Usersite 테이블](usersite.md)의 참조입니다.  <br/> |
   

