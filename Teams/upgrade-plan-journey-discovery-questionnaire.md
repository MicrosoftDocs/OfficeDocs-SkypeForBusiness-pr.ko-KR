---
title: Microsoft 팀 업그레이드 | 환경 평가, 검색 질문
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 이 지침을 사용 하 여 팀으로 업그레이드 하기 위한 현재 환경을 적절 하 게 평가 하는 요구 사항에 대해 알아보세요.
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
ms.openlocfilehash: b031b768bf918107cd60563e2e31b8d71b9018cc
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158776"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>검색 질문-환경 평가

[팀으로 업그레이드 하기 전에 환경을 평가](upgrade-plan-journey-evaluate-environment.md)하는 데 도움이 되는 질문은 다음과 같은 표 집합에 나열 되어 있습니다.

- [Microsoft 365 또는 Office 365 조직 세부 정보](#microsoft-365-or-office-365-organization-details)
- [기존 공동 작업 플랫폼 요약](#existing-collaboration-platform-summary)
- [공동 작업 플랫폼 배포 세부 정보](#collaboration-platform-deployment-details)
- [네트워킹 및 Microsoft 365 또는 Office 365 서비스에 대 한 액세스](#networking-and-access-to-microsoft-365-or-office-365-services)
- [끝점](#endpoints)
- [운영](#operations)
- [채택 및 준비](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 또는 Office 365 조직 세부 정보

질문에 대 한 작업을 하는 경우에는 활성 Microsoft 365 또는 Office 365 조 직을 사용 하는 것이 좋습니다. Microsoft 365 또는 Office 365 조 직을 아직 활성화 하지 않았거나 구성 하지 않은 경우 [비즈니스용 microsoft 365 설정 계획](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)을 참조 하세요.

다음 표를 사용 하 여 Microsoft 365 또는 Office 365 조직에 대 한 정보를 수집 합니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 프로덕션 Microsoft 365 또는 Office 365 조직에 유의 <br>응답 열의 이름 및 ID <br/>테 넌 트가 두 개 이상 있는 경우 <br>조직과 연결 된 경우 <br>모든 Id를 기록해 둡니다. | 테 넌 트 이름: <br/>테 넌 트 ID:| |
> | 테 넌 트는 어떤 영역을 배포 하나요?| | |
> | 이러한 테 넌 트 Microsoft 365 또는 Office 365 다중 테 넌 트 <br>전용? | <input type="checkbox">다중<br/> <input type="checkbox">전용 | |
> | 현재 사용 중인 Microsoft Online 제품은 어디에 있나요? <br/>각 사용자의 수를 설정 합니다. <br>설명 열에 서비스를 추가 합니다. | <input type="checkbox">Microsoft 팀 <br/> <input type="checkbox">비즈니스용 Skype <br>&nbsp;&nbsp; &nbsp; 온라인 <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">비즈니스용 OneDrive <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">나머지| |
> | 용 Skype에 대해 사용 가능한 라이선스 수준 <br>비즈니스 온라인 사용자 | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">독립 | 사용자 수 <br>각 SKU에 대해 다음을 수행 합니다. |
> | 현재 Active Directory 포리스트 <br>환경의 기능 수준 <br/>포리스트가 여러 개 있는 경우 세부 정보를 확인 합니다. <br>메모 열 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 디렉터리에 사용 하는 항목 <br>오늘 동기화 하 시겠습니까? |<input type="checkbox">동기화 안 함 (클라우드만 해당) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp; 연결은 <br/> <input type="checkbox">Other (지정 된 <br>&nbsp;&nbsp; &nbsp; 메모 열.)| |
> | 현재 페더레이션 id가 배포 되어 있습니까? <br/>(Active Directory Federation Services 또는 <br>제 3 자) | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 페더레이션 id를 사용 하 고 있는 경우 <br>페더레이션 인프라 | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">타사 페더레이션 <br>&nbsp;&nbsp; &nbsp; gateway <br>&nbsp;&nbsp; &nbsp; (참고 항목 <br>&nbsp;&nbsp; &nbsp; 메모 열.) | |
> | 현재 활성 상태인 Microsoft 365 또는 Office 365을 유지 관리 하는 경우 <br>테 넌 트는 귀하의 SMTP/SIP 도메인입니다. <br>테 넌 트와 연결 된 대상 사용자 | <input type="checkbox">N/A-Microsoft 365 또는 Office 365 없음 <br>&nbsp;&nbsp; &nbsp; 현재 위치에서 테 넌 트 <br/> <input type="checkbox">아니요, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 도메인이 연결 되어 있지 않습니다. <br>&nbsp;&nbsp; &nbsp; 의 모든 테 넌 트 사용 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 도메인이 연결 됨 <br>&nbsp;&nbsp; &nbsp; 기존 테 넌 트 사용 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365 | |
> | 사용자 Upn이 기본 SMTP 주소와 일치 하나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 <br/> <input type="checkbox">명령이 | |

## <a name="existing-collaboration-platform-summary"></a>기존 공동 작업 플랫폼 요약

다음 표를 사용 하 여 기존 공동 작업 플랫폼 배포에 대 한 정보를 수집 합니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | Microsoft 팀이 배포 되나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 비즈니스용 Skype를 배포 하 고 계십니까? <br/>온-프레미스 및 하이브리드 배포의 경우 다음을 수행 해야 합니다. <br>버전 및 누적 업데이트 (CU ()를 기록해 둡니다. <br>메모 열에 자세히 설명 되어 있습니다. | <input type="checkbox">예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 혼성 (Microsoft 365 또는 Office 365 사용) <br/> <input type="checkbox">예, 온-프레미스 <br/> <input type="checkbox">예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">예, 호스팅 가능, 전용 <br>&nbsp;&nbsp; &nbsp; (제 3 자) <br/> <input type="checkbox">예, 호스팅, 공유 (제 3 자) <br/> <input type="checkbox">아니요, 기타 | |
> | Exchange가 배포 되었습니까? <br/>온-프레미스 및 하이브리드 배포의 경우 다음을 수행 해야 합니다. <br>메모의 버전 및 CU (세부 정보를 적어 둡니다. <br>열. | <input type="checkbox">예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 혼성 (Microsoft 365 또는 Office 365 사용) <br/> <input type="checkbox">예, 온-프레미스 <br/> <input type="checkbox">예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">예, 호스팅 가능, 전용 <br>&nbsp;&nbsp; &nbsp; (제 3 자) <br/> <input type="checkbox">예, 호스팅, 공유 <br>&nbsp;&nbsp; &nbsp; (제 3 자) <br/> <input type="checkbox">아니요, 기타 | |
> | SharePoint가 배포 되나요? <br/>온-프레미스 및 하이브리드 배포의 경우 다음을 수행 해야 합니다. <br>메모의 버전 및 CU (세부 정보를 적어 둡니다. <br>열. | <input type="checkbox">예, Microsoft 365 또는 Office 365 <br/> <input type="checkbox">예, 혼성 (Microsoft 365 또는 Office 365 사용) <br/> <input type="checkbox">예, 온-프레미스 <br/> <input type="checkbox">예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">예, 호스팅 가능, 전용 <br>&nbsp;&nbsp; &nbsp; (제 3 자) <br/> <input type="checkbox">예, 호스팅, 공유 <br>&nbsp;&nbsp; &nbsp; (제 3 자) <br/> <input type="checkbox">아니요, 기타 | |
> | Microsoft 365 또는 Office 365 비즈니스용 OneDrive가 배포 되나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 다른 서드 파티 플랫폼이 배포 되어 있는지 <br>현재 사용 중인 경우 그렇다면 다음 사용자 수를 기록해 둡니다. <br>이러한 플랫폼 및 메모의 사용 세부 정보 <br>열. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">이란 <br/> <input type="checkbox">기타 (메모에 지정 <br>&nbsp;&nbsp; &nbsp; 열.) | 사용자 수: <br/>세부적인|
> | 이 타사에서 사용자를 이동할 계획 입니까? <br>팀에 대 한 플랫폼 | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 현재 전화 통신 및 회의 솔루션은 무엇 인가요? <br>이 이니셔티브의 범위에 있는 사용자의 경우 | | |
> | 이 이니셔티브에 대 한 범위 내에 있는 사무실에 배포 된 [직접 라우팅을 지 원하는 SBCs](direct-routing-plan.md#supported-session-border-controllers-sbcs) 가 있나요? <br>예를 들어 메모 열의 세부 정보를 기록해 둡니다.| <input type="checkbox">' <br/> <input type="checkbox">아니요 ||

## <a name="collaboration-platform-deployment-details"></a>공동 작업 플랫폼 배포 세부 정보

### <a name="microsoft-teams-if-applicable"></a>Microsoft 팀 (해당 하는 경우)

해당 하는 경우 아래 예제 표를 사용 하 여 팀 배포의 세부 정보를 수집 합니다. 팀을 배포 하지 않은 경우이 섹션을 건너뛰십시오.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 팀에 대해 어떤 사용자 유형을 사용할 수 있나요? | <input type="checkbox">조직의 모든 사용자 <br/> <input type="checkbox">특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; &nbsp; (메모 열에서 지정) ||
> | 사용 중인 팀 기능 및 형식을 | <input type="checkbox">채널 기반 대화 <br/> <input type="checkbox">개인 채팅 <br/> <input type="checkbox">게스트 액세스 <br/> <input type="checkbox">채널 모임 <br/> <input type="checkbox">비공개 모임 <br/> <input type="checkbox">비공개 통화 <br/> <input type="checkbox">Ad-hoc 채널 잔 <br/> <input type="checkbox">모임의 비디오 <br/> <input type="checkbox">모임에서 화면 공유 <br/> <input type="checkbox">오디오 회의 <br/><input type="checkbox">응용 프로그램 (앱)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> 탭<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 봇 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 기가<br><input type="checkbox">사용자 지정 클라우드 저장소 통합 <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google Drive, Egnyte (곧 출시 예정) <br/> <input type="checkbox">채널 전자 메일 통합 <br/> <input type="checkbox">기타 (메모 열에서 지정) | |
> | 팀에 배포 하는 응용 프로그램은 무엇 인가요? | | |
> | 팀의 접근 권한 값을 구체적으로 차단 했습니까? <br/>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 ||
> | 사용 중인 팀 클라이언트 | <input type="checkbox">웹 <br/> <input type="checkbox">창을 <br/> <input type="checkbox">Ac <br/> <input type="checkbox">Io <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | 팀을 만들 수 있는 권한이 있는 사람은 누구 입니까? | <input type="checkbox">조직의 모든 사용자 <br>&nbsp;&nbsp; &nbsp; (기본 설정) <br/> <input type="checkbox">특정 사용자 <br>&nbsp;&nbsp; &nbsp; (메모 열에서 지정 합니다.) | |
> | 팀의 보안 및 규정 준수 기능을 사용 하 고 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |

### <a name="skype-for-business-online-if-applicable"></a>비즈니스용 Skype Online (해당 하는 경우)

해당 하는 경우 아래 예제 표를 사용 하 여 비즈니스용 Skype Online 배포에 대 한 세부 정보를 수집 합니다. 비즈니스용 Skype Online 배포를 배포 하지 않은 경우이 섹션을 건너뛰십시오.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | Skype에 대해 어떤 유형의 사용자를 사용할 수 있는지 <br>비즈니스용 온라인 | <input type="checkbox">조직의 모든 사용자 <br/> <input type="checkbox">특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; &nbsp; (메모 열에서 지정) | |
> | 현재 형식을 및 기능 <br>지금 사용 하 고 계십니까? | <input type="checkbox">인스턴트 메시지 및 현재 상태 (IM/P)<br/> <input type="checkbox">Meeting <br/> <input type="checkbox">Federation <br/> <input type="checkbox">모임 녹음/녹화 <br/> <input type="checkbox">Microsoft 오디오 회의 <br/> <input type="checkbox">타사 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보를 기록해 둡니다.) <br/> <input type="checkbox">통화 요금제 (이전의 PSTN 통화) <br/> <input type="checkbox">조직 자동 전화 교환 <br/> <input type="checkbox">통화 대기열 | |
> | 의 Skype를 구체적으로 차단 하셨습니다. <br>비즈니스 온라인 기능 <br>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 사용 하는 방법 또는 사용 계획 <br>휴대폰 시스템 연결 (이전의 클라우드 PBX) <br>PSTN 인가요? <br/>적용 되는 모든 것을 선택 합니다. | <input type="checkbox">통화 요금제 (이전의 PSTN 통화) <br/> <input type="checkbox">온-프레미스 PSTN 연결 (기존 컴퓨터 활용 <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype 2015 또는 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 배포) <br/> <input type="checkbox">온-프레미스 PSTN 연결 (클라우드 커넥터 사용) | |
> | 모든 전화 번호를 Microsoft로 이식 했습니까? <br/>이는 통화 요금제 및 오디오에 적용 됩니다. <br>회의 기능. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>비즈니스용 Skype 온-프레미스 (해당 하는 경우)

해당 하는 경우 아래 예제 표를 사용 하 여 비즈니스용 Skype 배포에 대 한 세부 정보를 수집 합니다. 비즈니스용 Skype 온-프레미스를 배포 하지 않은 경우이 섹션을 건너뛰십시오.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 현재 Lync 또는 비즈니스용 Skype 버전 <br>온-프레미스에 배포 됨 | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 <br/> <input type="checkbox">비즈니스용 Skype 클라우드 커넥터 에디션 | |
> | 비즈니스용 Skype Online이 구성 된 하이브리드이 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 제 3 자에 의해이 환경이 호스팅되며 관리 되나요? <br/>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 현재 사용 중인 형식을 및 기능 <br>오늘로? | <input type="checkbox">인스턴트 메시지 및 현재 상태 (IM/P) <br/> <input type="checkbox">Meeting <br/> <input type="checkbox">Federation <br/> <input type="checkbox">모임 녹음/녹화 <br/> <input type="checkbox">영구 채팅/그룹 채팅 <br/> <input type="checkbox">Microsoft 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (이전에는 회의에 전화 접속) <br>&nbsp;온 &nbsp; &nbsp; -프레미스 Lync Server 또는 <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype 배포 <br/> <input type="checkbox">타사 오디오 회의 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보 참고) <br/> <input type="checkbox">온-프레미스 PSTN을 사용 하는 Enterprise Voice <br>&nbsp;&nbsp; &nbsp; 연결 <br/> <input type="checkbox">(이전의 PSTN 통화)를 통한 통화 계획 <br>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype Online으로 하이브리드 | |
> | 배포한 Edge 서버의 버전은 무엇 인가요? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 | |
> | Lync 또는 비즈니스용 Skype Edge가 배포 되어 있습니까? <br>두 개 이상의 데이터 센터에 <br/>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | Edge 역할이 현재 제공 하는 서비스를 선택 합니다. | <input type="checkbox">외부 사용자 액세스 (회사 사용자) <br/> <input type="checkbox">원격 사용자 액세스 (익명 외부 <br>&nbsp;&nbsp; &nbsp; 모임 참가자) <br/> <input type="checkbox">Federation <br/> <input type="checkbox">미디어 릴레이 | |
> | 다음 음성 통화 기능 중 어떤 것을 사용할 수 있습니까? <br>현재 종속성이 있나요? <br/>메모에 추가 종속성을 기록 합니다. <br>열. | <input type="checkbox">약속 있음 옵션 <br/> <input type="checkbox">통화 공원 <br/> <input type="checkbox">통화 픽업 또는 그룹 통화 픽업 <br/> <input type="checkbox">일반 지역 전화 또는 "hot desking" <br/> <input type="checkbox">응답 그룹 또는 헌트 그룹 <br/> <input type="checkbox">공유 선 모양 <br/> <input type="checkbox">비공개 회선 <br/> <input type="checkbox">보이스 메일 <br/> <input type="checkbox">직장을 통한 통화 <br/> <input type="checkbox">긴급 또는 정보 번호 <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox">내선 번호 <br/> <input type="checkbox">자동 전화 교환 <br/> <input type="checkbox">구독자 액세스 <br/> <input type="checkbox">아날로그 장치 <br/> <input type="checkbox">전송 <br/> <input type="checkbox">발신자 ID 마스킹 또는 변경 <br/> <input type="checkbox">위치 기반 라우팅 <br/> <input type="checkbox">가장 저렴 한 라우팅 <br/> <input type="checkbox">엘리베이터 전화 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>네트워킹 및 Microsoft 365 또는 Office 365 서비스에 대 한 액세스

다음 표를 사용 하 여 조직의 네트워크 세부 정보를 캡처하고 사용자가 Microsoft 365 또는 Office 365 서비스에 연결 되는 방법을 알아보세요.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 사용자의 마이그레이션 범위 (또는 방법) <br>팀이 사무실에 있는 동안 액세스 하 고 계십니까? <br/>적용 되는 모든 것을 선택 합니다. | <input type="checkbox">라우팅된 NAT 연결 <br/> <input type="checkbox">프록시 서버 <br/> <input type="checkbox">공개 Wi-fi <br/> <input type="checkbox">관리 (공개 아님) Wi-fi <br/> <input type="checkbox">Express 경로 (Microsoft 피어 링) ||
> | 프록시 서버를 통해 Microsoft 365 또는 Office 365에 액세스할 수 있는 경우 <br>프록시를 우회 하는 방법 | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 현재 Express 경로를 사용 하 고 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 <br/> <input type="checkbox">아니요, 계획 중입니다. | |
> | 네트워크 준비 평가를 수행 했습니까? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 연결할 때 VPN을 사용 해야 하는 사용자 <br>원격으로 회사 리소스 | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | VPN을 사용 하는 경우 팀 트래픽을 다음에서 제외할 수 있습니다. <br>VPN에서 Microsoft 365 또는 Office 365 서비스에 직접 액세스 합니까? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 네트워크 지원 QoS가 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 팀의 오디오 및 비디오 소통량에 우선 순위를 지정할 수 있습니다. <br>고품질 환경을 구동 하려면 어떻게 하나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 지역 내의 모든 위치에 인터넷 송신이 필요 합니다. <br>또는 전체 지역에 대해 인터넷 송신이 중앙 집중화 되나요? | <input type="checkbox">인터넷에 대 한 국가별 액세스 <br/> <input type="checkbox">중앙 인터넷 액세스 | |

## <a name="endpoints"></a>끝점

사용 중인 클라이언트 및 끝점에 대 한 세부 정보를 캡처하려면 다음 표를 사용 합니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 사용자가 사용 중인 데스크톱 OS는 무엇 인가요? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (메모 열에서 버전을 지정 합니다.) <br/> <input type="checkbox">Linux (메모 열에 분포 지정) <br/> <input type="checkbox">기타 (메모 열의 세부 정보를 참고 하세요.) | |
> | 배포 되는 Microsoft Office 버전 <br>이 장치에 대 한 자세한 내용을 확인 하세요. | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Mac 용 Office 2011 <br/> <input type="checkbox">Mac 용 Office 2016 <br/> <input type="checkbox">기타 (메모 열의 세부 정보를 참고 하세요.) | |
> | 사용 중인 Office 배포 기술 <br>조직에서 | <input type="checkbox">MSI <br/> <input type="checkbox">간편 실행 | |
> | 허용 및 지원 되는 모바일 장치 <br>사용 중인 플랫폼 <br/>적용 되는 모든 것을 선택 합니다. | <input type="checkbox">창을 <br/> <input type="checkbox">무선 <br/> <input type="checkbox">Io <br/> <input type="checkbox">Android <br/> <input type="checkbox">기타 (메모 열의 세부 정보를 참고 하세요.) | |
> | 모바일 장치를 어떻게 제공 하나요? <br/>적용 되는 모든 것을 선택 합니다. | <input type="checkbox">회사 장치 <br/> <input type="checkbox">나만의 장치 가져오기 | |
> | 현재 사용자가 액세스 하는 데 사용 하는 장치 <br>음성 및 회의 서비스 <br>(송수화기, 헤드셋, 전화, 영상)? | | |

## <a name="operations"></a>운영

다음 표를 사용 하 여 환경의 작업 측면에 대 한 세부 정보를 수집 합니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | Lync 서버용 운영 모델은 무엇 인가요? <br>비즈니스용 Skype 서버, Microsoft 365 또는 Office 365 배포 <br>오늘로? | | |
> | 현재 지원 배열에 대 한 개요를 만들 수 있습니다. <br>Lync Server, 비즈니스용 Skype 서버, Microsoft 365 또는 Office 365? | | |
> | 여러 국가나 지역에 배포 하는 경우 <br>각 국가/지역에 고유한 IT/전화 통신이 있는지 <br>직원이 작업을 수행 하거나 중앙에서 관리할 수 있나요? | <input type="checkbox">국가별 작업 및 지원 <br/> <input type="checkbox">중앙 집중화 된 운영 및 지원 | |
> | [통화 품질 방법론](quality-of-experience-review-guide.md)을 팔 로우 하 고 계십니까? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 개인 또는 팀을 지정 하 여 <br>공동 작업 플랫폼의 품질 챔피언 역할 <br>사용 중인 경우 | <input type="checkbox">' <br/> <input type="checkbox">아니요 ||
> | Lync Server를 모니터링 하는 방법, Skype <br>비즈니스 서버, Microsoft 365 또는 Office 365 배포 | | |
> | 통화 품질 문제가 발생 하나요? | <input type="checkbox">'<br/> <input type="checkbox">아니요 | |
> | 어디에 교육을 제공 하는 방법과 시기 <br>새로운 서비스 및 기능에 대 한 헬프데스크 | | |

## <a name="adoption-and-readiness"></a>채택 및 준비

다음 표를 사용 하 여 조직의 현재 채택 및 준비 상태를 수집 합니다.

>
> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 의 현재 활성 사용량은 무엇 인가요? <br>비즈니스용 Skype | **__** % 총 활성 사용자와 사용 가능한 사용자 비교 | |
> | 조직에서 사용 하는 방법 <br>비즈니스용 Skype | 1:1 대화 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 메시징 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 전화 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br> 모임 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 회의용<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 전화 | |
> | 조직에서 사용자 채택을 사용 합니까? <br>변경 관리 팀 | <input type="checkbox">'<br/> <input type="checkbox">아니요 | |
> | 현재 기술에 대 한 성공 여부를 측정 하는 방법 <br>비즈니스용 Skype와 유사 하 게 롤아웃 | | |
> | 사용자 기준으로 사용할 백분율 <br>비즈니스용 Skype를 채택 하시 나요? | | |
> | 비즈니스용 Skype 주변의 사용자 정서? | <input type="checkbox">적합 <br/> <input type="checkbox">중립 <br/> <input type="checkbox">잘못 | |
> | 다음 중 롤아웃에 가장 잘 설명 된 내용 <br>Skype for Business에 사용 되는 전략 <br>배포가? | <input type="checkbox">광범위 한 접근: 전자 메일 캠페인 <br>&nbsp;&nbsp; &nbsp; 교육 링크 <br/> <input type="checkbox">확장: 폭넓은 달성 범위와 다양 한 <br>&nbsp;&nbsp; &nbsp; 의 인식 캠페인 (포스터, <br>&nbsp;&nbsp; &nbsp; 이벤트, 챔피언) 및 교육 <br>&nbsp;&nbsp; &nbsp; (비디오, 사용자 안내서, 사용자) <br/> <input type="checkbox">맞춤: 확장 됨, 대상 추가 <br>&nbsp;&nbsp; &nbsp; 가상 사용자의 메시지 및 교육 <br/> <input type="checkbox">나머지 <br>&nbsp;&nbsp; &nbsp; (메모 열의 세부 정보를 기록해 둡니다.) | |


