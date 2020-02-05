---
title: 비즈니스용 Skype 서버의 토폴로지 작성기에 추가 trunks 정의
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: afd8a37272d7450115f688bafe3627fb2689903c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767721"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 토폴로지 작성기에 추가 trunks 정의
 
**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하는 방법에 대해 알아봅니다.
  
이 단계에 따라 피어를 중재 서버와 연결할 수 있는 추가 트렁크를 정의 합니다. 피어는 PSTN (공개 통신 네트워크) 연결을 통해 엔터프라이즈 음성을 사용할 수 있는 사용자를 제공 합니다. 피어는 ITSP (인터넷 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (세션 경계 컨트롤러) 일 수 있습니다.
  
트렁크는 중재 서버와 게이트웨이 간의 논리적 연결입니다.
  
> [!NOTE]
> 이 항목에서는 배포 설명서의 [비즈니스용 Skype 서버에서 토폴로지 작성기의 게이트웨이 정의](define-a-gateway.md) 에서 설명한 대로 하나 이상의 collocated 또는 독립 실행형 중재 서버 또는 풀을 사용 하 여 PSTN 게이트웨이 및 루트 트렁크를 설정 하는 것으로 가정 합니다.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하려면

1. 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.
    
2. 비즈니스용 Skype 서버, 사이트 이름, **공유 구성 요소**에서 **Trunks** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 트렁크**를 클릭 합니다.
   1. **새 트렁크 정의**에서 트렁크를 고유 하 게 식별 하는 대화명을 지정 합니다. 두 개의 trunks 같은 이름을 사용할 수 없습니다.
    
      > [!NOTE]
      > 전송 형식으로 TLS (전송 계층 보안)를 지정 하는 경우 중재 서버 피어의 피어 IP 주소 대신 FQDN을 지정 해야 합니다. 
  
3. **연결 된 PSTN 게이트웨이에서**이 트렁크와 연결할 pstn 게이트웨이 피어를 선택 합니다.
    5. **Pstn 게이트웨이의 수신 대기 포트**에서 피어 (pstn 게이트웨이, IP-PBX 또는 SBC)가이 트렁크와 연결할 중재 서버에서 SIP 메시지를 수신 하는 수신 대기 포트를 입력 합니다. 기본 피어 포트는 TCP (전송 제어 프로토콜) 및 TLS (전송 계층 보안) 용 5067의 5066입니다. 기본 Survivable Branch 기기 포트는 TCP 및 TLS 용 5082의 5081입니다.
    
4. **SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 합니다.
    
    > [!NOTE]
    > 보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다. 
  
5. **연결 된 중재 서버**에서이 피어의 루트 트렁크에 연결할 중재 서버 풀을 선택 합니다.
    
6. **연결 된 중재 서버 포트**에서 중재 서버가 피어에서 SIP 메시지를 수신할 수신 대기 포트를 입력 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype 서버에서 여러 트렁크 지원 기능을 사용 하는 경우 두 개의 trunks 같은 **연결 된 중재 서버 포트** 와 **수신 대기 포트 (IP/PSTN 게이트웨이** )를 사용 하 여 다른 트렁크 이름을 구성할 수 없습니다.
  
    > [!NOTE]
    > 비즈니스용 Skype Server의 여러 트렁크 지원 기능을 사용 하면 여러 피어와 통신 하기 위해 중재 서버에서 여러 개의 SIP 신호 포트를 정의할 수 있습니다. 트렁크를 정의할 때 **연결 된 중재 서버 포트** 번호는 중재 서버에서 허용 하는 해당 프로토콜에 대 한 수신 대기 포트 범위 내에 있어야 합니다. 이 포트 범위는 비즈니스용 Skype 서버 및 중재 서버 풀에 정의 되어 있습니다. 관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **수신 대기 포트** 필드에 포트 범위를 지정 합니다.
  
7. **확인**을 클릭합니다. 
    

