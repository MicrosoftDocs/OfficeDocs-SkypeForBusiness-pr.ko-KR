---
title: 파일럿 풀 배포에 대한 DNS 레코드 구성
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
description: 파일럿 풀을 배포하기 전에 파일럿 풀에 대한 DNS 호스트 A 항목을 업데이트해야 합니다. 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
ms.openlocfilehash: e77a85d84debadc19e52cb2d195ac86f5b3e6055
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588060"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>파일럿 풀 배포에 대한 DNS 레코드 구성

파일럿 풀을 배포하기 전에 파일럿 풀에 대한 DNS 호스트 A 항목을 업데이트해야 합니다. 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
  
### <a name="to-configure-dns-host-a-records"></a>DNS 호스트 A 레코드를 구성하려면

1. DNS(Domain Name System) 서버에서 **시작**, **관리 도구** 를 차례로 클릭한 다음 **DNS** 를 클릭합니다.
    
2. 도메인의 콘솔 트리에서 정방 검색 영역 을 확장한 다음 2019년 2019년을 설치할 도메인을 비즈니스용 Skype 서버 클릭합니다. 
    
3. **새 호스트(A 또는 AAAA)** 를 클릭합니다.
    
4. 이름을 **클릭하고** 비즈니스용 Skype 서버 2019 풀의 호스트 이름을 입력합니다. 도메인 이름은 레코드가 정의된 영역으로 사용되어 A 레코드의 일부로 입력할 필요가 없습니다.
    
5. **IP 주소를 클릭한** 다음 프런트 엔드 풀의 IP 주소를 입력합니다.
    
6. **호스트 추가** 를 클릭한 다음 **확인** 을 클릭합니다. 
    
7. 작업을 마쳤으면 **완료** 를 클릭합니다.
    

