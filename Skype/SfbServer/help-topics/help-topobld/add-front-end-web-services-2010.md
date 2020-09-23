---
title: 프런트 엔드 웹 서비스 2010 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 인 경우 https://pool01.contoso.net 기본 URL은 pool01.contoso.net입니다.
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217959"
---
# <a name="add-front-end-web-services-2010"></a>프런트 엔드 웹 서비스 2010 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 인 경우 https://pool01.contoso.net 기본 URL은 pool01.contoso.net입니다.
  
Standard Edition 서버에 대 한 내부 웹 서비스 풀 FQDN (정규화 된 도메인 이름)은 재정의할 수 없습니다. Enterprise Edition 프런트 엔드 풀에 대해 DNS (Domain Name System) 부하 분산을 구성 하는 경우에는 다른 내부 기본 URL (풀 FQDN과는 다르며, 내부-)을 지정할 수 있습니다 \<your base URL\> .
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우를 예로 들 수 있습니다. 이 경우 contoso.com 도메인 이름을 사용하여 외부 기본 URL을 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 인스턴트 메시징 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.
  

