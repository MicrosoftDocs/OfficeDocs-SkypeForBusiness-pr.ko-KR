---
title: 서브넷 테이블
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: 10df067fe95f244aea2fa9987b4962efaef9fbe32fbbfbe5b0e9f6ed9f6392e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279964"
---
# <a name="subnet-table"></a>서브넷 테이블
 
Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primary, Foreign  <br/> |정수로 표시된 서브넷 IP입니다.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||서브넷 마스크입니다.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |외계인  <br/> |[UserSite 테이블에서 참조됩니다.](usersite.md)  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||서브넷에 대한 설명입니다.  <br/> |
   

