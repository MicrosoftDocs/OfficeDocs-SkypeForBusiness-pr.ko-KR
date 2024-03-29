---
title: 2016에서 VIS 풀 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '요약: 토폴로지 작성기에서 비즈니스용 Skype 서버 Interop 서버 풀을 만드는 방법을 설명하는 문서입니다.'
---

# <a name="create-a-vis-pool-in-skype-for-business-server"></a>2016에서 VIS 풀 비즈니스용 Skype 서버
 
**요약:** 토폴로지 작성기에서 비디오 비즈니스용 Skype 서버 풀을 만들 수 있습니다.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>토폴로지 작성기에서 VIS 또는 VIS 풀 만들기

1. 프런트 엔드 서버에서 토폴로지 작성기 열기 토폴로지 작성기 왼쪽 창에서 비디오 **Interop** 서버 풀을 마우스 오른쪽 단추로 클릭하고 새 **비디오 Interop 서버 풀을 클릭합니다**. 
    
2. 그러면 새 비디오 **Interop 서버 풀 만들기 마법사가 열** 립니다. 새 Video Interop 서버에 대한 풀 FQDN을 제공하고 이 풀에 서버가  하나만 있는 경우 또는 이  풀에 요구 사항에 따라 여러 서버가 있습니다.를 선택하고 다음을 **누르십시오**.
    
    비디오 Interop 서버 풀을 배포하여 고가용성을 제공하려면 이 풀에 여러 서버 **가 있습니다.를 선택합니다**. 이 옵션에 유의하세요. 
    
    - Video Interop 서버 풀을 지원하려면 DNS 부하 분산을 배포해야 합니다. 
    
   - 다음 페이지의 이 풀의 컴퓨터 정의  항목에 대해 풀에 있는 각 서버의 컴퓨터 **FQDN** 을 텍스트 필드에 입력한 다음 추가를 **클릭합니다**. 풀에 다른 Video Interop 서버를 추가하기 위해 이 단계를 반복합니다. 풀의 모든 컴퓨터를 정의한 경우 다음을 **누르고 있습니다**.
    
     고가용성을 요구하지 않는 비디오 Interop 서버를 풀에 하나만 배포하려면 이 풀에 서버가 하나만  있습니다.를 선택하고 **다음을 누르고 있습니다**.
    
3. 드롭다운 목록에서 다음 홉 풀/FE를 선택하고 다음을 **누르고 있습니다**.
    
4. VIS와 연결하려면 에지 풀을 선택하고 마친을 **누르십시오**.
    
5. TCP 또는 TLS 포트를 설정합니다.
    
    토폴로지 작성기 왼쪽 창에서 새로 추가된 Video Interop 서버를 선택하고 마우스 오른쪽 단추로 클릭하고 속성 편집 **을 선택합니다**. 요구 사항에 따라 TCP 또는 TLS 포트를 사용하도록 설정 또는 업데이트하고 확인을 **선택 합니다**. 기본적으로 TLS가 추가되어도 Cisco Unified Communications Manager(CallManager 또는 CUCM)를 통해 TCP만 완전히 테스트되었습니다.
    
6. 비디오 게이트웨이를 추가합니다. 이렇게하려면 공유 구성 요소를 확장하고 비디오 게이트웨이를 마우스 오른쪽 단추로 클릭 **한** 다음 **새 비디오 게이트웨이를 선택합니다**.
    
7. 비디오 게이트웨이 FQDN 또는 IP 주소를 제공합니다. 비디오 게이트웨이가 하위 도메인 또는 다른 도메인에 있을 수 있습니다. 시스템의 VTC에서 사용하는 CUCM은 비디오 게이트웨이 역할을 합니다.
    
8. IPv4 또는 IPv6을 적절하게 선택합니다. 구성된 모든 IP 주소를 사용하거나 서비스 사용을 선택한 IP 주소로 제한할 수 있습니다.
    
9. 비디오 게이트웨이의 수신 포트를 선택합니다. TCP 또는 TLS(전송 프로토콜)를 선택하고 비디오 SIP 트렁크에 대해 설정된 Video Interop 서버와 연결합니다. 비디오 게이트웨이의 전송 프로토콜은 VIS에 대해 구성된 전송 프로토콜과 일치해야 합니다.
    
10. 위의 단계를 완료하면 해당 SIP 비디오 트렁크가 추가됩니다. SIP 비디오 트렁크를 마우스 오른쪽 단추로 클릭하고 방금 추가한 트렁크를 선택합니다. 비디오 SIP 트렁크 이름, 연결된 Video Interop 서버, SIP 전송 프로토콜 및 포트를 모두 변경할 수 있습니다. 
    
    > [!NOTE]
    >  비디오 Interop 서버는 1:N 트렁크를 지원합니다. 따라서 여러 트렁크를 추가할 수 있습니다. 이 트렁크는 단일 Video Interop 서버와 연결됩니다. 여기서 각 트렁크는 다른 비디오 게이트웨이에서 종료됩니다. 제한은 특정 비디오 게이트웨이에 하나의 트렁크만 있으며 이러한 트렁크를 배포에 정의할 수 비즈니스용 Skype 서버 있습니다.
  
11. Create [and publish new topology in 비즈니스용 Skype 서버 2015](../../deploy/install/create-and-publish-new-topology.md)에 설명된 토폴로지 문서를 게시합니다.
    
    > [!NOTE]
    > 복원성을 향상하기 위해 두 번째 Video Interop 서버 또는 VIS 풀 또는 백업 프런트 엔드 풀을 구성할 수 있습니다. 자세한 [내용은 탄력성 메커니즘](../../plan-your-deployment/video-interop-server.md#resiliency) 을 참조하세요.
  
이제 토폴로지 작성기에서 수행한 모든 작업이 완료됩니다. 계속 새 VIS 서버 또는 서버에 소프트웨어를 설치합니다.
## <a name="see-also"></a>참고 항목

[VIS 서버 역할 배포를 비즈니스용 Skype 서버](deploy-the-vis-server-role.md)

[2013의 비디오 Interop 서버 비즈니스용 Skype 서버](../../plan-your-deployment/video-interop-server.md)
  
[비즈니스용 Skype 서버 2015에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md)
