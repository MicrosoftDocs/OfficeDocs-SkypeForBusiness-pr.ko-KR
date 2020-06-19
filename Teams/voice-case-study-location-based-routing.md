---
title: 팀 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786075"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso 사례 연구: 위치 기반 라우팅

LBR (위치 기반 라우팅)은 전화를 걸거나 받을 때 정책 및 사용자의 실제 위치에 따라 유료 바이패스를 제한 하는 기능입니다.  

## <a name="overview"></a>개요

Contoso는 해외 전화 통신망 (PSTN) 공급자를 우회 하 여 장거리 통화 비용을 줄일 수 없는 국가의 두 곳을 보유 하 고 있습니다. 기본 office에는 본사와 두 번째 사무실에서 사용 하는 인터넷 연결이 있습니다. 각 사무실에는 PSTN 통신 업체에 연결 된 자체 세션 경계 컨트롤러 (SBC)가 있습니다.  
 
이 국가에서 Contoso는 비즈니스용 Skype 배포에 대해 LBR을 구성 했습니다. 팀의 LBR을 구성 하는 방법을 결정 하기 위해 Contoso는 [직접 라우팅에 대 한 계획 위치 기반 라우팅을](location-based-routing-plan.md)읽습니다. Contoso는 전화를 받을 수 있는 경우 (예를 들어 팀과 Skype가 통화를 수신 하는 경우), PSTN 통화를 팀 사용자에 게 전송할 수 있는 경우, 그리고 다른 팀 사용자를 PSTN 통화에 양도할 수 있는 경우와 같은 시나리오를 수행 한다고 결정 했습니다.  

비즈니스용 Skype의 경우 LBR이 PSTN 캐리어에 연결 되는 SBC (세션 경계 컨트롤러) SIP 트렁크으로 구성 되었습니다. 이 SBC의 경우 Contoso는 [인증 된 SBCs 목록을](direct-routing-border-controllers.md) 검토 하 고, 전달 된 SBC가 직접적인 라우팅에 대해 인증 되었지만 미디어 바이패스를 인증 받지 않았음을 확인 했습니다. LBR를 지원 하려면 직접 라우팅이 사이트의 SBC로 구성 되어야 하 고, 로컬 인터넷 송신이 필요 하며, SBC를 미디어 바이패스에 맞게 구성 해야 합니다. 이 정보에 따라 Contoso는 다음을 결정 했습니다.

- 기존 SBC가 미디어 바이패스를 인증 받을 때까지 팀의 사용을 지연 시킬 수 있습니다.   

- Contoso는 Office 365에 대 한 직접 경로에 기본 사이트 SBC를 사용 하기로 결정 했습니다.  기본 사이트 SBC는 원격 사이트의 프록시 SBC입니다.  

- Contoso는 인도를 기반으로 하는 타사 컨설턴트를 사용 하 여 전화 통신 회사의 국가에서의 LBR 구성 인증을 지원 합니다.  

- 사무실 외부에서 작업 하는 사용자에 게 PSTN 통화를 지원 하기 위해 회사에서 발급 한 휴대 전화를 직원 들에 게 제공 했습니다. 

다음 다이어그램은 위치 기반 라우팅이 필요한 전화 통신 규정이 있는 국가에 대 한 이전 및 이후 배포를 보여 줍니다.

**원래 배포**

![이전 상태를 보여 주는 다이어그램](media/voice-case-study-5.png)

**직접 라우팅으로 배포**

![이전 상태를 보여 주는 다이어그램](media/voice-case-study-6.png)


## <a name="configuration"></a>구성 

팀에서 네트워크 구성 요소를 구성 하기 위해 Contoso는 [클라우드 음성 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)의 지침을 따릅니다. Contoso는 위치 기반 라우팅을 구성 하기 위해 아래 단계를 완료 했습니다. 

- 네트워크 지역 정의-네트워크 영역이 하나 정의 되었습니다. 

- 네트워크 사이트 정의-두 개의 네트워크 사이트가 정의 되었습니다. 지역 내의 각 사무실 위치에 대 한 사이트 한 대

- 네트워크 서브넷 정의-사무실 위치 내의 각 층에는 유선 및 무선 네트워크에 대 한 고유한 서브넷이 있습니다. 이 구성은 Contoso 용 서브넷을 20 개 생성 했습니다. 

- 신뢰할 수 있는 IP 주소 정의-SBC에 대 한 외부 IP 주소가 신뢰할 수 있는 IP 주소에 추가 되었습니다.  

