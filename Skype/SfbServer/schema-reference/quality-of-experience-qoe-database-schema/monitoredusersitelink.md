---
title: MonitoredUserSiteLink 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 한 링크를 나타냅니다.
ms.openlocfilehash: 7c9e924092b687abe6fefe579109e943fd7c71ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399532"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 테이블
 
MonitoredUserSiteLink 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 한 링크를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primary, Foreign  <br/> |[UserSite 테이블에서 참조됩니다](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primary, Foreign  <br/> |[UserSite 테이블의 참조입니다](usersite.md).  <br/> |
   

