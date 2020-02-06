---
title: 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 Office 365의 전화 시스템 계획
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
description: 온-프레미스 PSTN 연결을 사용 하는 클라우드 PBX (Office 365)에서 전화 시스템의 계획 고려 사항에 대해 알아봅니다.
ms.openlocfilehash: a134b4dbe48d302ee8be8df528e6bbebac336b8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814486"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 Office 365의 전화 시스템 계획

온-프레미스 PSTN 연결을 사용 하는 클라우드 PBX (Office 365)에서 전화 시스템의 계획 고려 사항에 대해 알아봅니다.

이 콘텐츠는 온-프레미스 비즈니스용 Skype Server 또는 Lync Server 2013을 이미 사용 중인 경우에 적합 합니다. 다른 시나리오는 [Microsoft 전화 통신 솔루션](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)을 참조 하세요.

 온-프레미스 PSTN 연결을 사용 하는 Office 365의 전화 시스템을 사용 하면 사용자에 게 클라우드 PBX (전화 시스템) 기능을 활용할 수 있습니다. 이렇게 하면 다음과 같은 시나리오에 도움이 될 수 있습니다.

- 비즈니스용 skype 사용자 중 일부는 비즈니스용 Skype Online에 홈으로 표시 되어 있습니다. 이제 비즈니스용 Skype Online에 있는 사용자의 Office 365 기능 및 기능을 사용 하도록 설정할 수 있지만, 계속 해 서 온-프레미스 PSTN 연결을 사용 합니다.

- 온-프레미스 배포로 사용자의 일부 또는 전체를 비즈니스용 Skype Online으로 이동 하 되, 계속 해 서 온-프레미스 PSTN 연결을 사용 하려는 경우

    > [!IMPORTANT]
    > Office 365에서 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템용 사용자를 활성화 하려면 해당 SIP 주소가 자신의 도메인에 있어야 합니다. Office 365, onmicrosoft.com에 대 한 기본 도메인 사용이 지원 되지 않습니다. 

라이선스 및 계획을 포함 하 여 Office 365의 전화 시스템에 대 한 자세한 내용은 [비즈니스용 Skype의 PSTN 통화 요금제](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)를 참조 하세요.

## <a name="feature-comparison"></a>기능 비교

