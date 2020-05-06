---
title: Microsoft 팀 업그레이드 | 환경 평가, 검색 질문
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
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
ms.openlocfilehash: cd9ee15a1fad0e8fcb228b449bf4cea41da0eeb1
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041745"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>팀으로 업그레이드 하기 전에 환경 평가

![여행 다이어그램 업그레이드, 기술 준비 단계 강조](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")

이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다. 계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

이 문서에서는 운영 팀의 현재 환경을 적절 하 게 평가 하기 위한 요구 사항을 간략하게 설명 합니다. 환경을 평가 하 여 전체 배포에 영향을 주는 위험 및 요구 사항을 식별 합니다. 이러한 항목을 미리 확인 하 여 성공에 대 한 계획을 조정할 수 있습니다.

## <a name="introduction-to-the-discovery-questionnaire"></a>검색 질문에 대 한 소개

목표 키 결과 (OKRs)를 달성 하기 위해 이전에는 키 서비스 결정을 했습니다. 다음 단계는 환경 검색을 수행 하 여 IT 인프라, 네트워킹 및 작업 관련 모든 측면을 평가 하 여 조직이 솔루션을 구현할 준비가 되었는지 확인 하는 것입니다. 검색은 팀에 대 한 여행 계획을 수립할 때 가장 먼저 수행 하는 주요 단계 중 하나입니다. 환경 검색에는 네트워크가 팀으로 업그레이드를 지원할 수 있도록 네트워크 준비 평가가 포함 되어야 합니다. 자신의 환경에 대 한 상세한 검색을 수행 하 여 현재 상태를 파악 하 고, 문제가 있거나 팀의 출시에 대 한 가능한 차단 가능성을 더욱 중요 하 게 합니다.

환경 평가 및 채택 준비 평가의 일부로 기술 위험을 식별 하 고 식별 된 각 위험에 대 한 완화 계획을 개발 합니다. 이 정보는 위험 등록기에 통합 해야 합니다.

기존 공동 작업 인프라 및 Office 365 조직, 네트워킹, 끝점, 운영, 채택 및 준비와 관련 된 모든 문제가 환경 검색 질문의 일부로 포함 됩니다. 이 질문에 대 한 설문지는 여러 섹션으로 나뉘어 조직의 팀이 여러 주요 영역에서 배포에 대 한 준비가 되었는지 확인 합니다. 프로젝트 팀과 협력 하 여 필요한 정보를 최대한 자세하게 제공 하 여 계획 활동을 촉진 하세요.

> [!TIP]
> Microsoft Word 문서로 질문을 복사 하 여 시작할 수 있습니다. 모든 질문에 답을 하 고 이동할 때 모든 세부 정보를 수집 해 보세요.

## <a name="project-team"></a>프로젝트 팀

프로젝트 팀에 게 적합 한 사람을 참여 했는지 확인 합니다. [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)에서 완료 한 단계를 확인 합니다.

## <a name="office-365-organization-details"></a>Office 365 조직 세부 정보

이 질문에 대 한 작업을 하는 동안 활성 Office 365 조직을 사용 하는 것이 좋습니다. 아직 Office 365 조직을 활성화 하지 않았거나 구성 하지 않은 경우 [비즈니스용 office 365의 설정 계획](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)을 참조 하세요.

다음 표를 사용 하 여 Office 365 조직에 대 한 정보를 수집 합니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 프로덕션 Office 365 조직에 유의 하십시오. <br>응답 열의 이름 및 ID <br/>테 넌 트가 두 개 이상 있는 경우 <br>조직과 연결 된 경우 <br>모든 Id를 기록해 둡니다. | 테 넌 트 이름: <br/>테 넌 트 ID:| |
> | 테 넌 트는 어떤 영역을 배포 하나요?| | |
> | 이러한 테 넌 트 Office 365 다중 테 넌 트 또는 <br>전용? | <input type="checkbox">다중<br/> <input type="checkbox">전용 | |
> | 현재 사용 중인 Microsoft Online 제품은 어디에 있나요? <br/>각 사용자의 수를 설정 합니다. <br>설명 열에 서비스를 추가 합니다. | <input type="checkbox">Microsoft 팀 <br/> <input type="checkbox">비즈니스용 Skype <br>&nbsp;&nbsp; &nbsp;온라인 상태 <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">비즈니스용 OneDrive <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">나머지| |
> | 용 Skype에 대해 사용 가능한 라이선스 수준 <br>비즈니스 온라인 사용자 | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">독립 | 사용자 수 <br>각 SKU에 대해 다음을 수행 합니다. |
> | 현재 Active Directory 포리스트 <br>환경의 기능 수준 <br/>포리스트가 여러 개 있는 경우 세부 정보를 확인 합니다. <br>메모 열 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 디렉터리에 사용 하는 항목 <br>오늘 동기화 하 시겠습니까? |<input type="checkbox">동기화 안 함 (클라우드만 해당) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;연결 <br/> <input type="checkbox">Other (지정 된 <br>&nbsp;&nbsp; &nbsp;| |
> | 현재 페더레이션 id가 배포 되어 있습니까? <br/>(Active Directory Federation Services 또는 <br>제 3 자) | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 페더레이션 id를 사용 하 고 있는 경우 <br>페더레이션 인프라 | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">타사 페더레이션 <br>&nbsp;&nbsp; &nbsp;gateway <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; | |
> | 현재 활성 상태인 Office 365를 유지 관리 하는 경우 <br>테 넌 트는 귀하의 SMTP/SIP 도메인입니다. <br>테 넌 트와 연결 된 대상 사용자 | <input type="checkbox">N/A-Office 365 없음 <br>&nbsp;&nbsp; 현재 위치에서 테 &nbsp;넌 트 <br/> <input type="checkbox">아니요, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; 도메인이 연결 되어 있지 &nbsp;않습니다. <br>&nbsp;&nbsp; 의 모든 테 넌 &nbsp;트 사용 <br>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox">예, 사용자의 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp;트 사용 <br>&nbsp;&nbsp; &nbsp;Office 365 | |
> | 사용자 Upn이 기본 SMTP 주소와 일치 하나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 <br/> <input type="checkbox">명령이 | |

## <a name="existing-collaboration-platform-summary"></a>기존 공동 작업 플랫폼 요약

다음 표를 사용 하 여 기존 공동 작업 플랫폼 배포에 대 한 정보를 수집 합니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | Microsoft 팀이 배포 되나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 비즈니스용 Skype를 배포 하 고 계십니까? <br/>온-프레미스 및 하이브리드 배포의 경우 다음을 수행 해야 합니다. <br>버전 및 누적 업데이트 (CU ()를 기록해 둡니다. <br>메모 열에 자세히 설명 되어 있습니다. | <input type="checkbox">예, Office 365 <br/> <input type="checkbox">예, 혼성 (Office 365 사용) <br/> <input type="checkbox">예, 온-프레미스 <br/> <input type="checkbox">예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">예, 호스팅 가능, 전용 <br>&nbsp;&nbsp; &nbsp;자) <br/> <input type="checkbox">예, 호스팅, 공유 (제 3 자) <br/> <input type="checkbox">아니요, 기타 | |
> | Exchange가 배포 되었습니까? <br/>온-프레미스 및 하이브리드 배포의 경우 다음을 수행 해야 합니다. <br>메모의 버전 및 CU (세부 정보를 적어 둡니다. <br>열. | <input type="checkbox">예, Office 365 <br/> <input type="checkbox">예, 혼성 (Office 365 사용) <br/> <input type="checkbox">예, 온-프레미스 <br/> <input type="checkbox">예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">예, 호스팅 가능, 전용 <br>&nbsp;&nbsp; &nbsp;자) <br/> <input type="checkbox">예, 호스팅, 공유 <br>&nbsp;&nbsp; &nbsp;자) <br/> <input type="checkbox">아니요, 기타 | |
> | SharePoint가 배포 되나요? <br/>온-프레미스 및 하이브리드 배포의 경우 다음을 수행 해야 합니다. <br>메모의 버전 및 CU (세부 정보를 적어 둡니다. <br>열. | <input type="checkbox">예, Office 365 <br/> <input type="checkbox">예, 혼성 (Office 365 사용) <br/> <input type="checkbox">예, 온-프레미스 <br/> <input type="checkbox">예, 온라인, 전용 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">예, 호스팅 가능, 전용 <br>&nbsp;&nbsp; &nbsp;자) <br/> <input type="checkbox">예, 호스팅, 공유 <br>&nbsp;&nbsp; &nbsp;자) <br/> <input type="checkbox">아니요, 기타 | |
> | Office 365 비즈니스용 OneDrive가 배포 되나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 다른 서드 파티 플랫폼이 배포 되어 있는지 <br>현재 사용 중인 경우 그렇다면 다음 사용자 수를 기록해 둡니다. <br>이러한 플랫폼 및 메모의 사용 세부 정보 <br>열. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">이란 <br/> <input type="checkbox">기타 (메모에 지정 <br>&nbsp;&nbsp; &nbsp; | 사용자 수: <br/>세부적인|
> | 이 타사에서 사용자를 이동할 계획 입니까? <br>팀에 대 한 플랫폼 | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 현재 전화 통신 및 회의 솔루션은 무엇 인가요? <br>이 이니셔티브의 범위에 있는 사용자의 경우 | | |
> | 이 이니셔티브에 대 한 범위 내에 있는 사무실에 배포 된 [직접 라우팅을 지 원하는 SBCs](direct-routing-plan.md#supported-session-border-controllers-sbcs) 가 있나요? <br>예를 들어 메모 열의 세부 정보를 기록해 둡니다.| <input type="checkbox">' <br/> <input type="checkbox">아니요 ||

## <a name="collaboration-platform-deployment-details"></a>공동 작업 플랫폼 배포 세부 정보

### <a name="microsoft-teams-if-applicable"></a>Microsoft 팀 (해당 하는 경우)

해당 하는 경우 아래 예제 표를 사용 하 여 팀 배포의 세부 정보를 수집 합니다. 팀을 배포 하지 않은 경우이 섹션을 건너뛰십시오.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 팀에 대해 어떤 사용자 유형을 사용할 수 있나요? | <input type="checkbox">조직의 모든 사용자 <br/> <input type="checkbox">특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; (메모 열에서 &nbsp;지정) ||
> | 사용 중인 팀 기능 및 형식을 | <input type="checkbox">채널 기반 대화 <br/> <input type="checkbox">개인 채팅 <br/> <input type="checkbox">게스트 액세스 <br/> <input type="checkbox">채널 모임 <br/> <input type="checkbox">비공개 모임 <br/> <input type="checkbox">비공개 통화 <br/> <input type="checkbox">Ad-hoc 채널 잔 <br/> <input type="checkbox">모임의 비디오 <br/> <input type="checkbox">모임에서 화면 공유 <br/> <input type="checkbox">오디오 회의 <br/><input type="checkbox">응용 프로그램 (앱)<br> &nbsp;&nbsp; 탭 &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; 봇 &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; 연결선 &nbsp; <input type="checkbox"><br><input type="checkbox">사용자 지정 클라우드 저장소 통합 <br>&nbsp;&nbsp; Dropbox, Box, sharefile, Google Drive, Egnyte (곧 출시 &nbsp; 예정) <br/> <input type="checkbox">채널 전자 메일 통합 <br/> <input type="checkbox">기타 (메모 열에서 지정) | |
> | 팀에 배포 하는 응용 프로그램은 무엇 인가요? | | |
> | 팀의 접근 권한 값을 구체적으로 차단 했습니까? <br/>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 ||
> | 사용 중인 팀 클라이언트 | <input type="checkbox">웹 <br/> <input type="checkbox">창을 <br/> <input type="checkbox">Ac <br/> <input type="checkbox">Io <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | 팀을 만들 수 있는 권한이 있는 사람은 누구 입니까? | <input type="checkbox">조직의 모든 사용자 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">특정 사용자 <br>&nbsp;&nbsp; (메모 열에서 지정 합니다 &nbsp;.) | |
> | 팀의 보안 및 규정 준수 기능을 사용 하 고 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |

### <a name="skype-for-business-online-if-applicable"></a>비즈니스용 Skype Online (해당 하는 경우)

해당 하는 경우 아래 예제 표를 사용 하 여 비즈니스용 Skype Online 배포에 대 한 세부 정보를 수집 합니다. 비즈니스용 Skype Online 배포를 배포 하지 않은 경우이 섹션을 건너뛰십시오.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | Skype에 대해 어떤 유형의 사용자를 사용할 수 있는지 <br>비즈니스용 온라인 | <input type="checkbox">조직의 모든 사용자 <br/> <input type="checkbox">특정 사용자/사용자 그룹 <br>&nbsp;&nbsp; (메모 열에서 &nbsp;지정) | |
> | 현재 형식을 및 기능 <br>지금 사용 하 고 계십니까? | <input type="checkbox">인스턴트 메시지 및 현재 상태 (IM/P)<br/> <input type="checkbox">Meeting <br/> <input type="checkbox">Federation <br/> <input type="checkbox">모임 녹음/녹화 <br/> <input type="checkbox">Microsoft 오디오 회의 <br/> <input type="checkbox">타사 오디오 회의 <br>&nbsp;&nbsp; (메모 열의 세부 정보를 기록해 둡니다 &nbsp;.) <br/> <input type="checkbox">통화 요금제 (이전의 PSTN 통화) <br/> <input type="checkbox">조직 자동 전화 교환 <br/> <input type="checkbox">통화 대기열 | |
> | 의 Skype를 구체적으로 차단 하셨습니다. <br>비즈니스 온라인 기능 <br>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 사용 하는 방법 또는 사용 계획 <br>휴대폰 시스템 연결 (이전의 클라우드 PBX) <br>PSTN 인가요? <br/>적용 되는 모든 것을 선택 합니다. | <input type="checkbox">통화 요금제 (이전의 PSTN 통화) <br/> <input type="checkbox">온-프레미스 PSTN 연결 (기존 컴퓨터 활용 <br>&nbsp;&nbsp; 비즈니스용 Skype 2015 또는 Lync &nbsp;Server 2013 <br>&nbsp;&nbsp; &nbsp;배포) <br/> <input type="checkbox">온-프레미스 PSTN 연결 (클라우드 커넥터 사용) | |
> | 모든 전화 번호를 Microsoft로 이식 했습니까? <br/>이는 통화 요금제 및 오디오에 적용 됩니다. <br>회의 기능. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>비즈니스용 Skype 온-프레미스 (해당 하는 경우)

해당 하는 경우 아래 예제 표를 사용 하 여 비즈니스용 Skype 배포에 대 한 세부 정보를 수집 합니다. 비즈니스용 Skype 온-프레미스를 배포 하지 않은 경우이 섹션을 건너뛰십시오.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 현재 Lync 또는 비즈니스용 Skype 버전 <br>온-프레미스에 배포 됨 | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 <br/> <input type="checkbox">비즈니스용 Skype 클라우드 커넥터 에디션 | |
> | 비즈니스용 Skype Online이 구성 된 하이브리드이 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 제 3 자에 의해이 환경이 호스팅되며 관리 되나요? <br/>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 현재 사용 중인 형식을 및 기능 <br>오늘로? | <input type="checkbox">인스턴트 메시지 및 현재 상태 (IM/P) <br/> <input type="checkbox">Meeting <br/> <input type="checkbox">Federation <br/> <input type="checkbox">모임 녹음/녹화 <br/> <input type="checkbox">영구 채팅/그룹 채팅 <br/> <input type="checkbox">Microsoft 오디오 회의 <br>&nbsp;&nbsp; (이전에는 회의에 전화 &nbsp;접속) <br>&nbsp;&nbsp; 온-프레미스 Lync &nbsp;Server 또는 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">타사 오디오 회의 <br>&nbsp;&nbsp; (메모 열의 세부 정보 &nbsp;참고) <br/> <input type="checkbox">온-프레미스 PSTN을 사용 하는 Enterprise Voice <br>&nbsp;&nbsp; &nbsp;연결 <br/> <input type="checkbox">(이전의 PSTN 통화)를 통한 통화 계획 <br>&nbsp;&nbsp; &nbsp;으로 하이브리드 | |
> | 배포한 Edge 서버의 버전은 무엇 인가요? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 | |
> | Lync 또는 비즈니스용 Skype Edge가 배포 되어 있습니까? <br>두 개 이상의 데이터 센터에 <br/>예를 들어 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | Edge 역할이 현재 제공 하는 서비스를 선택 합니다. | <input type="checkbox">외부 사용자 액세스 (회사 사용자) <br/> <input type="checkbox">원격 사용자 액세스 (익명 외부 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Federation <br/> <input type="checkbox">미디어 릴레이 | |
> | 다음 음성 통화 기능 중 어떤 것을 사용할 수 있습니까? <br>현재 종속성이 있나요? <br/>메모에 추가 종속성을 기록 합니다. <br>열. | <input type="checkbox">약속 있음 옵션 <br/> <input type="checkbox">통화 공원 <br/> <input type="checkbox">통화 픽업 또는 그룹 통화 픽업 <br/> <input type="checkbox">일반 지역 전화 또는 "hot desking" <br/> <input type="checkbox">응답 그룹 또는 헌트 그룹 <br/> <input type="checkbox">공유 선 모양 <br/> <input type="checkbox">비공개 회선 <br/> <input type="checkbox">보이스 메일 <br/> <input type="checkbox">직장을 통한 통화 <br/> <input type="checkbox">긴급 또는 정보 번호 <br>&nbsp;&nbsp; (911, 811, &nbsp;411) <br/> <input type="checkbox">내선 번호 <br/> <input type="checkbox">자동 전화 교환 <br/> <input type="checkbox">구독자 액세스 <br/> <input type="checkbox">아날로그 장치 <br/> <input type="checkbox">전송 <br/> <input type="checkbox">발신자 ID 마스킹 또는 변경 <br/> <input type="checkbox">위치 기반 라우팅 <br/> <input type="checkbox">가장 저렴 한 라우팅 <br/> <input type="checkbox">엘리베이터 전화 | |

## <a name="networking-and-access-to-office-365-services"></a>네트워킹 및 Office 365 서비스에 대 한 액세스

다음 표를 사용 하 여 조직의 네트워킹 세부 정보 및 사용자가 Office 365 서비스에 연결 되는 방법 (또는)을 캡처할 수 있습니다.

> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 사용자의 마이그레이션 범위 (또는 방법) <br>팀이 사무실에 있는 동안 액세스 하 고 계십니까? <br/>적용 되는 모든 것을 선택 합니다. | <input type="checkbox">라우팅된 NAT 연결 <br/> <input type="checkbox">프록시 서버 <br/> <input type="checkbox">공개 Wi-fi <br/> <input type="checkbox">관리 (공개 아님) Wi-fi <br/> <input type="checkbox">Express 경로 (Microsoft 피어 링) ||
> | 프록시 서버를 통해 Office 365에 액세스할 수 있는 경우 <br>프록시를 우회 하는 방법 | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 현재 Express 경로를 사용 하 고 있나요? | <input type="checkbox">' <br/> <input type="checkbox">아니요 <br/> <input type="checkbox">아니요, 계획 중입니다. | |
> | 네트워크 준비 평가를 수행 했습니까? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 연결할 때 VPN을 사용 해야 하는 사용자 <br>원격으로 회사 리소스 | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | VPN을 사용 하는 경우 팀 트래픽을 다음에서 제외할 수 있습니다. <br>VPN에서 Office 365 서비스에 직접 액세스 합니까? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
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
> | Lync 서버용 운영 모델은 무엇 인가요? <br>비즈니스용 Skype Server 또는 Office 365 배포 <br>오늘로? | | |
> | 현재 지원 배열에 대 한 개요를 만들 수 있습니다. <br>Lync Server, 비즈니스용 Skype Server 또는 Office 365? | | |
> | 여러 국가나 지역에 배포 하는 경우 <br>각 국가/지역에 고유한 IT/전화 통신이 있는지 <br>직원이 작업을 수행 하거나 중앙에서 관리할 수 있나요? | <input type="checkbox">국가별 작업 및 지원 <br/> <input type="checkbox">중앙 집중화 된 운영 및 지원 | |
> | [통화 품질 방법론](quality-of-experience-review-guide.md)을 팔 로우 하 고 계십니까? | <input type="checkbox">' <br/> <input type="checkbox">아니요 | |
> | 개인 또는 팀을 지정 하 여 <br>공동 작업 플랫폼의 품질 챔피언 역할 <br>사용 중인 경우 | <input type="checkbox">' <br/> <input type="checkbox">아니요 ||
> | Lync Server를 모니터링 하는 방법, Skype <br>비즈니스 서버 또는 Office 365 배포 | | |
> | 통화 품질 문제가 발생 하나요? | <input type="checkbox">'<br/> <input type="checkbox">아니요 | |
> | 어디에 교육을 제공 하는 방법과 시기 <br>새로운 서비스 및 기능에 대 한 헬프데스크 | | |

## <a name="adoption-and-readiness"></a>채택 및 준비

다음 표를 사용 하 여 조직의 현재 채택 및 준비 상태를 수집 합니다.

>
> | 리콜 | 질문 | 설명 |
> |---|---|---|
> | 의 현재 활성 사용량은 무엇 인가요? <br>비즈니스용 Skype | **__** % 총 활성 사용자와 사용 가능한 사용자 비교 | |
> | 조직에서 사용 하는 방법 <br>비즈니스용 Skype | 1:1 대화 <br>&nbsp;&nbsp; &nbsp; 메신저 <input type="checkbox"> 대화 <br>&nbsp;&nbsp; &nbsp; 전화 <input type="checkbox"> 걸기 <br>&nbsp;&nbsp; 공유 &nbsp; <input type="checkbox"><br> 모임 <br>&nbsp;&nbsp; 회의 &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; 공유 &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; &nbsp; 전화 <input type="checkbox"> 걸기 | |
> | 조직에서 사용자 채택을 사용 합니까? <br>변경 관리 팀 | <input type="checkbox">'<br/> <input type="checkbox">아니요 | |
> | 현재 기술에 대 한 성공 여부를 측정 하는 방법 <br>비즈니스용 Skype와 유사 하 게 롤아웃 | | |
> | 사용자 기준으로 사용할 백분율 <br>비즈니스용 Skype를 채택 하시 나요? | | |
> | 비즈니스용 Skype 주변의 사용자 정서? | <input type="checkbox">적합 <br/> <input type="checkbox">중립 <br/> <input type="checkbox">잘못 | |
> | 다음 중 롤아웃에 가장 잘 설명 된 내용 <br>Skype for Business에 사용 되는 전략 <br>배포가? | <input type="checkbox">광범위 한 접근: 전자 메일 캠페인 <br>&nbsp;&nbsp; &nbsp;교육 링크 <br/> <input type="checkbox">확장: 폭넓은 달성 범위와 다양 한 <br>&nbsp;&nbsp; 의 인식 캠페인 ( &nbsp;포스터, <br>&nbsp;&nbsp; 이벤트, 챔피언) &nbsp;및 교육 <br>&nbsp;&nbsp; (비디오, 사용자 안내서, &nbsp;사용자) <br/> <input type="checkbox">맞춤: 확장 됨, 대상 추가 <br>&nbsp;&nbsp; 가상 사용자의 메시지 &nbsp;및 교육 <br/> <input type="checkbox">나머지 <br>&nbsp;&nbsp; (메모 열의 세부 정보를 기록해 둡니다 &nbsp;.) | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>판단 요점</td><td><ul><li>환경 평가를 완료 해야 하는 사람은 누구 인가요?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>다음 단계</td><td><ul><li>환경 평가의 결과를 문서화 합니다.</li></ul></td></tr>
</table>

환경을 평가한 후에는 다음 단계를 진행 하세요 ( [네트워크 준비](prepare-network.md)).
