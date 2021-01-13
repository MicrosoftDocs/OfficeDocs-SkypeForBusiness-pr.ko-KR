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
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831338"
---
# <a name="subnet-table"></a>서브넷 테이블
 
Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primary, Foreign  <br/> |정수로 표시된 서브넷 IP입니다.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||서브넷 마스크입니다.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |외계인  <br/> |[UserSite 테이블에서 참조됩니다.](usersite.md)  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||서브넷에 대한 설명입니다.  <br/> |
   