온-프레미스 PSTN 연결을 사용 하는 클라우드 PBX는 완전히 온-프레미스 엔터프라이즈 음성 솔루션과 동일한 기능 집합을 제공 하지 않습니다. 온-프레미스 PSTN 연결을 사용 하는 클라우드 PBX가 조직에 적합 한 기능 집합을 제공 하는지 여부를 결정 하는 데 도움이 되도록 [클라우드 pbx를 통해 얻을 수 있는 작업](https://go.microsoft.com/fwlink/?LinkId=715517)을 참조 하세요.

## <a name="benefits-and-planning-considerations"></a>이점 및 계획 고려 사항

> [!CAUTION]
> Lync Phone Edition 장치는 비즈니스용 Skype Online으로 이동 하기 전에 온-프레미스 환경에서 필요한 최소 펌웨어로 업데이트 해야 합니다.
펌웨어를 업데이트 하기 전에 온-프레미스에서 온라인으로 사용자를 이동 하면 사용자가 전화를 사용 하 여 연결할 수 없게 됩니다. 이 문제를 해결 하려면 사용자가 온-프레미스 환경으로 다시 이동 하 여 전화기를 최소 펌웨어로 업데이트 해야 합니다. 사용자를 다시 온-프레미스 환경으로 이동 하기 전에 최소한의 펌웨어로 업데이트 하거나 전화를 다시 초기화 하지 마세요.
장치가 최소 펌웨어가 아닌 동안 하드 리셋을 수행 하는 경우 기본적으로 비즈니스용 Skype Online에서 지원 되지 않는 PIN 인증을 사용 하는 것입니다. 자세한 내용은 [비즈니스용 Skype Online 용 전화 받기](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)를 참조 하세요.

Office 365에서 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템을 배포 하면 사용자는 온-프레미스 PSTN 연결을 유지 하면서 비즈니스용 Skype Online을 통해 자신의 속도로 클라우드로 이동할 수 있습니다. PBX가 있는 경우이를 계속 사용 하 여 클라우드로 이동 하는 사용자에 게 PSTN 연결을 제공 합니다. Office 365에서 사용자가 비즈니스용 Skype Online 및 전화 시스템으로 이동한 후에는 해당 레거시 PBX 전화기가 더 이상 작동 하지 않지만 해당 전화 번호는 Pc 또는 스마트 휴대폰용 비즈니스용 Skype 클라이언트와 비즈니스용 skype 규격의 일반 전화기로 라우팅됩니다. server 일단 이식 하면 Office 365 사용자와 레거시 PBX 사용자의 전화 시스템이 서로 일반 전화 번호를 사용 하 여 PSTN 전화를 걸거나 받을 수 있습니다.

통화 센터와 같이 레거시 PBX에 대 한 사용자 지정 기능이 나 주요 추가 기능을 사용할 수 있습니다. 현재 Office 365의 전화 시스템에서 사용자 지정 기능을 사용할 수 없는 경우 해당 사용자 지정 기능을 레거시 PBX와 함께 온 상태로 유지 하 고 Office 365에서 사용자 지정 기능에 액세스할 필요가 없는 사용자를 이식 하는 것이 좋습니다. 온-프레미스 PSTN 연결을 사용 합니다.

비즈니스용 Skype 2015 서버와 직접 상호 작용 하는 레거시 Pbx 목록은 [Microsoft Lync의 인프라 자격](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)을 참조 하세요. PBX가이 목록에 없는 경우에는 세션 경계 컨트롤러를 사용 하 여 비즈니스용 Skype Online에서 Office 365의 휴대폰 시스템에 PBX를 연결할 수 있습니다.

### <a name="network-considerations-for-quality-and-performance"></a>품질 및 성능에 대 한 네트워크 고려 사항

온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템 같은 클라우드 호스팅 서비스를 배포 하는 경우 다음 사항을 염두에 두어야 합니다. 순수한 온-프레미스 비즈니스용 Skype 서버 2015 엔터프라이즈 음성 배포에서는 모든 인프라 및 클라이언트가 엔터프라이즈의 자체 네트워크에 있습니다. 고품질 오디오 및 비디오에 중요 한이 네트워크의 품질과 성능은 엔터프라이즈 직원의 직접적인 제어를 대상으로 합니다. Office 365에서 온-프레미스 PSTN 연결을 사용 하는 경우에는 세 가지 네트워크 (예: 기업 직원이 직접 제어 하는 다음 중 한 가지)가 포함 됩니다.

- **Microsoft의 글로벌 미디어 배달 네트워크** Microsoft의 글로벌 클라우드 네트워크 및 인프라. Office 365 서버와 트래픽에 있는 office 365 및 전화 시스템은이 네트워크를 통과 합니다.

- **엔터프라이즈/클라우드 PSTN 상호** 연결 엔터프라이즈를 Office 365 클라우드에 연결 하는 네트워크입니다. 이는 일반 인터넷 연결과 다를 수도 있습니다.

- **기업의 자체 네트워크** 실시간 미디어의 품질은 특히 WiFi 네트워크와 Office 365 클라우드에 도달 하는 데 사용 되는 interconnect의 품질에 의존 합니다.

> [!NOTE]
> 비즈니스용 Skype Online의 성능 조정에 대 한 자세한 내용은 비즈니스용 [Skype online 성능을 조정](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)을 참조 하세요. 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>온-프레미스 PSTN 연결을 사용 하는 Office 365에서 전화 시스템을 사용 하기 위한 필수 구성 요소

온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템을 구성 하 고 사용자를 비즈니스용 Skype Online으로 이동 하려면 먼저 다음 필수 구성 요소가 있는지 확인 해야 합니다.

 **온-프레미스 서버 버전.** 온-프레미스 배포의 서버 버전은 온-프레미스 PSTN 연결을 사용 하는 Office 365의 전화 시스템을 지원 하기 위해 다음 표에 나열 되어야 합니다.


| **서버 역할**                                       | **지원 되는 버전\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 페더레이션 가장자리\*\*  <br/>                            | 비즈니스용 Skype 서버 2015  <br/>                                                                              |
| 다음 홉 페더레이션 경로 내부 풀 서버  <br/> | 비즈니스용 Skype 서버 2015, 2016 6.0.9319.235 누적 업데이트 (프론트 엔드 또는 디렉터)  <br/> |
| 프런트 엔드 사용자 서버  <br/>                          | 비즈니스용 Skype 서버 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge 서버  <br/>                                    | 비즈니스용 Skype 서버 2015  <br/>                                                                              |
| 중재 서버  <br/>                               | 비즈니스용 Skype 서버 2015  <br/> Lync Server 2013  <br/>                                                      |

\*지원 되는 최소 버전:

- 비즈니스용 Skype 서버 2015, 2016 3 월 누적 업데이트 6.0.9319.235

- Lync Server 2013 7 월 2015 누적 업데이트 5.0.8308.920

\*\*지원 되는 모든 SIP 도메인의 페더레이션 경로는 3 월 2016 이상 누적 업데이트를 실행 하는 비즈니스용 Skype Server 2015 Edge 서버를 통해 경로를 만들어야 합니다. 사용자 풀이 Lync Server 2013에 있는 경우 해당 외부 풀 트래픽은 Lync Server 2013 Edge 서버에 남아 있습니다. 

또한 다음을 확인 해야 합니다.

- 온 **-프레미스 Enterprise Voice는 온-프레미스 사용자를 구성 하 고 테스트 합니다** . 여기에는 PSTN 연결 구성 요소가 포함 됩니다. 자세한 내용은 비즈니스용 Skype 서버 2015을 사용 중인 경우 다음 항목을 참조 하세요. 비즈니스용 skype server [2015의 Enterprise Voice 요금제](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 를 참조 하 고 [비즈니스용 skype 서버 2015에서 Enterprise](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)voice를 배포 합니다.

    Lync Server 2013을 사용 하는 경우 lync [server 2013의 Enterprise Voice 계획](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) 을 참조 하 고 [lync Server 2013에서 Enterprise voice를 배포](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)합니다.

- **Active Directory 동기화** Azure AD Connect를 사용 하 여 Active Directory 동기화를 구성 해야 합니다. 자세한 내용은 [AZURE AD Connect 관리](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)를 참조 하세요.

    > [!NOTE]
    > 사용 하는 AAD Connect 버전은 버전 1.0.9125.0 이상 이어야 합니다. 이전 버전의 AAD Connect 도구 또는 DirSync을 사용 하는 경우 지원 되는 버전으로 업그레이드 하세요. 현재 설치를 업그레이드 하 고 환경에 정의한 사용자 지정 규칙을 유지 관리할 수 있습니다. 

- **하이브리드 배포 구성** 현재 모든 비즈니스용 Skype 사용자가 온라인 또는 온-프레미스에 연결 되어 있는지 여부 또는 현재 mix가 있는 경우 비즈니스용 skype [서버와 Office 365의 하이브리드 연결 배포](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)에 명시 된 대로 비즈니스용 skype Server 또는 Lync server 2013의 하이브리드 배포를 구성 하는 단계를 완료 해야 합니다. 하이브리드 배포에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Office 365 하이브리드 연결 계획](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)을 참조 하세요. 

    Lync Server 2013를 사용 하는 경우 [Lync server 2013 하이브리드](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)을 참조 하세요.

- **권장 AD FS (Active Directory Federation Services)** Single Sign-on을 지원 하기 위해 AD FS를 배포 하는 것이 좋습니다. 자세한 내용은 [AD FS (Active Directory Federation Services)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)를 참조 하세요.

Office 365에서 전화 시스템을 배포 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 office 365에서 전화 시스템 사용자 사용](enable-users-for-phone-system.md)을 참조 하세요.


