---
title: DNS SRV 레코드 업데이트
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812776"
---
# <a name="update-dns-srv-records"></a>DNS SRV 레코드 업데이트

이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.
  
이 항목에서는 비즈니스용 Skype 서버 2019으로 마이그레이션한 후 DNS (Domain Name System) 레코드를 업데이트 하는 방법에 대해 설명 합니다. 모든 사용자가 비즈니스용 Skype 서버 2019로 이동 했지만 레거시 풀 또는 디렉터를 해제 하기 전에 모든 SIP 도메인에 대 한 내부 DNS의 DNS SRV 레코드를 업데이트 해야 합니다. 이 절차에서는 내부 DNS에 SIP 사용자 도메인에 대 한 영역이 있다고 가정 합니다.
  
## <a name="to-configure-a-dns-srv-record"></a>DNS SRV 레코드를 구성 하려면

1. DNS 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **dns**를 클릭 합니다.
    
2. SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 하 고 비즈니스용 Skype 서버 2019이 설치 되어 있는 SIP 도메인을 확장 한 다음 **_tcp** 설정으로 이동 합니다. 
    
3. 오른쪽 창에서 **_sipinternaltls** 를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.
    
4. **이 서비스를 제공**하는 호스트에서 비즈니스용 Skype 서버 2019 풀을 가리키도록 호스트 FQDN을 업데이트 합니다.
    
5. **확인**을 클릭합니다.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>프런트 엔드 풀 또는 Standard Edition 서버의 FQDN을 확인할 수 있는지 확인 하려면

1. 도메인의 클라이언트 컴퓨터에 로그온 합니다.
    
2. **시작**을 클릭 한 다음 **실행**을 클릭 합니다.
    
3. **열기** 상자에 cmd를 입력 한 다음 **확인**을 클릭 합니다.
    
4. 명령 프롬프트에서 _ \<프런트 엔드 풀\> 의 nslookup fqdn_ 또는 _ \<Standard Edition server\>의 fqdn_을 입력 한 다음 enter 키를 누릅니다.
    
5. FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.
    

