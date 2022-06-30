---
title: 환경 호환성 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 비즈니스용 Skype Microsoft Teams로의 여정을 계획할 때 자세한 환경 검색을 수행하는 방법입니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 348a0e615f5ef876bfdd62b71adb30f6bf242dd6
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562607"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Microsoft Teams 출시를 위한 환경 검색

검색은 Microsoft Teams로의 여행을 계획할 때 수행하는 첫 번째 주요 단계 중 하나입니다.

환경의 자세한 검색을 수행하여 현재 상태를 더 잘 이해하고 어려움을 드러내거나 Teams 롤아웃 실행에 방해가 될 수 있습니다.

## <a name="discovery-questionnaire"></a>검색 설문지

아래 샘플 설문지는 조직에서 Teams에서 통화 플랜 기능을 사용하여 오디오 회의 및 전화 시스템을 성공적으로 출시할 준비가 되었다는 것을 확인하는 일련의 질문을 안내합니다.

기존 공동 작업 인프라 및 Microsoft 365 또는 Office 365 조직, 네트워킹, 엔드포인트, 운영 및 채택 및 준비와 관련된 모든 문제는 환경 검색 설문지의 일부로 포함됩니다.

설문지는 여러 섹션으로 나뉘어져 있으며, 여러 주요 영역에서 Teams 배포에 대한 조직의 준비 상태를 확인합니다. 프로젝트 팀과 협력하여 요청된 정보를 가능한 한 세부 정보로 제공하여 계획 활동을 용이하게 합니다.

> [!TIP]
> 먼저 설문지를 Microsoft Word 문서에 복사할 수 있습니다. 모든 질문에 답변하고 이동하는 동안 모든 세부 정보를 캡처합니다.

### <a name="project-team"></a>프로젝트 팀

Teams 출시 프로젝트의 주요 이해 관계자에 대한 자세한 정보를 캡처합니다. 한 사람이 프로젝트 전체에서 여러 역할을 수행할 수 있습니다.

> | 역할 | 이름, 전자 메일 주소, 전화 번호 | 위치, 표준 시간대 | 설명 |
> |---|---|---|---|
> | 이그제큐티브 스폰서 | | | |
> | 프로젝트 리드 | | | |
> | 공동 작업 책임자/설계자 | | | |
> | 컨설턴트 | | | |
> | 프로젝트 관리자 | | | |
> | 변경 관리/채택 전문가 | | | |
> | 네트워크 잠재 고객 | | | |
> | 보안 책임자 | | | |
> | 전화 통신 리드 | | | |
> | 데스크톱 리드 | | | |
> | 지원/지원 센터 책임자 | | | |
> | 배포 리드 | | | |
> | 서비스 소유자 | | | |
> | 시설 리드 | | | |
> | 비디오 팀 리더 | | | |
> | 사업부 잠재 고객 | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 또는 Office 365 조직 세부 정보

