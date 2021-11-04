---
title: 2016년 8월 전용 전화선 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 2016년 8월 전용(보조) 전화선 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 4c4a03d539835a1b776b729c83bdd1bf19e0ff82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763476"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>2016년 8월 전용 전화선 비즈니스용 Skype
 
2016년 8월 전용(보조) 전화선 비즈니스용 Skype 서버 Enterprise Voice.
  
비즈니스용 Skype 서버 사용하면 사용자에게 기본 전화선과 함께 두 번째 전용 전화선도 제공합니다. 전용 전화선은 경영진 및 직접 연결 가능한 등록되지 않은 전화 번호를 원하는 사람에게 할당되는 경우가 많습니다.
  
전용 전화선은 관리 셸을 사용하여 비즈니스용 Skype 서버 수 있습니다. 전용 전화선은 제어판을 사용하여 비즈니스용 Skype 서버 없습니다. 전용 전화선은 배포 시에만 구성해야 비즈니스용 Skype 서버 혼합 배포에서는 구성할 수 없습니다.
  
## <a name="characteristics-of-private-telephone-lines"></a>전용 전화선의 특성

제2 전용 전화선의 개념은 기본적으로 간단하지만 전용선의 특성과 사용자의 기본 전화선과 유사하고 다른 방법을 이해하는 것이 중요합니다.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>전용 전화선의 일반 특성

- 사용자 한 명이 하나의 전용 전화선만 유지할 수 있습니다.
    
- 전용 전화선을 사용하는 사용자는 하나의 음성 사서함만 유지하며 단일 전자 메일 주소로 부재 중 통화 알림을 받습니다.
    
- 전용 전화선을 사용하는 사용자에게는 보조 SIP 주소가 없으며, 보조 전용 전화선은 사용자에게 네트워크의 두 번째 현재 상태(예: 두 번째 인스턴트 메시징 ID)를 제공하지 않습니다. 
    
- 전용 전화선은 온-프레미스 배포에만 사용할 수 있습니다. 호스트된 배포에서는 사용할 수 비즈니스용 Skype 서버.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>전용 전화선이 기본 전화선과 다른 점

- 전용 전화선의 전화 번호는 전화 디렉터리 또는 Active Directory 도메인 서비스에서 파생된 연락처 목록에 표시되지 않습니다.
    
- 전용 전화선에서는 통화 전달, 팀 통화, 위임, 팀 링, 그룹 통화 선택 및 응답 그룹 응용 프로그램과 같은 기능을 사용할 수 없습니다.
    
- 전용 전화선 통화에는 특별한 벨소리가 지정되며, 시스템 알림에서 사용자에게 전용 회선으로 수신 전화가 걸려 왔음을 알려 줍니다.
    
- 전용 전화선 통화는 항상 벨이 울리며, "방해 금지" 규칙을 따르지 않습니다.
    
- 전용 전화선은 인바운드 전용이며, 발신 전화를 거는 데 사용할 수 없습니다. 전용 전화선이 있는 사용자가 전화를 걸면 통화가 사용자의 기본 전화선에서 시작된 것이고 사용자의 이름이나 사용자의 기본 전화 번호가 전화를 거는 사람을 숨기지 않습니다.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>전용 전화선이 기본 전화선과 유사한 점

- 응답하지 않은 전용 전화선 통화는 기본 전화선과 동일한 음성 메일 사서함으로 라우팅됩니다(음성 메일을 사용하도록 설정한 경우).
    
- 통화 파크 및 통화 Pickup은 사용자의 기본 전화선과 동일한 방식으로 전용 전화선에서 작동됩니다.
    
- 사용자의 기본 전화선에서 동시 벨 울림을 사용하도록 설정하면 전용 전화선에서도 동시 벨 울림을 사용할 수 있습니다.
    
- 전용 전화선의 전화 번호는 사용자의 기본 전화선 전화 번호와 같은 방식으로 통화 정보 기록에 기록되지만 전용 전화 번호로 표시됩니다.
    
- 사용자가 전용 전화선 통화에 응답하면 통화는 사용자의 기본 전화선 통화와 동일하게 처리됩니다. 예를 들어 전용 전화선으로 전화를 받은 사용자가 통화를 전달하거나 다른 사용자를 전화 회의에 초대하는 경우 사용자의 이름이 비즈니스용 Skype 표시되어 사용자의 기본 전화선의 전화 번호가 발신자 번호에 나타납니다.
    
- 사용자는 기본 전화선과 같은 방식으로 전용 전화선에서 통화를 돌릴 수(응답하기 전에 휴대폰이나 집 전화와 같은 다른 대상으로 통화 리디렉션) 있습니다. 
    
    > [!NOTE]
    > 전용선 통화가 대체 전화 번호로 라우팅된 경우에는 전용 전화선의 전화 번호를 대체 전화 번호로 사용할 수 있으며 이 번호에 대한 로그에 전용 전화선의 전화 번호가 표시될 수 있습니다. 
  
    > [!NOTE]
    > 전화 회의에서 전용 전화선으로 걸려오는 전화에는 수신 시스템 알림에 전용 회선이 표시되지 않습니다. 
  
## <a name="administering-private-telephone-lines"></a>전용 전화선 관리

전용 전화선을 만들고 관리하는 기술적인 측면 외에 설정해야 하는 관리 절차가 있습니다. 여기에는 조직에서 전용선을 사용할 수 있는 자격이 있는 사람에 대한 정책 결정, 사용자 및 이들의 전화선 목록 작성 및 유지 관리, 경영진에 대한 전용 전화 디렉터리 작성, 사용자 교육 계획 및 관련 작업이 포함됩니다.
  
> [!NOTE]
> 전용 전화선은 사용자 개체에 대한 msRTCSIP-PrivateLine 특성으로 Active Directory에 저장됩니다. 기본적으로 Authenticated Users 그룹의 모든 구성원은 이 특성에 대한 읽기 권한을 갖습니다. 
  
### <a name="assigning-telephone-numbers"></a>전화 번호 할당

 전용 전화선이 필요한 새 사용자의 계정은 전용 전화선이 없는 계정과 같은 방식으로 만들어지며, 비즈니스용 Skype 서버 제어판 또는 관리 비즈니스용 Skype 서버 됩니다.
  
비즈니스용 Skype 서버 관리 셸에서 **Set-CsUser** cmdlet을 사용하여 사용자의 전용 전화선에 전화 번호를 **할당합니다(예: Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**).
  
전용 전화선의 전화 번호는 3에서 15 사이의 숫자일 수 있으며 앞에 "TEL:" 앞에 와야 합니다. 또한 지역 코드 및 국가/지역 코드가 지정될 수 있습니다(조직에 해당 지역 코드 및 국가/지역 코드에 대한 DID(Direct Inward Dialing)가 있는 경우). 
  
cmdlet 및 비즈니스용 Skype 서버 관리 셸에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>혼합 배포에서의 전용 전화선

전용 전화선은 Lync Server 2013 또는 비즈니스용 Skype 서버 전용으로 구성해야 합니다. 이전 버전의 Lync Server를 실행하는 서버가 있는 배포에서 이전 버전의 사용자가 전용 전화선에 전화를 걸려 할 때 서버가 전용 전화선에서 역방향 전화 번호를 찾을 수 없는 경우 통화 라우팅이 실패합니다.
  

