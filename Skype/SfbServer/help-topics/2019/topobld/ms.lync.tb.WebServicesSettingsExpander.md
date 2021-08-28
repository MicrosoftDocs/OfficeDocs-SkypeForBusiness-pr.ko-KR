---
title: 웹 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: 토폴로지 작성기 내에서 내부 및 외부 웹 서비스에 사용되는 포트 설정을 수정할 수 있습니다. 또한 DNS(Domain Name System) 부하 분산을 배포하는 경우 토폴로지 작성기에서 해당 풀에 있는 모든 서버의 실제 IP 주소로 확인되는 풀의 FQDN(FQDN)을 구성할 수 있습니다.
ms.openlocfilehash: f160259a78f5d95bd7e5e7e974579ddebe738115
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596992"
---
# <a name="web-services-settings-expander"></a>웹 서비스 설정 확장기
 
토폴로지 작성기 내에서 내부 및 외부 웹 서비스에 사용되는 포트 설정을 수정할 수 있습니다. 또한 DNS(Domain Name System) 부하 분산을 배포하는 경우 토폴로지 작성기에서 해당 풀에 있는 모든 서버의 실제 IP 주소로 확인되는 풀의 FQDN(FQDN)을 구성할 수 있습니다.
  
### <a name="editing-web-services-settings"></a>웹 서비스 설정 편집

1. 적절한 프런트 엔드 Standard Edition 프런트 엔드 풀 또는 Enterprise Edition 풀을 선택한 다음 속성 편집 **을 클릭합니다.**
    
2. **속성 편집** 대화 상자에서 **웹 서비스** 탭을 클릭합니다.
    
    > [!CAUTION]
    > 프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우 외부 웹 서비스 FQDN은 고유해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 pool01.contoso.com 경우 다른  pool01.contoso.com 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 FQDN을 사용할 수 없습니다.  또한 Director를 배포하는 경우 모든 Director 또는 Director 풀에 대해 정의된 외부 웹 서비스 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버뿐만 아니라 다른 모든 Director 또는 Director 풀과 고유해야 합니다. 내부 웹 서비스를 자체 정의 FQDN으로 다시 정의하려면 각 FQDN이 다른 프런트 엔드 풀, Director 또는 Director 풀과 고유해야 합니다.
  
3. Enterprise Edition 풀의 속성을 편집하는 경우 **FQDN** 다시 지정을 선택할 수 있습니다. 이 옵션은 DNS(Domain Name System) 부하 분산을 사용하는 경우만 선택해야 합니다. DNS 부하 분산을 사용하는 경우 **FQDN 다시 정의** 를 선택한 다음 텍스트 상자에 풀에 있는 모든 서버의 물리적 IP 주소로 확인되는 해당 풀의 FQDN을 입력합니다. DNS 부하 분산을 사용하지 않는 경우 및 **FQDN 다시 정의** 를 선택하지 않는 경우 내부 웹 서비스 FQDN을 변경할 수 없습니다. 내부 웹 서비스 FQDN은 내부 사용자가 내부 웹 서비스에 연결하는 데 사용하는 비즈니스용 Skype 서버.
    
4. 선택적으로 **수신 대기 포트** 및 **게시된 포트** 에 대한 새 HTTP, HTTPS 또는 HTTP 및 HTTPS 값을 입력합니다. 수신 대기 포트는 IIS(인터넷 정보 서비스)에서 들어오는 SIP(Session Initiation Protocol) 트래픽을 수신 대기하는 데 사용하는 포트이고, 게시된 포트는 부하 분산 장치 또는 역방향 프록시 서버에 구성된 포트로서 들어오는 SIP 트래픽을 수신 대기하는 데에도 사용됩니다. 기본적으로 HTTP 수신 대기 포트 및 HTTP 게시된 포트는 둘 다 포트 80으로 설정되고 해당 HTTPS 포트는 둘 다 443으로 설정됩니다. 두 HTTP 게시된 포트의 기본값은 8080이고 해당 HTTPS 포트는 4443으로 설정됩니다.
    
5. **확인** 을 클릭합니다.
    
내부 FQDN 또는 수신 포트 할당을 수정하는 경우 변경 내용을 적용하려면 풀의 모든 서버에서 로컬 설치를 다시 해야 합니다.
  

