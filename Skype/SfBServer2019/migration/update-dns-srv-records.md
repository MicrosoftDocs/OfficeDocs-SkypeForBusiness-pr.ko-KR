---
title: DNS SRV 레코드 업데이트
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
ms.openlocfilehash: 1b88ada924cbf2cf7f4153acda54584d81946cb0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579422"
---
# <a name="update-dns-srv-records"></a>DNS SRV 레코드 업데이트

이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
  
이 항목에서는 2019년 8월 1일로 마이그레이션한 후 DNS(Domain Name System) 레코드를 업데이트하는 비즈니스용 Skype 서버 설명합니다. 모든 사용자를 비즈니스용 Skype 서버 2019로 이동한 후 레거시 풀 또는 디렉터를 해제하기 전에 모든 SIP 도메인에 대한 내부 DNS의 DNS SRV 레코드를 업데이트해야 합니다. 이 절차에서는 내부 DNS에 SIP 사용자 도메인의 영역이 있다고 가정합니다.
  
## <a name="to-configure-a-dns-srv-record"></a>DNS SRV 레코드를 구성하려면

1. DNS 서버에서 **시작**, **관리 도구** 를 차례로 클릭한 다음 **DNS** 를 클릭합니다.
    
2. SIP 도메인의 콘솔 트리에서 정방 검색 영역, 비즈니스용 Skype 서버 2019가 설치된 SIP 도메인을 확장하고 _tcp **설정으로** 이동합니다. 
    
3. 오른쪽 창에서 마우스 오른쪽 단추로 _sipinternaltls **속성을** **선택합니다.**
    
4. 이 **서비스를 제공하는** 호스트에서 호스트 FQDN이 2019 풀을 비즈니스용 Skype 서버 업데이트합니다.
    
5. **확인** 을 클릭합니다.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>프런트 엔드 풀 또는 Standard Edition Server의 FQDN을 확인할 수 있는지 확인하려면

1. 도메인의 클라이언트 컴퓨터에 로그온합니다.
    
2. **시작** 을 클릭한 다음 **실행** 을 클릭합니다.
    
3. 열기 **상자에** cmd를 입력하고 확인을 **클릭합니다.**
    
4. 명령 프롬프트에 nslookup _\<FQDN of the Front End pool\>_ 또는 를 입력한  _\<FQDN of the Standard Edition server\>_ 다음 Enter를 누를 수 있습니다.
    
5. FQDN에 대해 적절한 IP 주소로 확인되는 응답이 수신되는지 확인합니다.
    

