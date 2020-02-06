---
title: 비즈니스용 Skype 서버에서 VIS 풀 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '요약: 토폴로지 작성기를 사용 하 여 비즈니스용 Skype 서버에서 비디오 Interop 서버 풀을 만듭니다.'
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798055"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 VIS 풀 만들기
 
**요약:** 토폴로지 작성기를 사용 하 여 비즈니스용 Skype 서버에서 비디오 Interop 서버 풀을 만듭니다.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 VIS 또는 VIS 풀 만들기

1. 프런트 엔드 서버에서 토폴로지 작성기를 엽니다. 토폴로지 작성기의 왼쪽 창에서 **비디오 Interop 서버 풀** 을 마우스 오른쪽 단추로 클릭 하 고 **새 비디오 interop 서버 풀**을 선택 합니다. 
    
2. **새 비디오 Interop 서버 풀 만들기** 마법사가 열립니다. 새 비디오 Interop 서버의 풀 FQDN을 제공 하 고 **이 풀에 서버가 하나** 있거나 요구 사항에 따라 **여러 서버가 있는** 경우 **다음**을 누릅니다.
    
    고가용성을 제공 하기 위해 비디오 Interop 서버 풀을 배포 하려는 경우 **이 풀에 여러 서버가 있는**경우를 선택 합니다. 이 옵션은 다음을 염두에 두어야 합니다. 
    
    - 비디오 Interop 서버 풀을 지원 하려면 DNS 부하 분산을 배포 해야 합니다. 
    
   - 다음 페이지에서 **이 풀의 컴퓨터 정의** 항목에 대해 풀에 있는 각 서버의 **컴퓨터 FQDN** 을 텍스트 필드로 입력 하 고 **추가**를 클릭 합니다. 이 단계를 반복 하 여 다른 비디오 Interop 서버를 풀에 추가 합니다. 풀의 모든 컴퓨터를 정의한 경우 **다음**을 누릅니다.
    
     고가용성이 필요 하지 않으므로 풀에 비디오 Interop 서버를 하나만 배포 하려는 경우 **이 풀에 서버가 하나** 있고 **다음**을 누릅니다 .를 선택 합니다.
    
3. 드롭다운 목록에서 다음 홉 풀/FE를 선택 하 고 **다음**을 누릅니다.
    
4. VIS와 연결할 Edge 풀을 선택 하 고 **마침을**누릅니다.
    
5. TCP 또는 TLS 포트를 설정 합니다.
    
    토폴로지 작성기의 왼쪽 창에서 새로 추가한 비디오 Interop 서버를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **속성 편집**을 선택 합니다. 요구 사항에 따라 TCP 또는 TLS 포트를 사용 하거나 업데이트 하 고 **확인**을 선택 합니다. 기본적으로 TLS가 추가 되지만, Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM)를 사용 하 여 TCP만 완전히 테스트 되었습니다.
    
6. 비디오 게이트웨이를 추가 합니다. 이렇게 하려면 공유 구성 요소를 확장 하 고 **비디오 게이트웨이** 를 마우스 오른쪽 단추로 클릭 한 다음 **새 비디오 게이트웨이**를 선택 합니다.
    
7. 비디오 게이트웨이 FQDN 또는 IP 주소를 제공 합니다. 비디오 게이트웨이는 하위 도메인 이나 다른 도메인에 있을 수 있습니다. 시스템의 VTCs에서 사용 하는 CUCM 비디오 게이트웨이 역할을 합니다.
    
8. IPv4 또는 IPv6 중 적절 하 게 선택 합니다. 구성 된 모든 IP 주소를 사용 하거나 선택한 IP 주소로 서비스 사용량을 제한할 수 있습니다.
    
9. 비디오 게이트웨이의 수신 대기 포트를 선택 합니다. 전송 프로토콜 (TCP 또는 TLS)을 선택 하 고 비디오 SIP 트렁크 용으로 설정 된 비디오 Interop 서버와 연결 합니다. 비디오 게이트웨이의 전송 프로토콜이 VIS에 대해 구성 된 전송 프로토콜과 일치 해야 합니다.
    
10. 위의 단계가 완료 된 후 해당 SIP 영상 트렁크가 추가 됩니다. SIP 비디오 트렁크를 마우스 오른쪽 단추로 클릭 하 고 방금 추가한 트렁크를 선택 합니다. 비디오 SIP 트렁크 이름, 연결 된 비디오 Interop 서버, SIP 전송 프로토콜 및 포트 모두 변경할 수 있습니다. 
    
    > [!NOTE]
    >  비디오 Interop 서버는 1: N trunks를 지원 합니다. 따라서 각 트렁크가 다른 비디오 게이트웨이에서 종료 되는 단일 영상 Interop 서버와 연결 된 여러 trunks을 추가할 수 있습니다. 이 제한 사항은 특정 비디오 게이트웨이에 비즈니스용 Skype 서버 배포에 정의할 수 있는 트렁크가 하나만 있다는 것입니다.
  
11. 비즈니스용 [Skype 서버 2015에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md)에 설명 된 대로 토폴로지 문서를 게시 합니다.
    
    > [!NOTE]
    > 복구 력을 개선 하기 위해 두 번째 비디오 Interop 서버 또는 VIS 풀 또는 백업 프런트 엔드 풀을 구성할 수 있습니다. 자세한 내용은 [회복성 메커니즘](../../plan-your-deployment/video-interop-server.md#resiliency) 을 참조 하세요.
  
이제 토폴로지 작성기를 사용 하 여 수행 하는 모든 작업이 완료 됩니다. 새 VIS 서버 또는 서버에 소프트웨어 설치를 계속 합니다.
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 VIS 서버 역할 배포](deploy-the-vis-server-role.md)

[비즈니스용 Skype 서버의 비디오 Interop 서버 계획](../../plan-your-deployment/video-interop-server.md)
  
[비즈니스용 Skype 서버 2015에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md)
