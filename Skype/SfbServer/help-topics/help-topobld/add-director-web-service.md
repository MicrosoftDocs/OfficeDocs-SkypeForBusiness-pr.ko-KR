---
title: 디렉터 웹 서비스 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 `https://pool01.contoso.net` URL은 `pool01.contoso.net` 입니다.
ms.openlocfilehash: 26e7056e670225aabf812bfe9dc782d800325757
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863985"
---
# <a name="add-director-web-service"></a>디렉터 웹 서비스 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 `https://pool01.contoso.net` URL은 `pool01.contoso.net` 입니다.
  
디렉터를 하나만 배포하는 경우 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다. Director 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 서로 다른 내부 기본 URL(풀 FQDN과 달라야 하며 internal- 등)을 지정할 수 있습니다. \<your base URL\>
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 이지만 외부 `contoso.net` 도메인 이름은 `contoso.com` 입니다. 도메인 이름을 사용하여 외부 기본 URL을 `contoso.com` 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 
  

