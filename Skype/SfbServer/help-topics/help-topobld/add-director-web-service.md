---
title: 디렉터 웹 서비스 추가
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL `https://pool01.contoso.net`이 인 경우 기본 URL은 입니다 `pool01.contoso.net`.
ms.openlocfilehash: 2251f984c301e6baa005e9fba84fbc86a0560499
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418571"
---
# <a name="add-director-web-service"></a>디렉터 웹 서비스 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL `https://pool01.contoso.net`이 인 경우 기본 URL은 입니다 `pool01.contoso.net`.
  
디렉터를 하나만 배포하는 경우 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다. Director 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 서로 다른 내부 기본 URL을 지정할 수 있습니다. 이 URL은 풀 FQDN과 달라야 하며 internal-\<your base URL\>과 같은 형식일 수 있습니다.
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 `contoso.net`이지만 외부 도메인 이름은 입니다 `contoso.com`. 도메인 이름을 사용하여 외부 기본 URL을 정의 `contoso.com` 합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 
  

