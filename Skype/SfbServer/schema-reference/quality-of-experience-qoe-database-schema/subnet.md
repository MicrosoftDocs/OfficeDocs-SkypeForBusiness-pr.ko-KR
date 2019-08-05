---
title: Subnet 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 서브넷 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196520"
---
# <a name="subnet-table"></a>Subnet 테이블
 
서브넷 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |기본, 외래  <br/> |서브넷 IP에 대 한 정수 표현입니다.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||서브넷 마스크.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |외부  <br/> |[Usersite 테이블](usersite.md)에서 참조 합니다.  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||서브넷에 대 한 설명입니다.  <br/> |
   

