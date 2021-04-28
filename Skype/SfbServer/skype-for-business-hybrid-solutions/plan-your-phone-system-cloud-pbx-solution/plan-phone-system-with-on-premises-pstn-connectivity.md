---
title: 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하여 전화 시스템 계획
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 사내 PSTN 연결을 통해 전화 시스템(클라우드 PBX)에 대한 계획 고려 사항을 자세히 알아보습니다.
ms.openlocfilehash: afa97a00b474017e6aed5e92802e7ba13483f7af
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064704"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하여 전화 시스템 계획

> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.  직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)

사내 PSTN 연결을 통해 전화 시스템(클라우드 PBX)에 대한 계획 고려 사항을 자세히 알아보습니다.

이 콘텐츠는 온-프레미스에 비즈니스용 Skype 서버 또는 Lync Server 2013이 이미 배포된 경우 관련이 있습니다. 다른 시나리오는 [Microsoft 전화 통신 솔루션을 참조하세요.](/microsoftteams/cloud-voice-landing-page)

 전화 시스템(사내 PSTN 연결을 통해 전화 시스템)을 통해 사용자에게 전화 시스템(클라우드 PBX) 기능을 활용할 수 있습니다. 이 시나리오는 다음과 같은 시나리오에 도움이 될 수 있습니다.

- 일부 비즈니스용 Skype 사용자는 사내에 있으며 다른 사용자는 비즈니스용 Skype Online에 있습니다. 이제 비즈니스용 Skype Online에 있는 사용자에 대해 전화 시스템 기능 및 기능을 사용하도록 설정할 수 있지만 계속해서 사내 PSTN 연결을 사용할 수 있습니다.

- 사용자가 일부 또는 전체를 비즈니스용 Skype Online으로 이동하지만 계속해서 사내 PSTN 연결을 사용하려는 경우,

    > [!IMPORTANT]
    > 사용자가 전자 메일 시스템(PSTN 연결)을 사용할 수 있도록 설정하려면 SIP 주소가 사용자 도메인에 있어야 합니다. Microsoft 365 또는 Office 365(Office 365)에 대한 기본 onmicrosoft.com 지원되지 않습니다. 

라이선싱 및 요금제 등 전화 시스템에 대한 자세한 내용은 [PSTN Calling plans for Skype for Business을 참조하세요.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)

## <a name="feature-comparison"></a>기능 비교

온-프레미스 PSTN 연결이 있는 클라우드 PBX는 완전한 온-프레미스 연결 솔루션과 동일한 Enterprise Voice 않습니다. 조직에 적합한 기능 집합을 제공하는 클라우드 PSTN 연결을 통해 클라우드 PBX가 조직에 적합한 기능을 제공할지 여부를 결정하는 데 도움이 되는 내용은 [클라우드 PBX를](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)사용하여 얻을 수 있는 정보를 참조하세요.

## <a name="benefits-and-planning-considerations"></a>이점 및 계획 고려 사항

