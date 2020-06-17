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
localization_priority: Normal
description: 파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다. 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754058"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>파일럿 풀 배포에 대한 DNS 레코드 구성

파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다. 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
  
### <a name="to-configure-dns-host-a-records"></a>DNS 호스트 A 레코드를 구성하려면

1. DNS(Domain Name System) 서버에서 **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.
    
2. 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 비즈니스용 Skype 서버 2019이 설치 될 도메인을 마우스 오른쪽 단추로 클릭 합니다.
    
3. **새 호스트(A 또는 AAAA)** 를 클릭합니다.
    
4. **이름을**클릭 하 고 비즈니스용 Skype 서버 2019 풀의 호스트 이름을 입력 합니다 (도메인 이름은 레코드를 정의 하는 영역에서, A 레코드의 일부로 입력할 필요는 없음).
    
5. **Ip 주소**를 클릭 한 다음 프런트 엔드 풀의 ip 주소를 입력 합니다.
    
6. **호스트 추가**를 클릭한 다음 **확인**을 클릭합니다. 
    
7. 작업을 마쳤으면 **완료**를 클릭합니다.
    

