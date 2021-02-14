---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786099"
---
# <a name="contoso-case-study-phone-system"></a>Contoso 사례 연구: 전화 시스템

지리적 위치 및 기타 요인에 따라 Contoso에는 다음 전화 통신 솔루션을 사용하는 사무실이 있습니다.

- 사이트 유형 A: 비즈니스용 Skype Enterprise Voice

- 사이트 유형 B: 기존 레거시 전화 통신 시스템

- 사이트 유형 C: 비즈니스용 Skype Enterprise Voice 기존 전화 통신 시스템 조합


전체 조직에 대해 Microsoft Phone System 솔루션을 구현하기 위해 Contoso는 &mdash; PSTN(공용 전화망)에 연결하는 데 전화 시스템과 함께 사용할 다음 옵션 중 어떤 것이 사용되는지 각 사이트 유형에 대해 결정해야 합니다. &mdash;

- 통화 요금제가 있는 전화 시스템 

- 직접 라우팅을 통해 자체 PSTN 통신업체가 있는 전화 시스템 

- 직접 라우팅을 통해 전화 시스템과 통화 요금제 및 전화 시스템 조합
 
Contoso는 조직에 적합한 솔루션을 결정하기 위해 Microsoft Teams에서 [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 전화 통신 솔루션과 Ignite 2019 세션 [통화를 사용했습니다.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>사이트 유형 A: 비즈니스용 Skype Enterprise Voice 

Contoso 비즈니스용 Skype Enterprise Voice 허브 및 스포크로 설정되어 있습니다. 해당 지역에서 PSTN 게이트웨이를 유지 관리하는 중앙 위치가 있습니다. 이 지역에서 비즈니스용 Skype 사용자용 PSTN에 Enterprise Voice 위치가 있습니다. 종종 이러한 위성 사무실에는 자체 인터넷 수신이 없습니다. 이러한 사용자의 번호는 기존 SBC에 연결하는 SIP 트렁크에 있습니다. 

이미 배포된 SBC가 직접 라우팅 및 미디어 우회에 대해 인증되어 있는지 확인하기 위해 Contoso는 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러 목록을 [확인했습니다.](direct-routing-border-controllers.md)  

사용자의 전화 걸기 습관은 사용자가 피어 투 피어 오디오에 사용할 수 있는 비즈니스용 Skype 클라이언트가 있는 경우에도 확장을 사용하여 레거시 전화 통신 시스템에서 사용자를 전화하는 것이었다. 

Contoso는 다음 질문에 대한 결정을 기반으로 합니다.

- Q. 이 배포에서 제공하는 기능을 유지해야 하나요?<br>
  A. 아니요 

- Q. 타사 PBX 시스템 및 기타 전화 통신 장비와 상호 협력해야 하나요?<br>
  A. 아니요 

- Q. 현재 타사 통신업체를 유지해야 하나요?<br> A. 예(규제된 국가) 및 아니요 

- Q. 배포된 SBC에서 ROI를 얻을 필요가 있나요?<br> A. 그렇기도 하고 그렇지 않기도 하고  

- Q. 이 지역에서 Microsoft PSTN 통화 플랜을 사용할 수 있나요?<br> A. 그렇기도 하고 그렇지 않기도 하고 

Contoso는 질문에 대한 답변에 따라 다음을 결정했습니다.

- 통화 요금제가 있는 전화 시스템에서 PSTN 통화 계획을 사용할 수 있는 지역에 있는 사용자를 이동합니다. 

- PSTN 통화 요금제가 사용 가능한 지역에 있지 않은 사용자, SBC의 ROI가 아직 충족되지 않은 사이트에 있는 사용자, 직접 라우팅을 통해 전화 시스템에 전화 통신 규정이 있는 국가에 상주하는 사용자를 이동하세요. 

다음 다이어그램은 초기 비즈니스용 Skype Enterprise Voice 배포 및 이 배포가 Microsoft 통화 계획 및 직접 라우팅으로 마이그레이션된 방법을 보여 주며,

![상태 전후를 보여주는 다이어그램](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>사이트 유형 B: 기존 레거시 전화 통신 시스템

Contoso에는 레거시 전화 통신 시스템을 활용하는 많은 사무실이 있습니다. E1.64 전화 번호가 있는 사용자 하위 집합이 있는 반면 다른 사용자의 경우 내선 번호만 있습니다. 이러한 숫자는 PSTN 게이트웨이에 대한 TDM 트렁크에 있습니다. 사이트 내 전화 걸기에서는 내선 번호 앞에 사이트 코드를 사용하여 통화를 라우팅할 위치를 결정하여 구성되었습니다. 사용자의 전화 걸기 습관은 내선 번호로 전화를 걸기입니다.   

Contoso는 다음 질문에 대한 결정을 기반으로 합니다.

- Q. 이 배포에서 제공하는 기능을 유지해야 하나요?<br>
  A. 아니요 

- Q. 타사 PBX 시스템 및 기타 전화 통신 장비와 상호 협력해야 하나요?<br> A. 예

- Q. 현재 타사 통신업체를 유지해야 하나요?<br> A. 아니요 

- Q. Microsoft PSTN의 통화 요금제는 지역에서 사용할 수 있나요?<br> A. 그렇기도 하고 그렇지 않기도 하고 

Contoso는 질문에 대한 답변에 따라 다음을 결정했습니다. 

- 통화 요금제가 있는 전화 시스템에서 PSTN 통화 계획을 사용할 수 있는 지역에 있는 사용자를 이동합니다. 

- 직접 라우팅을 통해 전화 시스템에서 PSTN 통화 계획을 사용할 수 있는 지역에 있지 않은 사용자를 이동합니다. 

- 중요 비즈니스용 아날로그 디바이스에 대한 PSTN 연결을 유지 관리합니다.

다음 다이어그램에서는 원격 사이트를 사용하는 원래 레거시 시스템 배포와 로컬 미디어 최적화를 사용하여 직접 라우팅 배포로 마이그레이션하는 방법을 보여 주며,

**원래 레거시 배포**  
 ![ 상태 전후를 보여주는 다이어그램](media/voice-case-study-2.png)


**직접 라우팅을 통해 배포**

![상태 전후를 보여주는 다이어그램](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>사이트 유형 C: 비즈니스용 Skype Enterprise Voice 기존 전화 통신 시스템 조합

Contoso 비즈니스용 Skype Enterprise Voice 사용자의 번호는 SIP 트렁크에 상주하여 통신 사업자로부터 SBC에 상주합니다. 기존 전화 통신 시스템의 번호는 PSTN 게이트웨이에 대한 TDM 트렁크에 있습니다.   

Contoso는 다음 질문에 대한 결정을 기반으로 합니다.

- Q. 이 배포에서 제공하는 기능을 유지해야 하나요?<br>
  A. 아니요 

- Q. 타사 PBX 시스템 및 기타 전화 통신 장비와 상호 협력해야 하나요?<br> A. 아니요 

- Q. 현재 타사 통신업체를 유지해야 하나요?<br> A. 아니요 

- Q. 배포된 SBC에서 ROI를 얻을 필요가 있나요?<br> A. 그렇기도 하고 그렇지 않기도 하고  

- Q. 이 지역에서 Microsoft의 PSTN 통화 플랜을 사용할 수 있나요?<br> A. 아니요 

Contoso는 질문에 대한 답변에 따라 다음을 결정했습니다. 

- 직접 라우팅에 사용할 레거시 전화 통신 사용자의 경우 Contoso는 TDM 트렁크에서 SBC의 SIP 트렁크로 번호를 포팅했습니다. SBC는 직접 라우팅에 대해 인증을 받아야 합니다. 

- 전화 시스템으로 이동하는 사용자의 하위 집합을 지원하고 레거시 시스템을 통해 계속 라우팅할 수 있도록 레거시 전화 통신 시스템이 SBC의 다음 홉으로 설정됩니다.   

- 또한 Contoso는 사용자 행동 변경을 장려하고 사이트 간 확장 전화 걸기에 대한 종속성 제거를 위해 모든 내부 통화에 Teams를 사용하기 위한 지침을 제공했습니다.  

다음 다이어그램은 원래 비즈니스용 Skype Enterprise Voice 및 레거시 전화 통신 시스템 배포와 직접 라우팅을 사용하여 혼합 배포로 마이그레이션하는 방법을 보여 주며,

**원래 혼합 배포** 
 ![ 이전 상태를 보여주는 다이어그램](media/voice-case-study-4.png)

**직접 라우팅과 혼합 배포** 
 ![ 이전 상태를 보여주는 다이어그램](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>통화 플랜

Contoso는 통화 계획에 대한 구성 요구 사항을 결정하기 위해 통화 계획 핵심 배포 [결정을 검토했습니다.](calling-plan-landing-page.md#core-deployment-decisions) 결과로 결정된 결정은 다음이 결정됩니다. 

- Q. 내 사용자에게 국제 통화가 필요한가요?<br> A. 예 

- Q. 내 사용자에게 각각 직접 전화 번호가 있나요?<br> A. 오늘은 아니요. 사용하도록 설정된 모든 사용자는 DID을 받게 됩니다. 

- Q. 호출자 ID를 마스킹하거나 사용하지 않도록 설정하나요?<br> A. 사용자의 호출자 ID는 Contoso의 로컬 번호로 마스킹됩니다. 


## <a name="direct-routing"></a>직접 라우팅

Contoso는 전화 시스템 및 직접 라우팅에서 사용할 수 있는 기능을 포함하여 Office 365 기능을 최신으로 유지하기 위해 Ignite에 참석했습니다. 기술 리더와 설계자는 Ignite 2019 중에 제공된 지침을 사용하여 방향을 결정했습니다.  사용된 키 세션: 

- [Microsoft Teams 직접 라우팅의 성공 계획](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [직접 라우팅에 대한 업데이트](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>구성

### <a name="calling-plans-sites"></a>요금제 사이트 호출

Contoso는 라이선스를 획득하고 사용자에게 전화 번호를 할당하기 위해 통화 계획 설정의 [단계를 수행했습니다.](set-up-calling-plans.md) 

전화 번호를 할당해야 하는 사용자 수로 인해 Contoso는 PowerShell을 사용하여 전화 번호를 할당하기로 결정했습니다. Contoso에서 Teams PowerShell 개요를 사용한 다른 설정 외에도 PowerShell을 사용하여 번호를 &mdash; &mdash; [할당하는 방법을 알아보기 위해](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>직접 라우팅 사이트

Contoso의 On-Premises Telephony 인프라를 Microsoft Teams에 연결하기 위해 Contoso의 관리자는 직접 라우팅 구성의 단계를 따르고 [Microsoft Teams에서](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) 비디오 직접 라우팅을 검토하여 지침을 검토했습니다. [](direct-routing-configure.md)  Contoso는 인증된 SBC 공급업체에서 직접 라우팅 배포 설명서를 참조했습니다. 

SBC와 Microsoft Phone System 간에 직접 라우팅을 구성한 후 Contoso에서 구성을 테스트해야 합니다. 이를 위해 Contoso 관리자는 [Ignite 2019의](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)직접 라우팅에 대한 업데이트 세션에서 설명한 SIP 테스터 클라이언트를 사용했습니다. 직접 라우팅 세션 테두리 컨트롤러 연결을 테스트하기 위해 PowerShell 스크립트에서 SIP 테스터 클라이언트 스크립트 및 설명서를 다운로드했습니다.   


### <a name="local-media-optimization"></a>로컬 미디어 최적화

Contoso는 전 세계 여러 지역에서 로컬 미디어 최적화를 활용할 수 있는 기회를 보게 되었습니다. Contoso에 지원되는 시나리오는 직접 라우팅에 대한 [로컬 미디어 최적화에 설명되어 있습니다.](direct-routing-media-optimization.md) 로컬 미디어 최적화 구성은 SBC 공급업체와 Microsoft의 지침에 따라 완료되었습니다. 로컬 미디어 최적화에 대한 구성 단계는 다음과 같습니다. 

- 사용자 및 SBC 사이트 구성 

- SBC 공급업체 사양에 따라 SBC를 구성합니다. 

- 로컬 미디어 최적화에 사용되는 각 사이트에 외부 신뢰할 수 있는 IP 주소 추가    

- 네트워크 토폴로지 정의 

- 가상 네트워크 토폴로지 정의 

- 모드 결정: 로컬 사용자에 대한 항상 무시 또는 전용 

## <a name="networking-considerations"></a>네트워킹 고려 사항

Contoso에는 전화 시스템에 대해 활성화된 후 장시간 원격으로 작업해야 하는 여러 사용자가 있습니다. 사용자는 VPN을 사용하여 특정 사업부 애플리케이션에 액세스했습니다. VPN을 사용하는 동안 전화 시스템 사용자는 통화 품질 저하를 경험했습니다. 

품질 문제를 해결하기 위해 Contoso는 내부 앱에 대한 연결이 VPN에 남아 있는 동안 Office 365 트래픽이 인터넷을 트래버스하도록 허용하는 VPN 분할 터널링을 구현했습니다. Contoso는 VPN 분할 터널링을 구현하기 위해 [Office 365에 대한 VPN 분할 터널링](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)구현 지침을 따랐습니다.  

 





