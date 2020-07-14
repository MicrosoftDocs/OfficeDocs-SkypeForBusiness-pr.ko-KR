---
title: 보안 및 규정 준수 개요
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: 감사 및 보고, 준수 콘텐츠 검색, eDiscovery 등의 Microsoft 팀의 보안 및 규정 준수 기능에 대해 간략하게 설명 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d4c19de7fdc8bfc4ed0608841613514d09fae27
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121388"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft 팀의 보안 및 규정 준수

> [!IMPORTANT]
> **모든 사람이 공동으로 작업 하는 동안 보안**을 유지 하는 가장 좋은 방법을 알아보려면 다음 문서를 참조 하세요.
>  - [보안 팀이 재택 근무를 지원하는 상위 12가지 작업](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [VPN 분할 터널링을 사용하여 원격 사용자를 위해 Microsoft 365 혹은 Office 365 연결 최적화](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 업데이트 됨 2020 년 4 월 2 일: [팀 보안 가이드](teams-security-guide.md)


Microsoft 팀은 고객에 게 제공 되는 고급 보안 및 규정 준수 기능을 제공 하는 Microsoft 365 및 Office 365 하이퍼 규모의 엔터프라이즈 등급 클라우드를 기반으로 합니다. Microsoft 365 또는 Office 365의 보안 계획에 대 한 자세한 내용은 [보안 로드맵](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) 을 시작 하는 것이 좋습니다. Microsoft 365 또는 Office 365의 준수 계획에 대 한 자세한 내용은 [보안 및 준수 계획](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) 문서를 사용 하 여 시작할 수 있습니다.


이 문서에서는 팀 관련 보안 및 준수에 대 한 자세한 정보를 제공 합니다. 보안 및 규정 준수에 대 한 다음 Microsoft 기술 비디오를 놓치지 마세요.

- [Microsoft 팀의 주요 기능: 보안 및 준수](https://youtu.be/91lHNKVVvQ4) (12:42 분)
- [Microsoft 팀의 보안 및 규정 준수 제어](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 분)

> [!IMPORTANT]
> Microsoft 365 또는 Office 365의 고객은 데이터를 소유 하 고 제어 합니다. Microsoft는 귀하가 구독 한 서비스를 제공 하는 것 외에는 데이터를 사용 하지 않습니다. 서비스 제공 업체는 전자 메일, 문서 또는 팀이 광고 또는 서비스와 관련이 없는 목적을 검사 하지 않습니다. Microsoft는 업로드 된 콘텐츠에 액세스할 수 없습니다. Microsoft 365의 OneDrive 및 SharePoint와 마찬가지로 고객 데이터는 테 넌 트 내에 남아 있습니다. [Microsoft 보안 센터](https://microsoft.com/trustcenter)에서 신뢰 및 보안 관련 정보에 대 한 자세한 내용을 확인할 수 있습니다. 팀은 Microsoft 보안 센터와 동일한 지침 및 원칙을 따릅니다.

## <a name="security"></a>보안

팀은 팀 전체 및 조직 차원의 두 요소 인증, Active Directory를 통한 single sign-on, 전송 및 남은 데이터의 암호화를 적용 합니다. 파일은 SharePoint에 저장 되며 SharePoint 암호화를 통해 지원 됩니다. 노트는 OneNote에 저장 되며 OneNote 암호화를 통해 지원 됩니다. OneNote 데이터는 팀 SharePoint 사이트에 저장 됩니다. 위 키 탭을 사용 하 여 노트를 작성 하 고 해당 콘텐츠도 팀 SharePoint 사이트 내에 저장할 수도 있습니다.

인증 및 팀에 대 한 자세한 내용을 확인 하기 위해 [id 모델 및 인증](identify-models-authentication.md) 을 읽고, [최신 인증 작동 방식](sign-in-teams.md) 에서는 최신 인증을 사용 하는 것이 특히 도움이 됩니다.

팀은 SharePoint, OneNote, Exchange 등과의 협력 관계를 사용 하기 때문에 Microsoft 365 또는 Office 365의 모든 보안을 더욱 안전 하 게 관리할 수 있습니다. 자세한 내용은 [보안을 강화 하기 위해 Microsoft 365 또는 Office 365 조 직을 구성 하는 방법을 참고 하세요](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> 현재 [개인 채널](private-channels.md) 은 제한 된 보안 및 규정 준수 기능을 지원 합니다. 개인 채널의 모든 보안 및 규정 준수 기능에 대 한 지원은 곧 제공 될 예정입니다.

### <a name="advanced-threat-protection-atp"></a>ATP (고급 위협 방지)

Microsoft 팀은 콘텐츠 관리용 팀과 통합 하는 응용 프로그램 및 SharePoint 및 OneDrive와 함께 ATP (Advanced Threat protection)를 사용할 수 있습니다. ATP를 사용 하 여 이러한 응용 프로그램의 콘텐츠가 악의적인 지 여부를 확인 하 고 사용자 액세스에서이 콘텐츠를 차단할 수 있습니다.

검색 후에는 Microsoft 365 또는 Office 365에서 선택한 설정에 영향을 받는 콘텐츠를 관리 하는 방법에 대해 설명 합니다. 모든 응용 프로그램에서 ATP를 구성 하 고 더 읽기 위해 [SharePoint, OneDrive 및 Microsoft 팀 문서에 대 한 atp](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 는 시작 방법에 대 한 자세한 정보를 얻을 것을 적극 권장 합니다.

### <a name="safe-links"></a>안전한 링크

이번에는 Microsoft 팀에서 ATP (고급 위협 방지)에 대 한 안전한 링크를 사용할 수 없으며, 이제 기술 채택 프로그램을 통해 [공개 미리 보기](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) 를 사용 하 고, 일반 사용이 가능한 경우 릴리스 날짜가 설정 되지 않은 경우, 해당 시간이 되 면이 문서를 업데이트 합니다. Microsoft 365 또는 Office 365 안전한 링크에 대 한 자세한 내용은 [ATP 안전한 링크](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)를 검토 하세요. ATP 안전한 링크는 [Atp 계획 1 및 Atp 계획 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)에서 사용할 수 있습니다.

### <a name="safe-attachments"></a>안전한 첨부 파일

안전한 첨부 파일은 악의적인 첨부 파일을 확인 하 고 검색 하 여 사용자 보안을 강화 하기 위해 디자인 된 기능입니다. 전역 또는 보안 관리자는 이러한 의심 스러운 첨부 파일을 사용자에 게 보내고, 클릭 하 고, 처리 하지 않도록 하는 [정책을](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) 만듭니다. 안전한 첨부 파일 보호는 SharePoint, OneDrive 및 Microsoft 팀에서 사용할 수 있으며, Microsoft 365 또는 Office 365 [고급 위협 보호 계획 1 및 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) 에는이 기능이 있습니다. 안전한 첨부 파일과 [이를 통해 조직을 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)하는 방법에 대 한 자세한 내용을 확인 하세요.

### <a name="how-conditional-access-policies-work-for-teams"></a>팀에 조건부 액세스 정책이 작동 하는 방식

Microsoft 팀은 모임, 일정, interop 채팅, 파일 공유 등의 핵심 생산성 시나리오를 위해 Exchange Online, SharePoint, 비즈니스용 Skype Online에 크게 의존 합니다. 이러한 클라우드 앱에 대해 설정 된 조건부 액세스 정책은 사용자가 모든 클라이언트에서 Microsoft 팀에 직접 로그인 할 때 Microsoft 팀에 적용 됩니다.

Microsoft 팀은 Azure Active Directory 조건부 액세스 정책의 클라우드 앱으로 별도로 지원 됩니다. Microsoft 팀 클라우드 앱에 대해 설정 된 조건부 액세스 정책은 사용자가 로그인 할 때 Microsoft 팀에 적용 됩니다. 그러나 Exchange Online 및 SharePoint 같은 다른 앱에 대 한 올바른 정책이 없으면 사용자가 계속 해당 리소스에 액세스할 수 있습니다. Azure 포털에서 조건부 액세스 정책을 설정 하는 방법에 대 한 자세한 내용은 [Azure Active Directory 빠른](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)시작을 참조 하세요.

Windows 및 Mac 용 Microsoft 팀 데스크톱 클라이언트는 최신 인증을 지원 합니다. 최신 인증은 office 용 ADAL (Active Directory 인증 라이브러리)을 플랫폼 전체의 Microsoft Office 클라이언트 응용 프로그램에 따라 로그인 합니다.

Microsoft 팀 데스크톱 응용 프로그램에서 AppLocker를 지원 합니다.  AppLocker 전제 조건에 대 한 자세한 내용은 [applocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)를 사용 하기 위한 요구 사항을 참조 하세요.

## <a name="compliance"></a>충족

팀에는 채널, 채팅, 첨부 파일, 보존 정책, 데이터 손실 방지 (DLP), 채널에 대 한 eDiscovery 및 유효 유지, 채팅 및 파일, 감사 로그 검색, Microsoft Intune의 모바일 응용 프로그램 관리에 대 한 통신 준수를 비롯 하 여 규정 준수 영역에 도움이 되는 다양 한 정보가 있습니다. 아래의 모든 항목에 대 한 정보를 제공 하 고 [Microsoft 365 준수 센터로](https://compliance.microsoft.com) 이동 하 여 이러한 설정을 관리할 수 있습니다.

### <a name="information-barriers"></a>정보 장벽

정보 장애물은 사용자 또는 그룹이 서로 통신 하는 것을 방지 (비즈니스에 필요 하지 않은 경우 또는 해당 작업을 차단 하는 규정 이유) 할 때와 같은 작업을 수행 하기 위해 팀 관리자에 게 제공 되며, 조회 및 eDiscovery (아래 내용 참조)와 관련 된 정책을 설정할 수도 있습니다. 이러한 정책은 1:1 채팅, 그룹 채팅 또는 팀 수준의 사용자에 게 영향을 줄 수 있습니다.

이 항목에 대 한 자세한 [내용은 Microsoft 팀의 정보 장벽](information-barriers-in-teams.md)으로 이동 하세요.

### <a name="communication-compliance"></a>통신 준수

Microsoft 365의 통신 준수를 통해 사용자를 범위 내 정책에 추가 하 여 악의적인 언어, 중요 한 정보, 내부 및 규제 표준 관련 정보에 대 한 Microsoft 팀 통신을 검사 하도록 구성할 수 있습니다. 공용 및 개인 팀 채널, 개인 채팅, 첨부 파일 모두에 대 한 채팅 통신 및 관련 첨부 파일을 검색 하 여 조직의 통신 위험을 최소화할 수 있습니다. 부적절 한 팀 통신을 감지 하 고 캡처하고 작업을 수행 하는 데 도움이 되도록 정책을 구성할 수 있는 방법에 대 한 자세한 내용은 [Microsoft 365의 통신 준수](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)를 참조 하세요.

### <a name="retention-policies"></a>보존 정책

Microsoft 팀의 보존 정책을 사용 하면 조직에서 중요 한 데이터를 유지 하 고, 규정, 법률, 비즈니스 또는 기타 이유를 유지 하 고, 유지 하는 것과 관련이 없는 콘텐츠 및 통신을 제거할 수도 있습니다. 보존 정책을 사용 하 여 일정 기간 동안 데이터를 보관 한 다음 삭제할 수도 있습니다. 자세한 내용은 [Microsoft 팀 문서의 보존 정책](retention-policies.md) 항목을 참조 하세요.

### <a name="data-loss-prevention-dlp"></a>DLP (데이터 손실 방지)

Microsoft 팀의 DLP (데이터 손실 방지)는 물론 Microsoft 365 또는 Office 365의 대규모 DLP 스토리는 중요 한 문서 및 데이터를 보호 하는 데 있어 비즈니스 준비가 진행 되 고 있는 것을 중심으로 합니다. 메시지 또는 문서의 중요 한 정보에 대해 염려 하는 경우 DLP 정책은 사용자가 중요 한 데이터를 잘못 된 사용자와 공유 하지 못하도록 할 수 있습니다.

팀에서 데이터 손실 방지에 대 한 자세한 내용은 [Microsoft 팀에 대 한 DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)를 검토 하세요. O365 DLP 문제에 대 한 좋은 문서는 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)에 대 한 개요입니다.

### <a name="ediscovery"></a>eDiscovery

전자적 검색 또는 eDiscovery는 법 슈트 또는 조사에서 생산 요청에 대 한 응답으로 ESI (전자적으로 저장 된 정보)를 식별, 수집 및 생성 하는 전자적 측면입니다. 접근 권한 값에는 사례 관리, 유지, 검색, 분석, 팀 데이터 내보내기 등이 포함 됩니다. 여기에는 채팅, 메시지 및 파일, 모임 및 통화 요약도 포함 됩니다. 팀 모임 및 통화의 경우, 모임 및 통화에 발생 한 이벤트에 대 한 요약이 만들어져서 eDiscovery에서 사용할 수 있게 됩니다.

보안 센터 및 준수 센터에서 Microsoft 365 또는 Office 365 eDiscovery을 수행 하는 방법에 대 한 자세한 내용과 팀 콘텐츠에 대 한 규정 준수 콘텐츠 검색을 실행 하는 방법에 대 한 자세한 내용은 아래 링크를 참고 하세요.

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

자세한 내용은 팀 관련 문서, [게스트 대 게스트 채팅의 eDiscovery](eDiscovery-investigation.md)를 참조 하세요.

고객은 필요에 따라 eDiscovery 또는 [고급 ediscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) 를 활용할 수 있습니다. 다음 표에서는 두 가지 사이의 차이점에 대해 간략하게 설명 합니다.

| |eDiscovery  |고급 eDiscovery  |
|---------|---------|---------|
|사례 관리     |X        |X         |
|액세스 제어  |X         |X         |
|콘텐츠 검색     |X         | X        |
|보류 (s)   |X         | X        |
|내보내기     |X         |X         |
|중복 검색     |-         |X         |
|기계 학습으로 관련성 검색    |-         |X         |
|비구조적 데이터 분석      |-         |X         |

### <a name="legal-hold"></a>법률 보류

소송 중에는 사용자에 연결 된 모든 데이터 (custodian) 또는 팀을 변경 되지 않은 상태로 유지 하 여 대/소문자에 대 한 증거로 사용할 수 있어야 할 수 있습니다. 이 작업은 사용자 (사용자 사서함) 또는 법률에 따라 팀 구성원을 배치 하 여 수행할 수 있습니다. 팀 법률을 유지 하기 위해 팀의 사서함을 다음 보류에 추가할 수 있습니다.

- 원본 위치 유지 (대상 쿼리 또는 필터링 된 콘텐츠를 통한 사서함 또는 사이트 모음의 하위 집합은 보류 중) 또는
- 소송 보존 (전체 사서함 또는 사이트 모음이 보류 상태에 배치 됨)

두 경우 모두 보류를 설정한 후 최종 사용자가 그룹 사서함에 있는 채널 메시지를 삭제 하거나 편집 하더라도 해당 콘텐츠의 변경 되지 않은 복사본이 eDiscovery 검색을 통해 유지 관리 되 고 사용할 수 있도록 보장 합니다. 법률 보존은 일반적으로 eDiscovery 사례의 컨텍스트 내에서 적용 됩니다.

Microsoft 365 규정 준수 센터의 보존 및 유지에 대 한 자세한 내용을 이해 하는 데는 [보존 정책 문서의 개요](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 를 참조 하세요. 법적 고 지에 대 한 팀 관련 정보에 대 한 자세한 내용은 [Microsoft 팀 사용자 또는 팀에](legal-hold.md) 게 자세한 내용에 대 한 법률 유지 문서를 준비 합니다.

### <a name="compliance-content-search"></a>콘텐츠 검색 준수

콘텐츠 검색을 사용 하 여 풍부한 필터링 기능을 통해 모든 팀 데이터를 검색할 수 있습니다. 결과 데이터를 규정 준수 및 소송 지원을 위해 특정 컨테이너에 내보낼 수 있습니다. 이 작업은 eDiscovery 사례와 관계 없이 수행할 수 있습니다. 이렇게 하면 규정 준수 관리자가 모든 사용자에 게 팀 데이터를 수집 하 고 추가 처리를 위해 검토 하 고 내보낼 수 있습니다. Microsoft 365 준수 센터에서 Microsoft 팀 및 기타 Microsoft 365 또는 Office 365 콘텐츠에 대 한 규정 준수 콘텐츠 검색을 수행 하는 방법에 대해 자세히 알아보려면이 [콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/content-search) 문서를 참조 하세요.

> [!TIP]
> 콘텐츠 검색을 사용 하면 필요한 경우 채팅 및 채널 메시지, 모임, 통화와 같은 Microsoft 팀의 콘텐츠만 필터링 할 수 있습니다.

콘텐츠 검색 구성에 대 한 추가 팀 관련 정보를 보려면 [Microsoft 팀의 콘텐츠 검색](content-search.md) 문서를 검토 하세요.

### <a name="auditing-and-reporting"></a>감사 및 보고

감사 로그 검색은 Microsoft 365 준수 센터에 바로 연결 되며, 다양 한 감사 시간 내에 관리 사용 및 조사를 위해 작업 부하 또는 제네릭 이벤트 집합을 내보낼 수 있도록 허용 하 여 감사 이벤트에 대 한 보고를 할 수 있는 기능을 제공 합니다. Microsoft 365 준수 센터 내에서 모든 감사 로그 데이터에 대 한 알림을 설정 하 고 추가 분석을 위해이 데이터를 필터링 하 고 내보낼 수 있습니다. Microsoft 365 또는 Office 365에 대 한 감사 로그 검색을 수행 하는 방법에 대해 자세히 알아보려면 [감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 문서를 참조 하세요. Microsoft 365 규정 준수 센터에서 Microsoft 팀 이벤트를 검색 하는 방법에 대해 자세히 알아보려면 [팀에서 감사를 사용](audit-log-events.md) 하는 방법에 대해서도 검토할 수 있습니다.

## <a name="privacy"></a>프라이버시

Microsoft에서 데이터를 보호 하는 것은 가장 중요 한 사항입니다. 개인정보 보호 정책에 대 한 자세한 내용은 [Microsoft에서 개인정보 보호](https://www.microsoft.com/trust-center/privacy)정책을 참조 하세요.

## <a name="information-protection-architecture"></a>정보 보호 아키텍처

다음 그림은 팀 파일 및 메시지에 대 한 Exchange 및 SharePoint 둘 다에 팀 데이터를 수집 하는 흐름을 나타냅니다.

![Exchange 및 SharePoint에 대 한 팀 데이터 워크플로 다이어그램](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

다음 그림은 Exchange로의 팀 모임 및 통화 데이터 수집 흐름을 나타냅니다.

![팀 모임 워크플로 및 Exchange로 데이터 호출에 대 한 다이어그램](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 팀 콘텐츠를 검색 하는 데 최대 24 시간이 걸릴 수 있습니다.

## <a name="licensing"></a>라이선싱

정보 보호 기능을 사용 하는 경우 Microsoft 365 구독, Office 365 구독, 관련 독립 실행형 라이선스를 통해 제공 되는 기능 집합을 확인할 수 있습니다.

보안 및 규정 준수를 위해 기능을 구현 하는 데 필요한 라이선스를 확인 하는 방법에 대 한 자세한 내용은 [Office 365 또는 Microsoft 365 라이선스](https://download.microsoft.com/download/8/7/7/877B1713-671E-43AA-BB79-AF8478C64AFF/Licensing-Microsoft-365.pdf)를 참조 하세요.

> [!NOTE]
> 보안 & 준수 센터에서 콘텐츠 검색 및 eDiscovery 기능을 사용 하도록 설정할 필요는 없습니다.

## <a name="location-of-data-in-teams"></a>Teams의 데이터 위치

팀의 데이터는 Microsoft 365 또는 Office 365 조직과 연결 된 지리적 영역에 위치 합니다. 현재 지원 되는 영역을 확인 하려면 [Microsoft 팀에서 데이터의 위치](location-of-data-in-teams.md)를 검토 하세요.

테 넌 트에 대 한 데이터가 들어 있는 영역을 확인 해야 하는 경우 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home)  >  **설정**  >  **조직 프로필로**이동 합니다. 아래로 스크롤하여 **데이터 위치로**이동 합니다.

![관리 센터의 팀을 비롯 한 데이터 위치 표 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>준수 표준

팀은 [iso 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001), [iso 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018), [SSAE16 soc 1 및 Soc 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc), [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)및 [EU 모델 절 (EUMC)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses)표준을 사용 합니다. Microsoft 규정 준수 프레임 워크에서 microsoft 365 및 Office 365 응용 프로그램 및 서비스를 네 가지 범주로 분류 합니다. 각 범주는 Microsoft 365 또는 Office 365 서비스에 대해 충족 해야 하는 특정 준수 약정 또는 해당 범주에 나열 되는 관련 Microsoft 서비스에 의해 정의 됩니다.

세부 정보는 [데이터 보호 리소스](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)에서 찾을 수 있습니다. 또한 팀은 클라우드 보안 동맹 준수를 지원 합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 보안](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 준수](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft 준수 제공](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
