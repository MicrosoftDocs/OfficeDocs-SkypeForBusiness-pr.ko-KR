---
title: 서브넷 테이블
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: 92e582332e0e7c20c443a57c4ba0cc6abbb66cad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394600"
---
# <a name="subnet-table"></a>서브넷 테이블
 
Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primary, Foreign  <br/> |정수로 표시된 서브넷 IP입니다.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||서브넷 마스크입니다.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |외계인  <br/> |[UserSite 테이블에서 참조됩니다](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||서브넷에 대한 설명입니다.  <br/> |
   

