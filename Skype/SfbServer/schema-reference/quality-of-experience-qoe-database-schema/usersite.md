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
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799918"
---
# <a name="usersite-table"></a>UserSite 테이블
 
UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 사용자 사이트를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |사용자 사이트를 식별하는 고유 번호입니다.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |고유  <br/> |사용자 사이트의 이름입니다.  <br/> |
|**RegionKey** <br/> |int  <br/> |외계인  <br/> |[Region 테이블에서 참조됩니다.](region.md)  <br/> |
   

