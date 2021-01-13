---
title: 프런트 엔드 웹 서비스 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이면 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
ms.openlocfilehash: 171cc8c912e1a1204d07be2c52c0e96bc1369991
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823988"
---
# <a name="add-front-end-web-services"></a>프런트 엔드 웹 서비스 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이면 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
  
Standard Edition 서버의 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다. Enterprise Edition 프런트 엔드 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 풀 FQDN(예: internal-)과 달라야 하는 다른 내부 기본 URL을 지정할 수 있습니다. \<your base URL\>
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우 contoso.com 도메인 이름을 사용하여 외부 기본 URL을 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 인스턴트 메시징 및 현재 상태를 사용하려면 프런트 엔드 풀에 대한 HTTP 액세스가 필요합니다.
  

