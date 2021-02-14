---
title: Microsoft Teams 업그레이드 | 환경 평가, 검색 질문
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 이 지침을 사용하여 Teams로 업그레이드하기 위한 현재 환경을 제대로 평가하기 위한 요구 사항에 대해 알아보면 됩니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3d1349cf32e652cc308bb85c187db90303aa959
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808958"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>검색 설문지 - 환경 평가

다음 표 집합에는 Teams로 업그레이드하기 전에 환경을 평가하는 데 도움이 [되는 질문이 나열되어 있습니다.](upgrade-plan-journey-evaluate-environment.md)

- [Microsoft 365 또는 Office 365 조직 세부 정보](#microsoft-365-or-office-365-organization-details)
- [기존 공동 작업 플랫폼 요약](#existing-collaboration-platform-summary)
- [공동 작업 플랫폼 배포 세부 정보](#collaboration-platform-deployment-details)
- [Microsoft 365 또는 Office 365 서비스에 대한 네트워킹 및 액세스](#networking-and-access-to-microsoft-365-or-office-365-services)
- [엔드포인트](#endpoints)
- [운영](#operations)
- [채택 및 준비](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 또는 Office 365 조직 세부 정보

설문지 작업을 할 때 활성 Microsoft 365 또는 Office 365 조직이 있는 것이 좋습니다. 아직 Microsoft 365 또는 Office 365 조직을 활성화하거나 구성하지 않은 경우 [비즈니스용 Microsoft 365](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)설정 계획을 참조합니다.

다음 표를 사용하여 Microsoft 365 또는 Office 365 조직에 대한 정보를 캡처합니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | 프로덕션 Microsoft 365 또는 Office 365 조직 참고 <br>답변 열의 이름 및 ID <br/>테넌트가 두 개 이상인 경우 <br>조직과 연결된 경우 <br>모든 신원을 참고합니다. | 테넌트 이름: <br/>테넌트 ID:| |
> | 테넌트가 배포된 지역은 무엇입니까?| | |
> | 이러한 테넌트는 Microsoft 365 또는 Office 365 다중 테넌트인가 <br>전용인가요? | <input type="checkbox"> 다중텐트<br/> <input type="checkbox"> 전용 | |
> | 현재 어떤 Microsoft Online 제품이 사용 중입니까? <br/>각각에 대해 활성화된 사용자 수를 확인합니다. <br>서비스에서 설명 열에 표시됩니다. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> 비즈니스용 Skype <br>&nbsp;&nbsp; &nbsp; 온라인 <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> 비즈니스용 OneDrive <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> 기타| |
> | Skype에서 사용할 수 있는 라이선스 수준 <br>Business Online 사용자가신가요? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> 독립 실행형 | 사용자 수 <br>각 SKU에 대해: |
> | 현재 Active Directory 포리스트는 어떻게 됐는가 <br>환경의 기능 수준이 있나요? <br/>포리스트가 두 개 이상 있는 경우 세부 정보를 참조합니다. <br>를 선택해야 합니다. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | 디렉터리에 사용 <br>동기화가 오늘인가요? |<input type="checkbox"> 동기화 없음(클라우드만 해당) <br/> <input type="checkbox"> Azure Active Directory <br>&nbsp;&nbsp; &nbsp; 연결 <br/> <input type="checkbox"> 기타( <br>&nbsp;&nbsp; &nbsp; 주석 열입니다.)| |
> | 페더러드 ID가 현재 배포된가요? <br/>(Active Directory Federation Services 또는 <br>타사) | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 페더러드 ID를 사용하는 경우 <br>페더러리 인프라가 있나요? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> 타사 페더러리 <br>&nbsp;&nbsp; &nbsp; 게이트웨이 <br>&nbsp;&nbsp; &nbsp; (다음의 세부 정보를 참고합니다. <br>&nbsp;&nbsp; &nbsp; 주석 열입니다.) | |
> | 현재 활성 Microsoft 365 또는 Office 365를 유지 관리하는 경우 <br>테넌트는 <br>테넌트와 연결된 대상 사용자인가요? | <input type="checkbox"> N/A – Microsoft 365 또는 Office 365 없음 <br>&nbsp;&nbsp; &nbsp; 테넌트가 있는 경우 <br/> <input type="checkbox"> 아니요, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 도메인이 연결되지 않습니다. <br>&nbsp;&nbsp; &nbsp; 테넌트가 있는 경우 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365 <br/> <input type="checkbox"> 예, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 도메인이 연결됩니다. <br>&nbsp;&nbsp; &nbsp; 기존 테넌트 사용 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365에서 | |
> | 사용자 UPNS가 기본 SMTP 주소와 일치하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 <br/> <input type="checkbox"> 불일치 | |

## <a name="existing-collaboration-platform-summary"></a>기존 공동 작업 플랫폼 요약

다음 표를 사용하여 기존 공동 작업 플랫폼 배포에 대한 정보를 캡처합니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | Microsoft Teams가 배포된가요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 비즈니스용 Skype가 배포된가요? <br/>On-premises 및 hybrid deployments의 경우 <br>버전 및 CU(누적 업데이트)를 적어 두는 경우 <br>세부 정보를 입력합니다. | <input type="checkbox"> 예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox"> 예, 하이브리드(Microsoft 365 또는 Office 365 사용) <br/> <input type="checkbox"> 예, 프레미스 <br/> <input type="checkbox"> 예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> 예, 호스트, 전용 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 예, 호스팅, 공유(타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | Exchange가 배포됐나요? <br/>On-premises 및 hybrid deployments의 경우 <br>메모에 버전 및 CU 세부 정보를 메모합니다. <br>열을 열 수 있습니다. | <input type="checkbox"> 예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox"> 예, 하이브리드(Microsoft 365 또는 Office 365 사용) <br/> <input type="checkbox"> 예, 프레미스 <br/> <input type="checkbox"> 예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> 예, 호스트, 전용 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 예, 호스트, 공유 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | SharePoint가 배포됐나요? <br/>On-premises 및 hybrid deployments의 경우 <br>메모에 버전 및 CU 세부 정보를 메모합니다. <br>열을 열 수 있습니다. | <input type="checkbox"> 예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox"> 예, 하이브리드(Microsoft 365 또는 Office 365 사용) <br/> <input type="checkbox"> 예, 프레미스 <br/> <input type="checkbox"> 예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> 예, 호스트, 전용 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 예, 호스트, 공유 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | Microsoft 365 또는 비즈니스용 Office 365 OneDrive가 배포된가요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 다른 타사 플랫폼이 배포된 경우 <br>오늘 사용 중이신가요? 이 경우 <br>이러한 플랫폼 및 설명의 사용 세부 정보 <br>열을 열 수 있습니다. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> 기타(주석에 지정) <br>&nbsp;&nbsp; &nbsp; 열)을 열에 추가합니다. | 사용자 수: <br/>세부 정보:|
> | 이러한 타사에서 사용자를 이동할 계획인가 <br>플랫폼에서 Teams로? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 전화 통신 및 회의 솔루션 <br>이 이니셔티브의 범위에 있는 사용자 중 누구인가요? | | |
> | 이 이니셔티브 범위에 있는 사무실에 배포된 직접 라우팅을 지원하는 [SBC가](direct-routing-plan.md#supported-session-border-controllers-sbcs) 있나요? <br>예인 경우 메모 열의 세부 정보를 메모합니다.| <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||

## <a name="collaboration-platform-deployment-details"></a>공동 작업 플랫폼 배포 세부 정보

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 Teams 배포의 세부 정보를 캡처합니다. Teams를 배포하지 않은 경우 이 섹션을 건너뜁니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | Teams에 사용할 수 있는 사용자 유형은 무엇입니까? | <input type="checkbox"> 조직의 모든 사용자 <br/> <input type="checkbox"> 특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; &nbsp; (설명 열에 지정) ||
> | 어떤 Teams 기능 및 부호가 사용 중입니까? | <input type="checkbox"> 채널 기반 대화 <br/> <input type="checkbox"> 비공개 채팅 <br/> <input type="checkbox"> 게스트 액세스 <br/> <input type="checkbox"> 채널 모임 <br/> <input type="checkbox"> 비공개 모임 <br/> <input type="checkbox"> 비공개 통화 <br/> <input type="checkbox"> 애드워크 채널 meetup <br/> <input type="checkbox"> 모임의 비디오 <br/> <input type="checkbox"> 모임에서 화면 공유 <br/> <input type="checkbox"> 오디오 회의 <br/><input type="checkbox"> 애플리케이션(앱)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> 탭<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 봇 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 커넥터<br><input type="checkbox"> 사용자 지정 클라우드 저장소 통합 <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google Drive, Egnyte <br/> <input type="checkbox"> 채널 전자 메일 통합 <br/> <input type="checkbox"> 기타(주석 열에 지정) | |
> | Teams에 배포한 애플리케이션은 무엇입니까? | | |
> | Teams 기능을 특별히 차단한 경우 <br/>예인 경우 메모 열의 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||
> | 어떤 Teams 클라이언트를 사용하나요? | <input type="checkbox"> 웹 <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | 누가 팀을 만들 수 있는 권한이 있나요? | <input type="checkbox"> 조직의 모든 사용자 <br>&nbsp;&nbsp; &nbsp; (기본 설정입니다.) <br/> <input type="checkbox"> 특정 사용자 <br>&nbsp;&nbsp; &nbsp; (설명 열에서 지정합니다.) | |
> | Teams에서 보안 및 규정 준수 기능을 사용하고 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |

### <a name="skype-for-business-online-if-applicable"></a>비즈니스용 Skype Online(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 비즈니스용 Skype Online 배포의 세부 정보를 캡처합니다. 비즈니스용 Skype Online 배포를 배포하지 않은 경우 이 섹션을 건너뜁니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | Skype에서 사용할 수 있는 사용자 유형 <br>비즈니스용 Online? | <input type="checkbox"> 조직의 모든 사용자 <br/> <input type="checkbox"> 특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; &nbsp; (설명 열에 지정) | |
> | 현재 어떤 부호 및 기능 <br>현재 사용 중이신가요? | <input type="checkbox"> 메신저 및 현재 상태(IM/P)<br/> <input type="checkbox"> 모임 <br/> <input type="checkbox"> 페더ation <br/> <input type="checkbox"> 모임 녹음/녹화 <br/> <input type="checkbox"> Microsoft 오디오 회의 <br/> <input type="checkbox"> 타사 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보를 참고합니다.) <br/> <input type="checkbox"> 통화 계획(이전의 PSTN 통화) <br/> <input type="checkbox"> 조직 자동 참석자 <br/> <input type="checkbox"> 호출 큐 | |
> | Skype를 특별히 차단한 경우 <br>Business Online 기능이 있나요? <br>예인 경우 메모 열의 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 사용 방법 또는 사용 계획 <br>전화 시스템(이전의 클라우드 PBX)을 <br>PSTN? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> 통화 계획(이전의 PSTN 통화) <br/> <input type="checkbox"> 기존 연결 활용(기존 PSTN 사용) <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype 2015 또는 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 배포) <br/> <input type="checkbox"> 클라우드 커넥터를 사용하여 프레미스 PSTN 연결 | |
> | 전화 번호를 Microsoft로 포식하고 있나요? <br/>통화 요금제 및 오디오에 적용할 수 있습니다. <br>회의 기능입니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>비즈니스용 Skype-프레미스(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 비즈니스용 Skype 배포의 세부 정보를 캡처합니다. 비즈니스용 Skype를 배포하지 않은 경우 이 섹션을 건너뜁니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | 현재 Lync 또는 비즈니스용 Skype 버전 <br>배포되어 있나요? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> 비즈니스용 Skype Server 2015 <br/> <input type="checkbox"> 비즈니스용 Skype Server 2019 <br/> <input type="checkbox"> 비즈니스용 Skype Cloud Connector Edition | |
> | 비즈니스용 Skype Online과의 하이브리드가 구성되어 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 이 환경은 타사에서 호스팅 및 관리하나요? <br/>예인 경우 메모 열의 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 사용 중인 모달 및 기능 <br>오늘인가요? | <input type="checkbox"> 메신저 및 현재 상태(IM/P) <br/> <input type="checkbox"> 모임 <br/> <input type="checkbox"> 페더ation <br/> <input type="checkbox"> 모임 녹음/녹화 <br/> <input type="checkbox"> 영구 채팅/그룹 채팅 <br/> <input type="checkbox"> Microsoft 오디오 회의 <br>&nbsp;(이전의 회의 전화 &nbsp; &nbsp; 접속) <br>&nbsp;&nbsp; &nbsp; 온-프레미스 Lync Server 또는 <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype 배포 <br/> <input type="checkbox"> 타사 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보 참고) <br/> <input type="checkbox"> Enterprise Voice PSTN 사용 <br>&nbsp;&nbsp; &nbsp; 연결 <br/> <input type="checkbox"> 다음을 통해 플랜(이전의 PSTN 통화) <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype Online과 하이브리드 | |
> | 어떤 버전의 Edge Server를 배포하나요? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> 비즈니스용 Skype Server 2015 <br/> <input type="checkbox"> 비즈니스용 Skype Server 2019 | |
> | Lync 또는 비즈니스용 Skype Edge가 배포된 경우 <br>두 개 이상의 데이터 센터로? <br/>예인 경우 메모 열의 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | Edge 역할이 현재 제공하는 서비스를 선택합니다. | <input type="checkbox"> 외부 사용자 액세스(회사 사용자) <br/> <input type="checkbox"> 원격 사용자 액세스(익명 외부) <br>&nbsp;&nbsp; &nbsp; 모임 참가자) <br/> <input type="checkbox"> 페더ation <br/> <input type="checkbox"> 미디어 릴레이 | |
> | 다음 음성 통화 기능 중 어떤 기능을 사용할 수 있습니다. <br>현재 종속성은 있나요? <br/>메모에 추가 종속성 참고 <br>열을 열 수 있습니다. | <input type="checkbox"> 사용 중 옵션 <br/> <input type="checkbox"> 호출 공원 <br/> <input type="checkbox"> 통화 픽업 또는 그룹 통화 픽업 <br/> <input type="checkbox"> 일반 지역 전화 또는 "핫 데스크" <br/> <input type="checkbox"> 응답 그룹 또는 헌트 그룹 <br/> <input type="checkbox"> 공유 선 모양 <br/> <input type="checkbox"> 비공개 줄 <br/> <input type="checkbox"> 음성메일 <br/> <input type="checkbox"> 업무를 통해 통화 <br/> <input type="checkbox"> 긴급 또는 정보 번호 <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> 확장 전화 걸기 <br/> <input type="checkbox"> 자동 전화 교환 <br/> <input type="checkbox"> 구독자 액세스 <br/> <input type="checkbox"> 아날로그 디바이스 <br/> <input type="checkbox"> 팩스 <br/> <input type="checkbox"> 호출자 ID 마스킹 또는 변경 <br/> <input type="checkbox"> 위치 기반 라우팅 <br/> <input type="checkbox"> 최소 비용 라우팅 <br/> <input type="checkbox"> 엘리베이터 전화 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Microsoft 365 또는 Office 365 서비스에 대한 네트워킹 및 액세스

다음 표를 사용하여 조직의 네트워킹 세부 정보 및 사용자가 Microsoft 365 또는 Office 365 서비스에 연결되는 방식(또는)을 캡처합니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | 마이그레이션 범위에 있는 사용자를 어떻게(또는 어떻게) 마이그레이션할 수 있습니다. <br>사무실에 있는 경우 Teams에 액세스하나요? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> 라우팅된 NAT 연결 <br/> <input type="checkbox"> 프록시 서버 <br/> <input type="checkbox"> 공용 Wi-Fi <br/> <input type="checkbox"> 관리되는(공용이 아닌) Wi-Fi <br/> <input type="checkbox"> ExpressRoute(Microsoft 피어링) ||
> | Microsoft 365 또는 Office 365에 대한 액세스가 프록시 서버를 통해 진행되는 경우 <br>프록시를 무시하는 방법은 무엇입니까? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 ExpressRoute가 사용되고 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 <br/> <input type="checkbox"> 아니요, 하지만 계획 중입니다. | |
> | 네트워크 준비 평가를 수행한 경우 | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 연결할 때 사용자가 VPN을 사용하는 데 필요한가 <br>회사 리소스를 원격으로 사용하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | VPN을 사용하는 경우 Teams 트래픽을 제외할 수 있습니다. <br>Microsoft 365 또는 Office 365 서비스에 직접 액세스하기 위한 VPN이 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 네트워크에서 QoS를 지원하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | Teams 오디오 및 비디오 트래픽의 우선 순위를 지정할 수 있습니다. <br>고품질 환경을 구동할 수 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 지역 내의 모든 위치가 인터넷을 통해 <br>또는 전체 지역에 대해 중앙 집중식으로 인터넷을 내보나요? | <input type="checkbox"> 인터넷에 대한 국가별 액세스 <br/> <input type="checkbox"> 인터넷에 대한 중앙 집중식 액세스 | |

## <a name="endpoints"></a>엔드포인트

다음 표를 사용하여 사용 중 클라이언트 및 엔드포인트의 세부 정보를 캡처합니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | 사용자가 사용하는 데스크톱 OS는 무엇입니까? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac(설명 열에서 버전을 지정합니다.) <br/> <input type="checkbox"> Linux(주석 열에서 배포를 지정합니다.) <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 참고합니다.) | |
> | 배포된 Microsoft Office 버전 <br>이러한 디바이스에? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office for Mac 2011 <br/> <input type="checkbox"> Office for Mac 2016 <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 참고합니다.) | |
> | 사용 중 Office 배포 기술 <br>조직에 있나요? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Click-to-Run | |
> | 허용되는 모바일 및 지원되는 모바일은 어떻게 받나 <br>플랫폼을 사용 중입니까? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> Windows <br/> <input type="checkbox"> 모바일 <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 참고합니다.) | |
> | 모바일 디바이스는 어떻게 제공하나요? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> 회사 디바이스 <br/> <input type="checkbox"> 사용자 디바이스 가져오기 | |
> | 사용자가 현재 액세스하는 데 사용하는 디바이스 <br>음성 및 회의 서비스 <br>(휴대폰, 헤드셋, 휴대폰, 비디오)? | | |

## <a name="operations"></a>운영

다음 표를 사용하여 환경의 운영 측면에 대한 세부 정보를 캡처합니다.

> | 질문 | 답변 | 설명 |
> |---|---|---|
> | Lync Server의 운영 모델 <br>비즈니스용 Skype Server, Microsoft 365 또는 Office 365 배포 <br>오늘인가요? | | |
> | 현재 지원 정렬을 간략하게 설명할 수 있습니다. <br>Lync Server, 비즈니스용 Skype Server, Microsoft 365 또는 Office 365? | | |
> | 여러 국가 또는 지역에 배포하는 경우 <br>각 국가/지역에 자체 IT/전화 통신이 있는가 <br>직원과 함께 일할 예정인가요? 아니면 중앙에서 관리될까요? | <input type="checkbox"> 지역 운영 및 지원 <br/> <input type="checkbox"> 중앙 집중식 작업 및 지원 | |
> | 통화 품질 [방법론을 따라가시나요?](quality-of-experience-review-guide.md) | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 개인 또는 팀을 <br>공동 작업 플랫폼에 대한 품질 챔피언 역할 <br>사용 중입니까? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||
> | Lync Server, Skype for를 모니터링하는 방법 <br>Business Server, Microsoft 365 또는 Office 365 배포 | | |
> | 통화 품질 문제가 있나요? | <input type="checkbox"> 예<br/> <input type="checkbox"> 아니요 | |
> | 교육을 제공하는 방법 및 언제 <br>새 서비스 및 기능에 대한 기술 지원 서비스가 있나요? | | |

## <a name="adoption-and-readiness"></a>채택 및 준비

다음 표를 사용하여 조직의 현재 채택 및 준비 상태를 캡처합니다.

>
> | 질문 | 답변 | 설명 |
> |---|---|---|
> | 현재 활성 사용 현황은 어떻게 됐는가 <br>비즈니스용 Skype? | **__** 총 활성 사용자 수와 활성화된 사용자 수의 %입니다. | |
> | 조직에서 사용하는 방법 <br>비즈니스용 Skype? | 1:1 대화 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 통화 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br> 모임 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 회의<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 통화 | |
> | 조직에 사용자 채택이 있는가 <br>및 변경 관리 팀이 있나요? | <input type="checkbox"> 예<br/> <input type="checkbox"> 아니요 | |
> | 현재 기술의 성공을 측정하는 방법 <br>비즈니스용 Skype와 같은 롤아웃인가요? | | |
> | 사용자 기반의 백분율입니다. <br>채택된 비즈니스용 Skype? | | |
> | 비즈니스용 Skype에 대한 사용자 감정은 무엇입니까? | <input type="checkbox"> 좋음 <br/> <input type="checkbox"> 중립 <br/> <input type="checkbox"> Bad | |
> | 다음 중 롤아웃을 가장 잘 설명하는 항목 <br>비즈니스용 Skype에 사용되는 전략 <br>배포 중이신가요? | <input type="checkbox"> 광범위한 범위: <br>&nbsp;&nbsp; &nbsp; 교육 링크 <br/> <input type="checkbox"> 확장: 광범위한 도달 범위 및 다양한 범위 <br>&nbsp;&nbsp; &nbsp; 인식 캠페인(포스터, <br>&nbsp;&nbsp; &nbsp; 이벤트, 챔피언) 및 교육 <br>&nbsp;&nbsp; &nbsp; (비디오, 사용자 가이드, 대면) <br/> <input type="checkbox"> 맞춤화: 확장 및 대상 지정 <br>&nbsp;&nbsp; &nbsp; 사용자에 의해 메시징 및 교육 <br/> <input type="checkbox"> 기타 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보를 참고합니다.) | |


