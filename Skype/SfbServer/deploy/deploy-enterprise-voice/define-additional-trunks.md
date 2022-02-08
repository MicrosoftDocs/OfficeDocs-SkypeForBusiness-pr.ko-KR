---
title: 토폴로지 작성기에서 추가 트렁크를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '요약: 중재 서버와 중재 서버의 토폴로지 작성기에서 게이트웨이 피어 간에 추가 트렁크를 정의하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: d490033f8efff1176fe9cca1fc7cbd7582e5e126
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388900"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>토폴로지 작성기에서 추가 트렁크를 비즈니스용 Skype 서버
 
**요약:** 중재 서버와 중재 서버의 토폴로지 작성기에서 게이트웨이 피어 간에 추가 트렁크를 정의하는 비즈니스용 Skype 서버.
  
다음 단계에 따라 피어를 중재 서버와 연결하기 위한 추가 트렁크를 정의합니다. 피어는 PSTN(Enterprise Voice 전화망)에 연결하여 사용자가 사용할 수 있도록 설정합니다. 피어는 ITSP(인터넷 전화 통신 서비스 공급자)에 대한 PSTN 게이트웨이, IP-PBX 또는 SBC(Session Border Controller)일 수 있습니다.
  
트렁크는 중재 서버와 게이트웨이 간의 논리적 연결입니다.
  
> [!NOTE]
> 이 항목에서는 배포 설명서의 [Define a gateway in Topology Builder in 비즈니스용 Skype 서버](define-a-gateway.md) 설명에 따라 하나 이상의 배치된 중재 서버 또는 독립 실행형 중재 서버 또는 풀을 사용하여 PSTN 게이트웨이 및 루트 트렁크를 설정했다고 가정합니다.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>중재 서버와 게이트웨이 피어 간에 추가 트렁크를 정의하기 위해

1. 토폴로지 작성기 시작 **: 시작,** 모든 **프로그램, 비즈니스용 Skype 서버** **2015** 를 클릭한 다음 비즈니스용 Skype 서버 **2015Topology Builder를 클릭합니다**.
    
2. 사이트 비즈니스용 Skype 서버 공유 구성 요소 아래에서 트렁크 노드를 마우스 오른쪽 단추로 클릭  한 다음 새 트렁크 **를 클릭합니다**.
   1. 새 **트렁크 정의에서** 트렁크를 고유하게 식별할 이름을 지정합니다. 이름이 같은 트렁크 두 개는 사용할 수 없습니다.
    
      > [!NOTE]
      > TLS(전송 계층 보안)를 전송 유형으로 지정하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정해야 합니다. 
  
3. 연결된 **PSTN 게이트웨이에서** 이 트렁크와 연결되는 PSTN 게이트웨이 피어를 선택합니다.
    5. **PSTN** 게이트웨이용 수신 포트에서 피어(PSTN 게이트웨이, IP-PBX 또는 SBC)가 이 트렁크와 연결될 중재 서버에서 SIP 메시지를 받을 수신 포트를 입력합니다. 기본 피어 포트는 TCP(Transmission Control Protocol)의 경우 5066, TLS(전송 계층 보안)의 경우 5067입니다. 기본 Survivable Branch Appliance 포트는 TCP의 경우 5081, TLS의 경우 5082입니다.
    
4. **SIP 전송 프로토콜에서** 피어가 사용하는 전송 유형을 클릭합니다.
    
    > [!NOTE]
    > 보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포하는 것이 좋습니다. 
  
5. 연결된 **중재 서버에서** 이 피어의 루트 트렁크와 연결하기 위해 중재 서버 풀을 선택합니다.
    
6. 연결된 **중재 서버 포트** 에서 중재 서버가 피어에서 SIP 메시지를 받을 수신 포트를 입력합니다.
    
    > [!NOTE]
    > 트렁크가 여러 개 비즈니스용 Skype 서버 동일한 트렁크 이름을 사용하는 두 트렁크를 **IP/PSTN** 게이트웨이용 수신 포트 및 연결된 중재  서버 포트로 구성할 수 없습니다.
  
    > [!NOTE]
    > 여러 트렁크 지원이 비즈니스용 Skype 서버 여러 피어와의 통신을 위해 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다. 트렁크를 정의할 때 연결된 중재  서버 포트 번호는 중재 서버에서 허용하는 각 프로토콜에 대한 수신 포트 범위 내에 있어야 합니다. 이 포트 범위는 비즈니스용 Skype 서버 및 중재 서버 풀 아래에 정의됩니다. 관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭하고 속성 **편집을 선택합니다**. **수신 대기 포트** 필드에서 포트 범위를 지정합니다.
  
7. **확인** 을 클릭합니다. 
    