이 설문지로 작업할 때 활성 Microsoft 365 또는 Office 365 조직이 있는 것이 좋습니다. 아직 Microsoft 365 또는 Office 365 조직을 활성화하거나 구성하지 않은 경우 [비즈니스용 Microsoft 365 설정 계획을 참조하세요](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

다음 표를 사용하여 Microsoft 365 또는 Office 365 조직에 대한 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 프로덕션 Microsoft 365 참고<br/>또는 Office 365 조직 이름 및 ID<br/>응답 열에 있습니다. 더 많은 항목이 있는 경우<br/>연결된 테넌트가 하나 이상<br/>조직에서 모든 ID를 기록해 둡니다. | 테넌트 이름: <br/>테넌트 ID:| |
> | 테넌트가 배포되는 지역은 무엇인가요?| | |
> | 이러한 Microsoft 365 또는 <br/>테넌트 Office 365. 다중 테넌트인가? <br/>또는 전용인가요? | <input type="checkbox"> 테 넌 트<br/> <input type="checkbox"> 전용 | |
> | 현재 사용 중인 Microsoft Online 제품은 무엇인가요? <br/>각 사용자에 대해 사용하도록 설정된 사용자 수를 확인합니다. <br/>설명 열의 서비스입니다. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">비즈니스용 Skype <br/>&nbsp;&nbsp; &nbsp; 온라인 <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">비즈니스용 OneDrive <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> 다른| |
> | Skype에 사용할 수 있는 라이선스 수준 <br/>비즈니스 온라인 사용자? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | 사용자 수 <br/>각 SKU에 대해 다음을 수행합니다. |
> | 현재 Active Directory 포리스트란? <br/>환경의 기능 수준 <br/>둘 이상의 포리스트가 있는 경우 세부 정보를 확인합니다. <br/>주석 열에 있습니다. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 디렉터리에 사용하는 항목 <br/>오늘 동기화하시겠습니까? |<input type="checkbox"> 동기화 없음(클라우드만 해당) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; 연결 <br/> <input type="checkbox"> 기타(에서 지정 <br/>&nbsp;&nbsp; &nbsp; 주석 열입니다.)| |
> | 페더레이션 ID가 현재 배포되어 있나요? <br/>(Active Directory Federation Services 또는 <br/>타사) | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 페더레이션 ID를 사용하는 경우 <br/>페더레이션 인프라? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> 타사 페더레이션 <br/>&nbsp;&nbsp; &nbsp;게이트웨이(세부 정보 참고 <br/>&nbsp;&nbsp; &nbsp;주석 열에 있습니다.) | |
> | 현재 활성 Microsoft 365를 유지 관리하는 경우<br/>또는 Office 365 테넌트의 SMTP/SIP 도메인입니다. <br/>테넌트에 연결된 대상 사용자인가요? | <input type="checkbox"> 해당 없음 - Microsoft 365 또는<br/>&nbsp;&nbsp; &nbsp;테넌트 Office 365 <br/> <input type="checkbox"> 아니요, 사용자의 SMTP/SIP <br/>&nbsp;&nbsp; &nbsp;도메인이 연결되어 있지 않습니다. <br/>&nbsp;&nbsp; &nbsp;에 테넌트가 있는 경우 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365<br/> <input type="checkbox"> 예, 사용자의 SMTP/SIP <br/>&nbsp;&nbsp; &nbsp;도메인이 연결되어 있습니다. <br/>&nbsp;&nbsp; &nbsp;에 기존 테넌트가 있는 경우 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 Office 365 | |
> | 사용자 UPN이 기본 SMTP 주소와 일치하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 <br/> <input type="checkbox"> 불규칙 | |

## <a name="existing-collaboration-platform-summary"></a>기존 공동 작업 플랫폼 요약

다음 표를 사용하여 기존 협업 플랫폼 배포에 대한 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | Microsoft Teams가 배포되었나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 비즈니스용 Skype 배포되었나요? <br/>온-프레미스 및 하이브리드 배포의 경우 <br/>버전 및 CU(누적 업데이트)를 확인합니다. <br/>설명 열의 세부 정보입니다. | <input type="checkbox"> 예, Microsoft 365 또는 <br/>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> 예, 하이브리드(포함) <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> 예, 온-프레미스 <br/> <input type="checkbox"> 예, 온라인, 전용 <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> 예, 호스팅, 전용 <br/>&nbsp;&nbsp; &nbsp;(타사) <br/> <input type="checkbox"> 예, 호스트됨, 공유됨 <br/>&nbsp;&nbsp; &nbsp;(타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | Exchange가 배포되었나요? <br/>온-프레미스 및 하이브리드 배포의 경우 <br/>주석에서 버전 및 CU 세부 정보를 기록해 둡니다. <br/>열. | <input type="checkbox"> 예, Microsoft 365 <br/> <input type="checkbox"> 예, 하이브리드(포함) <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> 예, 온-프레미스 <br/> <input type="checkbox"> 예, 온라인, 전용 <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> 예, 호스팅, 전용 <br/>&nbsp;&nbsp; &nbsp;(타사) <br/> <input type="checkbox"> 예, 호스트됨, 공유됨 <br/>&nbsp;&nbsp; &nbsp;(타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | SharePoint가 배포되었나요? <br/>온-프레미스 및 하이브리드 배포의 경우 <br/>주석에서 버전 및 CU 세부 정보를 기록해 둡니다. <br/>열. | <input type="checkbox"> 예, Microsoft 365 <br/> <input type="checkbox"> 예, 하이브리드(포함) <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 또는 <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> 예, 온-프레미스 <br/> <input type="checkbox"> 예, 온라인, 전용 <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> 예, 호스팅, 전용 <br/>&nbsp;&nbsp; &nbsp;(타사) <br/> <input type="checkbox"> 예, 호스트됨, 공유됨 <br/>&nbsp;&nbsp; &nbsp;(타사) <br/> <input type="checkbox"> 아니요, 기타 | |
> | 비즈니스용 OneDrive 배포되었나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 다른 타사 플랫폼이 배포되어 있나요? <br/>그리고 지금 사용 중입니까? 그렇다면 다음 사용자 수를 기록해 둡 <br/>이러한 플랫폼 및 다음의 사용량 세부 정보 <br/>주석 열입니다. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> 느슨하게 <br/> <input type="checkbox"> 기타(에서 지정 <br/>&nbsp;&nbsp; &nbsp; 주석 열입니다.) | 사용자 수: <br/>세부 정보:|
> | 이러한 타사에서 사용자를 이동할 계획인가? <br/>Teams에 대한 플랫폼? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 전화 통신 및 회의 솔루션이란? <br/>이 이니셔티브의 범위에 있는 사용자의 경우 | | |
> | [직접 라우팅을 지원하는 SBC가](./direct-routing-plan.md#supported-session-border-controllers-sbcs) 배포되었나요? <br/>이 이니셔티브의 범위에 있는 사무실의 경우 예인 경우<br/>메모 열의 세부 정보를 적어둡니다.| <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||

## <a name="collaboration-platform-deployment-details"></a>협업 플랫폼 배포 세부 정보

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 Teams 배포의 세부 정보를 캡처합니다. Teams를 배포하지 않은 경우 이 섹션을 건너뜁니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | Teams에 사용할 수 있는 사용자 유형은 무엇인가요? | <input type="checkbox"> 조직의 모든 사용자 <br/> <input type="checkbox"> 특정 사용자/사용자 그룹 <br/>&nbsp;&nbsp; &nbsp;(메모 열에 지정합니다.) ||
> | 사용 중인 Teams 기능 및 형식은 무엇인가요? | <input type="checkbox"> 채널 기반 대화 <br/> <input type="checkbox"> 비공개 채팅 <br/> <input type="checkbox"> 게스트 액세스 <br/> <input type="checkbox"> 채널 모임 <br/> <input type="checkbox"> 비공개 모임 <br/> <input type="checkbox"> 프라이빗 통화 <br/> <input type="checkbox"> 임시 채널 모임 <br/> <input type="checkbox"> 모임의 비디오 <br/> <input type="checkbox"> 모임에서 화면 공유 <br/> <input type="checkbox"> 오디오 회의 <br/><input type="checkbox"> 애플리케이션(앱)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> 탭<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 봇 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 커넥터<br/><input type="checkbox"> 사용자 지정 클라우드 스토리지 통합 <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; 드라이브, Egnyte <br/> <input type="checkbox"> 채널 전자 메일 통합 <br/> <input type="checkbox"> 기타(메모 열에 지정) | |
> | Teams에 배포한 애플리케이션은 무엇인가요? | | |
> | Teams 기능을 구체적으로 차단했나요? <br/>예인 경우 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||
> | 사용 중인 Teams 클라이언트는 무엇인가요? | <input type="checkbox"> 웹 <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> 리눅스 <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> 안 드 로이드 <br/> <input type="checkbox"> Windows Mobile | |
> | 팀을 만들 수 있는 권한이 있는 사람은 누구인가요? | <input type="checkbox"> 조직의 모든 사용자 <br/>&nbsp;&nbsp; &nbsp;(기본 설정) <br/> <input type="checkbox"> 특정 사용자 <br/>&nbsp;&nbsp; &nbsp;(메모 열에 지정합니다.) | |
> | Teams에서 보안 및 규정 준수 기능을 사용하고 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |

### <a name="skype-for-business-online-if-applicable"></a>비즈니스용 Skype Online(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 비즈니스용 Skype Online 배포의 세부 정보를 캡처합니다. 비즈니스용 Skype Online 배포를 배포하지 않은 경우 이 섹션을 건너뜁니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | Skype에 사용할 수 있는 사용자 유형 <br/>비즈니스 온라인? | <input type="checkbox"> 조직의 모든 사용자 <br/> <input type="checkbox"> 특정 사용자/사용자 그룹 <br/>&nbsp;&nbsp; &nbsp;(메모 열에 지정합니다.) | |
> | 현재 어떤 형식 및 기능이 있는지 <br/>현재 사용 중입니까? | <input type="checkbox"> 메신저 및 현재 상태(IM/P)<br/> <input type="checkbox"> 회의 <br/> <input type="checkbox"> 페더레이션 <br/> <input type="checkbox"> 모임 녹음/녹화 <br/> <input type="checkbox"> Microsoft 오디오 회의 <br/> <input type="checkbox"> 타사 오디오 회의(참고)<br/>&nbsp;&nbsp; &nbsp;주석 열의 세부 정보입니다.) <br/> <input type="checkbox"> 통화 플랜(이전의 PSTN 통화) <br/> <input type="checkbox"> 조직 자동 전화 교환 <br/> <input type="checkbox"> 통화 큐 | |
> | 에 대한 Skype를 구체적으로 차단했나요? <br/>비즈니스 온라인 기능? <br/>예인 경우 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 사용할 방법 또는 사용 계획 <br/>전화 시스템(이전의 클라우드 PBX)을 에 연결 <br/>PSTN? <br/>적용되는 모든 것을 선택합니다. | <input type="checkbox"> 통화 플랜(이전의 PSTN 통화) <br/> <input type="checkbox"> 온-프레미스 PSTN 연결 <br/>&nbsp;&nbsp; &nbsp;(에 대한 기존 Skype 활용 <br/>&nbsp;&nbsp; &nbsp; Business 2015 또는 Lync Server <br/>&nbsp;&nbsp; &nbsp;2013년 배포) <br/> <input type="checkbox"> 온-프레미스 PSTN 연결 <br/>&nbsp;&nbsp; &nbsp;(클라우드 커넥터 사용) | |
> | 전화 번호를 Microsoft로 이식했나요? <br/>통화 플랜 및 오디오에 적용됩니다. <br/>회의 기능. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>온-프레미스 비즈니스용 Skype(해당하는 경우)

해당하는 경우 아래 샘플 표를 사용하여 비즈니스용 Skype 배포의 세부 정보를 캡처합니다. 온-프레미스에 비즈니스용 Skype 배포하지 않은 경우 이 섹션을 건너뜁니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | Lync 또는 비즈니스용 Skype 버전 <br/> 현재 온-프레미스에 배포되어 있나요? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019 <br/><input type="checkbox">비즈니스용 Skype Cloud Connector <br/>&nbsp;&nbsp; &nbsp; 버전 | |
> | 비즈니스용 Skype Online이 구성된 하이브리드인가요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 이 환경은 3분의 1이 호스팅하고 관리합니다. <br/>파티? 예인 경우 다음의 세부 정보를 확인합니다. <br/>주석 열입니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 사용 중인 양식 및 기능 <br/>오늘? | <input type="checkbox"> 메신저 및 현재 상태(IM/P) <br/> <input type="checkbox"> 회의 <br/> <input type="checkbox"> 페더레이션 <br/> <input type="checkbox"> 모임 녹음/녹화 <br/> <input type="checkbox"> 영구 채팅/그룹 채팅 <br/> <input type="checkbox"> Microsoft 오디오 회의 <br/>&nbsp;&nbsp; &nbsp;(이전 회의로 전화 걸기) <br/>&nbsp;&nbsp; &nbsp;온-프레미스 Lync Server 또는 <br/>&nbsp;&nbsp; &nbsp;비즈니스용 Skype 배포 <br/> <input type="checkbox"> 타사 오디오 회의 <br/>&nbsp;&nbsp; &nbsp;(메모의 세부 정보를 기록해 둡니다. <br/>&nbsp;&nbsp; &nbsp;column.) <br/> <input type="checkbox">온-프레미스 사용 Enterprise Voice <br/>&nbsp; &nbsp; &nbsp;PSTN 연결 <br/> <input type="checkbox"> 을 통한 통화 플랜(이전의 PSTN 통화) <br/>&nbsp;&nbsp; &nbsp; 비즈니스용 Skype Online을 사용하는 하이브리드 | |
> | 어떤 버전의 Edge Server를 배포했나요? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">비즈니스용 Skype 서버 2015 <br/> <input type="checkbox">비즈니스용 Skype 서버 2019| |
> | Lync 또는 비즈니스용 Skype Edge가 있나요? <br/>둘 이상의 데이터 센터에 배포되었나요? <br/>예인 경우 메모 열의 세부 정보를 기록해 둡니다. | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 현재 Edge 역할이 제공하는 서비스를 선택합니다. | <input type="checkbox"> 외부 사용자 액세스(회사 사용자) <br/> <input type="checkbox"> 원격 사용자 액세스(익명) <br/>&nbsp;&nbsp; &nbsp;외부 모임 참가자) <br/> <input type="checkbox"> 페더레이션 <br/> <input type="checkbox"> 미디어 릴레이 | |
> | 다음 중 어떤 음성 통화 기능을 사용할 수 있나요? <br/>현재 종속성이 있나요? <br/>주석의 추가 종속성을 확인합니다. <br/>열. | <input type="checkbox"> 사용 중인 옵션 <br/> <input type="checkbox"> 통화 대기 <br/> <input type="checkbox"> 통화 픽업 또는 그룹 통화 픽업 <br/> <input type="checkbox"> 공용 지역 전화 또는 "핫 데스크" <br/> <input type="checkbox"> 응답 그룹 또는 헌트 그룹 <br/> <input type="checkbox"> 공유 줄 모양 <br/> <input type="checkbox"> 개인 회선 <br/> <input type="checkbox"> 음성 <br/> <input type="checkbox"> 작업을 통해 전화 걸기 <br/> <input type="checkbox"> 긴급 또는 정보 번호 <br/>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> 확장 전화 걸기 <br/> <input type="checkbox"> 자동 전화 교환 <br/> <input type="checkbox"> 구독자 액세스 <br/> <input type="checkbox"> 아날로그 디바이스 <br/> <input type="checkbox"> 팩스 <br/> <input type="checkbox"> 호출자 ID 마스킹 또는 변경 <br/> <input type="checkbox"> 위치 기반 라우팅 <br/> <input type="checkbox"> 최소 비용 라우팅 <br/> <input type="checkbox"> 엘리베이터 전화기 | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Microsoft 365 및 Office 365 서비스에 대한 네트워킹 및 액세스

다음 표를 사용하여 조직의 네트워킹 세부 정보 및 사용자가 Microsoft 365 및 Office 365 서비스에 어떻게 연결되어 있는지를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 마이그레이션 범위에서 사용자를 수행하는 방법(또는 방법) <br/>Office에 있을 때 Teams에 액세스하시겠습니까? <br/>적용되는 모든 것을 선택합니다. | <input type="checkbox"> 라우팅된 NAT 연결 <br/> <input type="checkbox"> 프록시 서버 <br/> <input type="checkbox"> 공용 Wi-Fi <br/> <input type="checkbox"> 관리되는(공용 아님) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp;(Microsoft 피어링) ||
> | Microsoft 365 또는 Office 365 대한 액세스 권한이<br/>프록시 서버, 프록시를 바이패스하는 방법이 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | ExpressRoute가 현재 사용되고 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 <br/> <input type="checkbox"> 아니요, 하지만 계획 중입니다. | |
> | 네트워크 준비 평가를 수행했나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 사용자가 연결할 때 VPN을 사용해야 합니까? <br/>회사 리소스를 원격으로 사용하시겠습니까? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | VPN을 사용하는 경우 Teams 트래픽을 제외할 수 있습니다. <br/>Microsoft 365 및 Office 365 Services에 직접 액세스하기 위한 VPN | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 네트워크에서 QoS를 지원하나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | Teams 오디오 및 비디오 트래픽의 우선 순위를 지정할 수 있나요? <br/>고품질 환경을 구동하려면? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 지역 내의 모든 위치에 인터넷 송신이 있나요? <br/>또는 인터넷 송신이 전체 지역에 중앙 집중화되어 있나요? | <input type="checkbox"> 인터넷에 대한 지역 액세스 <br/> <input type="checkbox"> 에 대한 중앙 집중식 액세스 <br/>&nbsp;&nbsp; &nbsp;인터넷 | |

## <a name="endpoints"></a>끝점

다음 표를 사용하여 사용 중인 클라이언트 및 엔드포인트의 세부 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 사용자가 사용하는 데스크톱 OS는 무엇인가요? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac(주석 열에서 버전을 지정합니다.) <br/> <input type="checkbox"> Linux(주석 열에서 배포 지정) <br/><input type="checkbox"> 기타(메모 열의 세부 정보를 적어 둡니다.) | |
> | 배포되는 Microsoft Office 버전 <br/>이 장치에? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Mac용 Office 2011 <br/> <input type="checkbox">Mac용 Office 2016 <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 적어 둡니다.) | |
> | 사용 중인 Office 배포 기술 <br/>조직에서? | <input type="checkbox"> MSI <br/> <input type="checkbox"> 간편 실행 | |
> | 허용 및 지원되는 모바일이란? <br/>사용 중인 플랫폼은 무엇인가요? <br/>적용되는 모든 것을 선택합니다. | <input type="checkbox"> Windows <br/> <input type="checkbox"> 모바일 <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> 안 드 로이드 <br/> <input type="checkbox"> 기타(메모 열의 세부 정보를 적어 둡니다.) | |
> | 모바일 디바이스는 어떻게 제공하나요? <br/>적용되는 모든 것을 선택합니다. | <input type="checkbox"> 회사 디바이스 <br/> <input type="checkbox"> 사용자 고유의 디바이스 가져오기 | |
> | 사용자가 현재 액세스하는 데 사용하는 디바이스 <br/>음성 및 회의 서비스 <br/>(핸드셋, 헤드셋, 휴대폰, 비디오)? | | |

## <a name="operations"></a>운영

다음 표를 사용하여 환경의 운영 측면에 대한 세부 정보를 캡처합니다.

> | 질문 | 대답 | 설명 |
> |---|---|---|
> | Lync Server에 대한 작업 모델은 무엇인가요? <br/>비즈니스용 Skype 서버, Microsoft 365 배포, <br/>또는 오늘 배포를 Office 365? | | |
> | 에 대한 현재 지원 배열을 간략하게 설명할 수 있나요? <br/>Lync Server, 비즈니스용 Skype 서버, Microsoft 365, <br/>또는 Office 365? | | |
> | 여러 국가 또는 지역에 배포하는 경우 <br/>각 국가/지역에 자체 IT/전화 통신이 있나요? <br/>함께 작업할 직원 또는 중앙에서 관리되나요? | <input type="checkbox"> 지역 운영 및 지원 <br/> <input type="checkbox"> 중앙 집중식 작업 및 지원 | |
> | 통화 품질 방법론을 따르고 있나요? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 | |
> | 개인 또는 팀을 <br/>협업 플랫폼에 대한 품질 챔피언 역할 <br/>사용 중입니까? | <input type="checkbox"> 예 <br/> <input type="checkbox"> 아니요 ||
> | Lync Server, Skype for를 모니터링하는 방법 <br/>비즈니스 서버, Microsoft 365 배포 또는 <br/>배포를 Office 365? | | |
> | 통화 품질 문제가 발생하나요? | <input type="checkbox"> 예<br/> <input type="checkbox"> 아니요 | |
> | 학습 방법 및 시기 <br/>새 서비스 및 기능에 대한 기술 지원팀? | | |

## <a name="adoption-and-readiness"></a>채택 및 준비 상태

다음 표를 사용하여 조직의 현재 채택 및 준비 상태를 캡처합니다.

>
> | 질문 | 대답 | 설명 |
> |---|---|---|
> | 의 현재 활성 사용 현황은 무엇인가요? <br/>비즈니스용 Skype? | **__** 전체 활성 사용자 수와 활성화된 사용자 비교 | |
> | 조직에서 사용하는 방법 <br/>비즈니스용 Skype? | 1:1 대화 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 호출 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br/> 모임 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 회의<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 공유<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> 호출 | |
> | 조직에 사용자 채택이 있나요? <br/>및 변경 관리 팀? | <input type="checkbox"> 예<br/> <input type="checkbox"> 아니요 | |
> | 현재 기술의 성공을 측정하는 방법 <br/>비즈니스용 Skype 같은 롤아웃? | | |
> | 사용자 기반의 백분율은 다음과 입니다. <br/>비즈니스용 Skype 채택? | | |
> | 비즈니스용 Skype 대한 사용자 감정은 무엇인가요? | <input type="checkbox"> 좋은 <br/> <input type="checkbox"> 중립 <br/> <input type="checkbox"> 나쁜 | |
> | 다음 중 롤아웃을 가장 잘 설명하는 것은 다음과 같습니다. <br/>비즈니스용 Skype 데 사용되는 전략 <br/>배포? | <input type="checkbox"> 광범위한 범위: 전자 메일 캠페인 <br/>&nbsp;&nbsp; &nbsp;학습 링크 <br/> <input type="checkbox"> 확장됨: 광범위한 범위와 다양한 범위 <br/>&nbsp;&nbsp; &nbsp;인식 캠페인(포스터, <br/>&nbsp;&nbsp; &nbsp;이벤트, 챔피언) 및 교육 <br/>&nbsp;&nbsp; &nbsp;(비디오, 사용자 가이드, 직접) <br/> <input type="checkbox"> 맞춤형: 확장됨 및 대상 지정 <br/>&nbsp;&nbsp; &nbsp;가상 사용자의 메시징 및 교육 <br/> <input type="checkbox"> 다른 <br/>&nbsp;&nbsp; &nbsp;(메모 열의 세부 정보를 기록해 둡니다.) | |