> [!CAUTION]
> 비즈니스용 Skype Online으로 이동하기 전에 Lync Phone Edition 장치를 온-프레미스 환경에서 필요한 최소 펌웨어로 업데이트해야 합니다.
펌웨어를 업데이트하기 전에 사용자를 온라인에서 온라인으로 이동하는 경우 사용자는 자신의 휴대폰을 사용하여 연결할 수 없습니다. 이 문제를 해결하려면 휴대폰을 최소 펌웨어로 업데이트하려면 사용자를 다시 사내 환경으로 이동해야 합니다. 사용자를 다시 프레미스 환경으로 이동하기 전에 최소 펌웨어로 업데이트하거나 휴대폰을 하드 초기화하지 않습니다.
장치가 최소 펌웨어가 아닌 동안 하드 초기화가 수행되는 경우 기본적으로 비즈니스용 Skype Online에서 지원되지 않는 PIN 인증을 사용합니다. 자세한 내용은 비즈니스용 Skype Online의 전화기 [를 참조하세요.](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

온라인 PSTN 연결과 함께 전화 시스템을 배포하면 사용자들이 원하는 속도로 비즈니스용 Skype Online을 통해 클라우드로 이동하는 동시에, 자신의 사내 PSTN 연결을 유지할 수 있습니다. PBX가 있는 경우 계속 PBX를 사용하여 클라우드로 이동하는 사용자에게 PSTN 연결을 제공합니다. 사용자가 비즈니스용 Skype Online 및 전화 시스템으로 이동하면 레거시 PBX 전화가 더 이상 작동하지 않지만 해당 전화 번호는 비즈니스용 Skype 규격 책상 전화뿐만 아니라 PC 또는 스마트폰용 비즈니스용 Skype 클라이언트로 라우팅됩니다. 이식된 전화 시스템 사용자와 레거시 PBX 사용자는 일반 전화 번호를 사용하여 PSTN 통화를 걸고 받을 수 있습니다.

콜 센터와 같은 레거시 PBX에 대한 사용자 지정 기능이나 주요 추가 기능이 있을 수 있습니다. 현재 전화 시스템에서 사용자 지정 기능을 사용할 수 없는 경우 해당 사용자 지정 기능이 레거시 PBX를 사용하여 해당 사용자 지정 기능을 필요로 하는 사용자를 그대로 두고, 사용자 지정 기능에 액세스할 필요가 없는 사용자를 전화 시스템에 포트하기만 해야 합니다(사내 PSTN 연결 시).

비즈니스용 Skype 서버 2015와 직접 상호 운영되는 레거시 PBX 목록은 [Infrastructure Qualified for Microsoft Lync를 참조하세요.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) PBX가 이 목록에 없는 경우 세션 경계 컨트롤러를 사용하여 비즈니스용 Skype Online의 전화 시스템에 PBX를 연결할 수 있습니다.

### <a name="network-considerations-for-quality-and-performance"></a>품질 및 성능에 대한 네트워크 고려 사항

전화 시스템과 같은 클라우드 호스팅 서비스를 배포할 때에는 다음에 유의해야 합니다. 전적으로 비즈니스용 Skype 서버 2015 Enterprise Voice 배포에서는 모든 인프라와 클라이언트가 엔터프라이즈 자체 네트워크에 있습니다. 고품질 오디오 및 비디오에 중요한 이 네트워크의 품질과 성능은 엔터프라이즈 직원의 직접적인 제어에 있습니다. 전화 시스템에는 프레미스 PSTN 연결이 있는 세 개의 네트워크가 관련되어 있습니다. 이 중 2개는 고객이 담당하지만 그 중 하나는 엔터프라이즈 직원이 직접 제어할 수 있습니다.

- **Microsoft의 전역 미디어 배달 네트워크** Microsoft의 글로벌 클라우드 네트워크 및 인프라. 전화 시스템 서버 및 트래픽이 이 네트워크를 트래버스합니다.

- **엔터프라이즈/클라우드 PSTN 상호 연결** 엔터프라이즈를 클라우드에 연결하는 네트워크입니다. 이는 일반 인터넷 연결과 반드시 같을 필요는 없습니다.

- **기업의 자체 네트워크** 실시간 미디어의 품질은 자체 네트워크에 크게 의존합니다. 특히 WiFi 네트워크 및 클라우드에 도달하는 데 사용되는 상호 연결의 품질입니다.

> [!NOTE]
> 비즈니스용 Skype Online의 성능 조정에 대한 자세한 내용은 비즈니스용 Skype Online 성능 [조정을 참조하세요.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>전화 시스템을 사용할 때의 선행 준비 상태(전화 시스템과, 사내 PSTN 연결 시)

온라인 PSTN 연결을 사용하여 전화 시스템을 구성하고 사용자를 비즈니스용 Skype Online으로 이동하려면 먼저 다음과 같은 선행 구성이 준비되어 있는지 확인해야 합니다.

 **On-premises server versions.** On-premises PSTN connectivity를 통해 전화 시스템을 지원하려면 다음 표에 On-premises deployment의 서버 버전이 나열되어 있어야 합니다.


| **서버 역할**                                       | **지원되는 버전\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 페더ation 에지\*\*  <br/>                            | Business Server 2015용 Skype  <br/>                                                                              |
| 다음 홉 페더ation 경로 내부 풀 서버  <br/> | 비즈니스용 Skype 서버 2015, 2016년 3월 누적 업데이트 6.0.9319.235 이상(프런트 엔드 또는 Director)  <br/> |
| 프런트 엔드 사용자 서버  <br/>                          | Business Server 2015용 Skype  <br/> Lync Server 2013  <br/>                                                      |
| 에지 서버  <br/>                                    | Business Server 2015용 Skype  <br/>                                                                              |
| 중재 서버  <br/>                               | Business Server 2015용 Skype  <br/> Lync Server 2013  <br/>                                                      |

\*지원되는 최소 버전은:

- 비즈니스용 Skype 서버 2015, 2016년 3월 누적 업데이트 6.0.9319.235

- Lync Server 2013 2015년 7월 누적 업데이트 5.0.8308.920

\*\*지원되는 모든 SIP 도메인에 대한 페더전 경로는 2016년 3월 이상 누적 업데이트를 실행하는 비즈니스용 Skype 서버 2015 에지 서버를 통해 라우팅해야 합니다. 사용자 풀이 Lync Server 2013에 있는 경우 해당 외부 풀 트래픽은 Lync Server 2013 에지 서버에 남아 있습니다. 

또한 다음을 보장해야 합니다.

- **프레미스** Enterprise Voice 구성 및 테스트 여기에는 PSTN 연결 구성 요소가 포함됩니다. 자세한 내용은 비즈니스용 Skype 서버 2015를 사용하는 경우 Plan [for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 및 [Deploy Enterprise Voice in Skype for Business Server 2015를](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)참조하십시오.

    Lync Server 2013을 사용하는 경우 Planning [for Enterprise Voice in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) 및 [Deploying Enterprise Voice in Lync Server 2013를](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)참조합니다.

- **Active Directory 동기화** Azure AD Connect를 사용하여 Active Directory 동기화를 구성해야 합니다. 자세한 내용은 [Azure AD Connect 관리를 참조하세요.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > 사용하는 AAD Connect 버전은 버전 1.0.9125.0 이상입니다. 이전 버전의 AAD Connect 도구 또는 DirSync를 사용하는 경우 지원되는 버전으로 업그레이드하십시오. 현재 설치를 업그레이드하고 환경에 정의한 사용자 지정 규칙을 유지 관리합니다. 

- **하이브리드 배포 구성** 모든 비즈니스용 Skype 사용자가 현재 온라인 또는 온-프레미스에 있는지 여부 또는 현재 혼합이 있는 경우 비즈니스용 Skype 서버와 [Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)간의 하이브리드 연결 배포에 설명된 따라 비즈니스용 Skype 서버 또는 Lync Server 2013의 하이브리드 배포를 구성하는 단계를 완료해야 합니다. 하이브리드 배포에 대한 자세한 내용은 비즈니스용 Skype 서버와 [Office 365](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)간의 하이브리드 연결 계획을 참조하세요. 

    Lync Server 2013을 사용하는 경우 [Lync Server 2013 하이브리드를 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)

- **(권장) AD FS(Active Directory Federation Services).** Single Sign-On을 지원하기 위해 AD FS를 배포하는 것이 좋습니다. 자세한 내용은 [AD FS(Active Directory Federation Services)를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))

전화 시스템 배포에 대한 자세한 내용은 [Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server을 참조하세요.](enable-users-for-phone-system.md)