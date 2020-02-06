---
title: UserSite 테이블
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805006"
---
# <a name="usersite-table"></a>UserSite 테이블
 
UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |주요한  <br/> |사용자 사이트를 식별 하는 고유 번호입니다.  <br/> |
|**UserSiteName** <br/> |name  <br/> |독특한  <br/> |사용자 사이트의 이름입니다.  <br/> |
|**국가 키** <br/> |int  <br/> |외부  <br/> |[지역 테이블](region.md)에서 참조 합니다.  <br/> |
   

