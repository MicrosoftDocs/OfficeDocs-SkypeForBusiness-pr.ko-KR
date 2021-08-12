---
title: UserSite 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 사용자 사이트를 나타냅니다.
ms.openlocfilehash: 01ab76218040d37176355d62768c6a8b8f4b7336d22ce7263c61ac9fc8c289ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314334"
---
# <a name="usersite-table"></a>UserSite 테이블
 
UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 사용자 사이트를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |사용자 사이트를 식별하는 고유 번호입니다.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Unique  <br/> |사용자 사이트의 이름입니다.  <br/> |
|**RegionKey** <br/> |int  <br/> |외계인  <br/> |[Region 테이블에서 참조됩니다.](region.md)  <br/> |
   

