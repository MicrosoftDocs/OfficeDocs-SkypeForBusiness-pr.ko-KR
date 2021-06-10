---
title: Microsoft Teams 업그레이드 | 환경 평가, 검색 질문
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 이 지침을 사용하여 현재 환경으로 업그레이드하기 위한 현재 환경을 올바르게 평가하기 위한 요구 사항에 대해 Teams.
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

다음 표 집합에는 다음 테이블로 업그레이드하기 전에 환경을 평가하는 데 도움이 되는 [질문이 Teams.](upgrade-plan-journey-evaluate-environment.md)

- [Microsoft 365 또는 Office 365 세부 정보](#microsoft-365-or-office-365-organization-details)
- [기존 공동 작업 플랫폼 요약](#existing-collaboration-platform-summary)
- [공동 작업 플랫폼 배포 세부 정보](#collaboration-platform-deployment-details)
- [네트워크 및 Microsoft 365 또는 Office 365 액세스](#networking-and-access-to-microsoft-365-or-office-365-services)
- [엔드포인트](#endpoints)
- [작업](#operations)
- [채택 및 준비](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 또는 Office 365 세부 정보

설문지에서 작업할 때 조직에 Microsoft 365 Office 365 조직이 있는 것이 좋습니다. 아직 조직을 활성화하거나 구성하지 않은 Microsoft 365 Office 365 비즈니스용 Microsoft 365 [를 참조합니다.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

다음 표를 사용하여 조직 또는 조직에 대한 Microsoft 365 Office 365 있습니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 프로덕션 Microsoft 365 또는 Office 365 참고 <br>답변 열의 이름 및 ID <br/>테넌트가 두 개 이상 있는 경우 <br>조직과 연결됩니다. <br>모든 신분을 유의합니다. | 테넌트 이름: <br/>테넌트 ID:| |
> | 테넌트가 배포되는 지역에는 어떤 지역이 있나요?| | |
> | 이러한 테넌트가 Microsoft 365 Office 365 또는 <br>전용? | <input type="checkbox"> 다중텐트<br/> <input type="checkbox"> 전용 | |
> | 현재 어떤 Microsoft Online 제품이 사용 중입니까? <br/>각 사용자에 대해 사용하도록 설정된 사용자 수를 확인합니다. <br>는 주석 열에서 서비스를 제공합니다. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">비즈니스용 Skype <br>&nbsp;&nbsp; &nbsp; 온라인 <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint 온라인 <br/> <input type="checkbox">비즈니스용 OneDrive <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> 기타| |
> | 사용 가능한 라이선스 수준은 Skype <br>Business Online 사용자? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> 독립 실행형 | 사용자 수 <br>각 SKU에 대해: |
> | 현재 Active Directory 포리스트는 무엇일지 <br>환경의 기능 수준? <br/>포리스트가 두 개 이상 있는 경우 세부 정보를 참고합니다. <br>주석 열에 있습니다. | <input type="checkbox">Windows 서버 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows 서버 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 디렉터리에 사용 중 <br>오늘 동기화? |<input type="checkbox"> 동기화 없음(클라우드만 해당) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp; 커넥트 <br/> <input type="checkbox"> 기타(에서 지정 <br>&nbsp;&nbsp; &nbsp; 주석 열.)| |
> | 페더러드 ID가 현재 배포된가요? <br/>(Active Directory Federation Services 또는 <br>타사) | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 페더리드 ID를 사용하는 경우 <br>페더전 인프라? | <input type="checkbox">Windows R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> 타사 페더전 <br>&nbsp;&nbsp; &nbsp; Gateway <br>&nbsp;&nbsp; &nbsp; (의 세부 정보를 참고합니다. <br>&nbsp;&nbsp; &nbsp; 주석 열.) | |
> | 현재 활성 Microsoft 365 또는 Office 365 <br>테넌트의 SMTP/SIP 도메인입니다. <br>테넌트와 연결된 대상 사용자? | <input type="checkbox">N/A – Microsoft 365 Office 365 <br>&nbsp;&nbsp; &nbsp; 테넌트가 있는 경우 <br/> <input type="checkbox"> 아니요, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 도메인이 연결되지 않습니다. <br>&nbsp;&nbsp; &nbsp; 테넌트가 있는 경우 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365 <br/> <input type="checkbox"> 예, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 도메인이 연결됩니다. <br>&nbsp;&nbsp; &nbsp; 기존 테넌트와 함께 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365 | |
> | 사용자 UPNS가 기본 SMTP 주소와 일치하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 <br/> <input type="checkbox"> 불일치 | |

## <a name="existing-collaboration-platform-summary"></a>기존 공동 작업 플랫폼 요약

다음 표를 사용하여 기존 공동 작업 플랫폼 배포에 대한 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 배포 Microsoft Teams? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 배포 비즈니스용 Skype? <br/>프레미스 및 하이브리드 배포의 경우 <br>CU(버전 및 누적 업데이트)를 참고합니다. <br>자세한 내용은 주석 열에 있습니다. | <input type="checkbox">예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 하이브리드(Microsoft 365 또는 Office 365) <br/> <input type="checkbox"> 예, 프레미스 <br/> <input type="checkbox"> 예, 온라인 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> 예, 호스팅, 전용 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 예, 호스팅, 공유(타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | 배포 Exchange? <br/>프레미스 및 하이브리드 배포의 경우 <br>메모에서 버전 및 CU 세부 정보를 참고합니다. <br>열. | <input type="checkbox">예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 하이브리드(Microsoft 365 또는 Office 365) <br/> <input type="checkbox"> 예, 프레미스 <br/> <input type="checkbox"> 예, 온라인 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> 예, 호스팅, 전용 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 예, 호스트, 공유 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | 배포 SharePoint? <br/>프레미스 및 하이브리드 배포의 경우 <br>메모에서 버전 및 CU 세부 정보를 참고합니다. <br>열. | <input type="checkbox">예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 하이브리드(Microsoft 365 또는 Office 365) <br/> <input type="checkbox"> 예, 프레미스 <br/> <input type="checkbox"> 예, 온라인 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> 예, 호스팅, 전용 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 예, 호스트, 공유 <br>&nbsp;&nbsp; &nbsp; (타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | 배포 Microsoft 365 또는 Office 365 비즈니스용 OneDrive? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 다른 타사 플랫폼이 배포된 경우 <br>오늘 사용 중이신가요? 이 경우 해당 사용자 수를 <br>이러한 플랫폼 및 주석의 사용 세부 정보 <br>열. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> 기타(주석에서 지정) <br>&nbsp;&nbsp; &nbsp; column.) | 사용자 수: <br/>세부 정보:|
> | 이러한 타사에서 사용자를 이동할 계획인가 <br>플랫폼을 Teams? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 전화 통신 및 회의 솔루션란 <br>이니셔티브의 범위에 있는 사용자의 경우 | | |
> | 이니셔티브의 범위에 있는 Office에 배포된 직접 라우팅을 지원하는 [SBC가](direct-routing-plan.md#supported-session-border-controllers-sbcs) 있나요? <br>예인 경우 메모 열에 세부 정보를 메모합니다.| <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||

## <a name="collaboration-platform-deployment-details"></a>공동 작업 플랫폼 배포 세부 정보

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 Teams 배포의 세부 정보를 캡처합니다. 배포하지 않은 Teams 이 섹션을 건너뜁니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 사용자에 대해 사용할 수 있는 사용자 유형은 Teams? | <input type="checkbox"> 조직의 모든 사용자 <br/> <input type="checkbox"> 특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; &nbsp; (주석 열에 지정) ||
> | 어떤 Teams 및 모달을 사용하나요? | <input type="checkbox"> 채널 기반 대화 <br/> <input type="checkbox"> 비공개 채팅 <br/> <input type="checkbox"> 게스트 액세스 <br/> <input type="checkbox"> 채널 모임 <br/> <input type="checkbox"> 비공개 모임 <br/> <input type="checkbox"> 개인 통화 <br/> <input type="checkbox"> Ad-Hoc 채널 미트업 <br/> <input type="checkbox"> 모임의 비디오 <br/> <input type="checkbox"> 모임에서 화면 공유 <br/> <input type="checkbox"> 오디오 회의 <br/><input type="checkbox"> 애플리케이션(앱)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> 탭<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 봇 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 커넥터<br><input type="checkbox"> 사용자 지정 클라우드 저장소 통합 <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google 드라이브, Egnyte <br/> <input type="checkbox"> 채널 전자 메일 통합 <br/> <input type="checkbox"> 기타(주석 열에 지정합니다.) | |
> | 어떤 애플리케이션을 배포한 Teams? | | |
> | 특정 기능을 차단한 Teams 있나요? <br/>예인 경우 메모 열에 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||
> | 사용 Teams 클라이언트는 무엇입니까? | <input type="checkbox"> 웹 <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows 모바일 | |
> | Who 팀을 만들 수 있는 권한이 있나요? | <input type="checkbox"> 조직의 모든 사용자 <br>&nbsp;&nbsp; &nbsp; (기본 설정입니다. <br/> <input type="checkbox"> 특정 사용자 <br>&nbsp;&nbsp; &nbsp; (주석 열에서 지정합니다.) | |
> | 보안 및 규정 준수 기능을 Teams. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |

### <a name="skype-for-business-online-if-applicable"></a>비즈니스용 Skype 온라인(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 비즈니스용 Skype 온라인 배포의 세부 정보를 캡처합니다. 온라인 배포를 배포하지 않은 비즈니스용 Skype 이 섹션을 건너뜁니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 사용 가능한 사용자 유형은 Skype <br>Business Online용? | <input type="checkbox"> 조직의 모든 사용자 <br/> <input type="checkbox"> 특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; &nbsp; (주석 열에 지정) | |
> | 현재 어떤 모달 및 기능 <br>오늘 사용 중이신가요? | <input type="checkbox"> 메신저 및 현재 상태(IM/P)<br/> <input type="checkbox"> 모임 <br/> <input type="checkbox"> 페더전 <br/> <input type="checkbox"> 모임 녹음 <br/> <input type="checkbox"> Microsoft 오디오 회의 <br/> <input type="checkbox"> 타사 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보를 참고합니다.) <br/> <input type="checkbox"> 통화 계획(이전 PSTN 호출) <br/> <input type="checkbox"> 조직 자동 참석자 <br/> <input type="checkbox"> 큐 호출 | |
> | 에 대한 모든 Skype 차단한 경우 <br>Business Online 기능? <br>예인 경우 메모 열에 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 사용 중 또는 사용 계획 <br>전화 시스템(이전 클라우드 PBX)에 연결 <br>PSTN? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> 통화 계획(이전 PSTN 호출) <br/> <input type="checkbox"> 온-프레미스 PSTN 연결(기존 활용) <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype 2015 또는 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 배포) <br/> <input type="checkbox"> 프레미스 PSTN 연결(클라우드 커넥터 사용) | |
> | Microsoft에 전화 번호를 이식한 적 있나요? <br/>통화 계획 및 오디오에 적용할 수 있습니다. <br>회의 기능입니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>비즈니스용 Skype(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 비즈니스용 Skype 배포의 세부 정보를 캡처합니다. 프레미스에서 배포하지 않은 비즈니스용 Skype 이 섹션을 건너뜁니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 현재 Lync 또는 비즈니스용 Skype 버전 <br>프레미스에서 배포되어 있나요? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 <br/> <input type="checkbox">비즈니스용 Skype 클라우드 커넥터 버전 | |
> | 온라인과 비즈니스용 Skype 구성되어 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 이 환경은 타사에서 호스팅 및 관리하나요? <br/>예인 경우 메모 열에 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 사용 중인 모달 및 기능 <br>오늘은? | <input type="checkbox"> 메신저 및 현재 상태(IM/P) <br/> <input type="checkbox"> 모임 <br/> <input type="checkbox"> 페더전 <br/> <input type="checkbox"> 모임 녹음 <br/> <input type="checkbox"> 영구 채팅/그룹 채팅 <br/> <input type="checkbox"> Microsoft 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (이전 회의에서 전화 걸기) <br>&nbsp;&nbsp; &nbsp; 온-프레미스 Lync Server 또는 <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype 배포 <br/> <input type="checkbox"> 타사 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보 참고) <br/> <input type="checkbox">Enterprise Voice PSTN을 사용하여 <br>&nbsp;&nbsp; &nbsp; 연결 <br/> <input type="checkbox"> 를 통해 계획(이전 PSTN 호출)을 호출합니다. <br>&nbsp;&nbsp; &nbsp; 온라인에서 비즈니스용 Skype 하이브리드 | |
> | 배포한 Edge Server 버전은 무엇입니까? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 | |
> | Edge가 배포된 Lync 또는 비즈니스용 Skype 있는가 <br>두 개 이상의 데이터 센터로 사용하나요? <br/>예인 경우 메모 열에 세부 정보를 메모합니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | Edge 역할이 현재 제공하는 서비스를 선택합니다. | <input type="checkbox"> 외부 사용자 액세스(회사 사용자) <br/> <input type="checkbox"> 원격 사용자 액세스(익명 외부) <br>&nbsp;&nbsp; &nbsp; 모임 참가자) <br/> <input type="checkbox"> 페더전 <br/> <input type="checkbox"> 미디어 릴레이 | |
> | 다음 음성 통화 기능 중 어떤 기능을 사용할 수 있습니다. <br>현재 종속성은 있나요? <br/>메모의 추가 종속성에 유의합니다. <br>열. | <input type="checkbox"> 사용 중 옵션 <br/> <input type="checkbox"> 통화 공원 <br/> <input type="checkbox"> 통화 픽업 또는 그룹 통화 픽업 <br/> <input type="checkbox"> 공용 영역 전화 또는 "핫 데스크" <br/> <input type="checkbox"> 응답 그룹 또는 사냥 그룹 <br/> <input type="checkbox"> 공유 줄 모양 <br/> <input type="checkbox"> 개인 줄 <br/> <input type="checkbox"> 음성사서 <br/> <input type="checkbox"> 업무를 통해 통화 <br/> <input type="checkbox"> 긴급 또는 정보 번호 <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> 확장 전화 걸기 <br/> <input type="checkbox"> 자동 전화 교환 <br/> <input type="checkbox"> 구독자 액세스 <br/> <input type="checkbox"> 아날로그 디바이스 <br/> <input type="checkbox"> 팩스 <br/> <input type="checkbox"> 발신자 ID 마스킹 또는 변경 <br/> <input type="checkbox"> 위치 기반 라우팅 <br/> <input type="checkbox"> 최소 비용 라우팅 <br/> <input type="checkbox"> 엘리베이터 휴대폰 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>네트워크 및 Microsoft 365 또는 Office 365 액세스

다음 표를 사용하여 조직의 네트워킹 세부 정보 및 사용자가 서비스 또는 서비스에 연결되는 방식(또는)을 Microsoft 365 Office 365 있습니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 마이그레이션 범위의 사용자를 어떻게(또는 어떻게) 할지 <br>사무실에 Teams 경우 액세스 권한이 있나요? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> 라우팅된 NAT 연결 <br/> <input type="checkbox"> 프록시 서버 <br/> <input type="checkbox"> 공용 Wi-Fi <br/> <input type="checkbox"> 관리되는(공개되지 않은) Wi-Fi <br/> <input type="checkbox"> ExpressRoute(Microsoft 피어링) ||
> | 프록시 Microsoft 365 Office 365 액세스하는 경우 <br>프록시를 무시하는 방법은 무엇입니까? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | ExpressRoute가 오늘 사용 되나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 <br/> <input type="checkbox"> 아니요, 하지만 계획 중입니다. | |
> | 네트워크 준비 평가를 수행한 경우 | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 연결할 때 VPN을 사용해야 하는 사용자 <br>회사 리소스가 원격으로 사용하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | VPN을 사용하는 경우 트래픽을 Teams 제외할 수 있습니다. <br>VPN을 사용하여 서비스에 Microsoft 365 Office 365 액세스하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 네트워크가 QoS를 지원하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 오디오 및 비디오 트래픽의 Teams 우선 순위를 지정할 수 있습니다. <br>고품질 환경을 구동할 수 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 지역 내의 모든 위치에 인터넷이 있는 경우 <br>또는 인터넷이 전체 지역에 대해 중앙 집중식으로 연결하나요? | <input type="checkbox"> 인터넷에 대한 지역별 액세스 <br/> <input type="checkbox"> 인터넷에 대한 중앙 집중식 액세스 | |

## <a name="endpoints"></a>엔드포인트

다음 표를 사용하여 사용 중인 클라이언트 및 엔드포인트의 세부 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 사용자가 사용하는 데스크톱 OS는 무엇입니까? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac(주석 열에서 버전을 지정합니다.) <br/> <input type="checkbox"> Linux(주석 열에 배포를 지정합니다.) <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 참고합니다.) | |
> | 배포되는 Microsoft Office 버전 <br>이러한 디바이스에? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Mac용 Office 2011 <br/> <input type="checkbox">Mac용 Office 2016 <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 참고합니다.) | |
> | 사용 Office 배포 기술 <br>조직에서? | <input type="checkbox"> MSI <br/> <input type="checkbox"> 클릭-실행 | |
> | 허용되는 모바일 및 지원되는 모바일은 무엇일지 <br>사용 중 플랫폼? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox">Windows <br/> <input type="checkbox"> 모바일 <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 참고합니다.) | |
> | 모바일 디바이스는 어떻게 제공하나요? <br/>적용되는 모든 옵션을 선택합니다. | <input type="checkbox"> 회사 디바이스 <br/> <input type="checkbox"> 사용자만의 디바이스 가져오기 | |
> | 사용자가 현재 액세스하는 데 사용하는 디바이스 <br>음성 및 회의 서비스 <br>(핸드셋, 헤드셋, 휴대폰, 비디오)? | | |

## <a name="operations"></a>작업

다음 표를 사용하여 환경의 운영 측면의 세부 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | Lync Server의 작업 모델 <br>비즈니스용 Skype 서버, Microsoft 365 또는 Office 365 배포 <br>오늘은? | | |
> | 현재 지원 배열을 간략하게 설명할 수 있습니다. <br>Lync Server, 비즈니스용 Skype 서버, Microsoft 365 또는 Office 365? | | |
> | 여러 국가 또는 지역에 배포하는 경우 <br>각 국가/지역에 자체 IT/전화 통신이 있는 경우 <br>직원에게 작업할지 아니면 중앙에서 관리될까요? | <input type="checkbox"> 지역 운영 및 지원 <br/> <input type="checkbox"> 중앙 집중식 작업 및 지원 | |
> | 통화 품질 [방법론을 따라가나요?](quality-of-experience-review-guide.md) | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 개인 또는 팀을 배정한 경우 <br>공동 작업 플랫폼에 대한 Quality Champion 역할 <br>사용 중이신가요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||
> | Lync Server를 모니터링하는 Skype <br>Business Server, Microsoft 365 또는 Office 365? | | |
> | 통화 품질 문제가 있나요? | <input type="checkbox"> 예<br/> <input type="checkbox"> 아니요 | |
> | 사용자에 대한 교육을 언제 어떻게 제공해야 겠는가 <br>새 서비스 및 기능에 대한 헬프데스크? | | |

## <a name="adoption-and-readiness"></a>채택 및 준비

다음 표를 사용하여 조직의 현재 채택 및 준비 상태를 캡처합니다.

>
> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 현재 활성 사용 현황 <br>비즈니스용 Skype? | **__%** 총 활성 사용자 및 사용 가능한 사용자 | |
> | 조직에서 사용하는 방법 <br>비즈니스용 Skype? | 1:1 대화 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 호출 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br> 모임 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 회의<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 호출 | |
> | 조직에 사용자 채택이 있는가 <br>및 변경 관리 팀? | <input type="checkbox"> 예<br/> <input type="checkbox"> 아니요 | |
> | 현재 기술의 성공을 측정하는 방법 <br>롤아웃과 비즈니스용 Skype? | | |
> | 사용자 기반의 백분율 <br>비즈니스용 Skype? | | |
> | 사용자에 대한 사용자 감정은 비즈니스용 Skype? | <input type="checkbox"> 좋음 <br/> <input type="checkbox"> 중립적 <br/> <input type="checkbox"> 잘못된 | |
> | 롤아웃을 가장 잘 설명하는 항목은 다음과 같습니다. <br>에 사용되는 전략이 비즈니스용 Skype <br>배포? | <input type="checkbox"> 광범위한 도달 범위: 전자 메일 캠페인과 함께 <br>&nbsp;&nbsp; &nbsp; 교육 링크 <br/> <input type="checkbox"> 확장: 광범위한 도달 범위 및 다양한 <br>&nbsp;&nbsp; &nbsp; 인식 캠페인(포스터, <br>&nbsp;&nbsp; &nbsp; 이벤트, 챔피언) 및 교육 <br>&nbsp;&nbsp; &nbsp; (비디오, 사용자 가이드, 대면) <br/> <input type="checkbox"> 맞춤: 확장 및 대상 지정 <br>&nbsp;&nbsp; &nbsp; persona에 의해 메시징 및 교육 <br/> <input type="checkbox"> 기타 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보를 참고합니다.) | |


