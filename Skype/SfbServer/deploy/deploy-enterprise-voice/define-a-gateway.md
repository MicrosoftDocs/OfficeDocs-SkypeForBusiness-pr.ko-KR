---
title: 비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 322c526c87c3a354f11fd0c906256b36e6df526e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233533"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의
 
**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 방법에 대해 알아봅니다.
  
다음 단계에 따라 토폴로지 작성기를 사용 하 여 엔터프라이즈 음성에 대해 사용 하도록 설정 된 사용자의 PSTN (공개 교환 전화 네트워크)에 대 한 연결을 제공 하기 위해 중재 서버를 연결할 수 있는 피어를 정의 합니다. 중재 서버에 대 한 피어는 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크를 구성 하 여 연결 하는 인터넷 통신 서비스 공급자 (ITSP)에 대 한 SBC (세션 경계 컨트롤러) 일 수 있습니다.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>중재 서버용 피어를 정의 하려면

1. 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.
    
2. 비즈니스용 Skype 서버, 사이트 이름, 공유 구성 요소에서 **PSTN 게이트웨이** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 pstn 게이트웨이**를 클릭 합니다.
3. **새 IP/PSTN 게이트웨이 정의**에서 피어의 FQDN (정규화 된 도메인 이름) 또는 IP 주소를 입력 하 고 **다음**을 클릭 합니다.
    
    > [!NOTE]
    > 전송 형식으로 TLS (전송 계층 보안)를 지정 하는 경우 중재 서버 피어의 피어 IP 주소 대신 FQDN을 지정 해야 합니다. 
  
4. 새 PSTN 게이트웨이의 IP 주소에 대 한 수신 모드 (ipv4 또는 Ipv6)를 정의 하 고 **다음**을 클릭 합니다.

5. PSTN 게이트웨이에 대 한 루트 트렁크를 정의 합니다. 트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.
    
    {중재 서버 FQDN, 중재 서버 수신 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 포트}
    
     - 토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 경우에는 토폴로지에 PSTN 게이트웨이를 성공적으로 추가 하기 위해 루트 트렁크를 정의 해야 합니다.
    
     - 연결 된 PSTN 게이트웨이를 제거할 때까지 루트 트렁크를 제거할 수 없습니다.
    
6. **IP/PSTN 게이트웨이의 수신 대기 포트**에서 게이트웨이, PBX 또는 SBC가 PSTN 게이트웨이의 루트 트렁크와 연결 되는 조정 서버의 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다. (기본적으로 포트는 TCP (전송 제어 프로토콜) 용 5066 이며 PSTN 게이트웨이, PBX 또는 SBC의 TLS (전송 계층 보안) 용 5067입니다. 지사 사이트의 Survivable Branch 기기에서 기본 포트는 TCP 용 5081이 고 TLS의 경우 5082입니다.
    
7. **SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 한 다음 **확인**을 클릭 합니다.
    
    > [!NOTE]
    > 보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다. 
  
8. **연결 된 중재 서버**에서이 PSTN 게이트웨이의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.
    
9. **연결 된 중재 서버 포트**에 중재 서버가 게이트웨이에서 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Server의 여러 트렁크 지원 기능을 사용 하면 여러 PSTN 게이트웨이와 통신 하기 위해 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다. 트렁크를 정의할 때 **연결 된 중재 서버 포트** 는 중재 서버에서 허용 하는 각 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다. 이 포트 범위는 비즈니스용 Skype 서버 및 중재 풀에 정의 되어 있습니다. 관심 있는 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **수신 대기 포트** 필드에 포트 범위를 지정 합니다.
  
10. 정의한 피어가 실행 중이 고 지정한 FQDN 또는 IP 주소를 사용 하 고 있는지 확인 합니다. 그런 다음 **마침을**클릭 합니다.
    
11. **비즈니스용 Skype 서버** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.
    

