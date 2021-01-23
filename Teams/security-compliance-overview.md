---
title: 보안 및 규정 준수 개요
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: 개인 정보 보호 및 암호화, 감사 및 보고 등을 포함한 Microsoft Teams 보안 및 규정 준수 기능에 대한 개요입니다.
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
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9ee7d3d4cd7d877925b649bb3f3b6a8da72ddf0
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937440"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams의 보안 및 규정 준수

> [!IMPORTANT]
> **COVID-19가** 발발하는 동안 모든 사람이 집에서 작업하는 동안 보안을 가장 잘 보장하는 방법을 알아보고 다음 문서를 읽어보아야 합니다.
>  - [보안 팀이 재택 근무를 지원하는 상위 12가지 작업](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [VPN 분할 터널링을 사용하여 원격 사용자를 위해 Microsoft 365 혹은 Office 365 연결 최적화](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 2020년 4월 2일 업데이트: [Teams 보안 가이드](teams-security-guide.md)


Microsoft Teams는 Microsoft 365 및 Office 365 대규모 엔터프라이즈급 클라우드를 구축하여 고객이 기대하는 고급 보안 및 규정 준수 기능을 제공합니다. Microsoft 365 또는 Office 365의 보안 계획에 대한 자세한 내용은 보안 로드맵을 시작하는 것이 좋습니다. [](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) Microsoft 365 또는 Office 365의 규정 준수 계획에 대한 자세한 내용은 보안 및 규정 준수 계획 문서에서 시작할 [수](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) 있습니다.


이 문서에서는 Teams 관련 보안 및 규정 준수에 대한 추가 정보를 제공합니다. 보안 및 규정 준수에 대한 다음 Microsoft 역학 비디오를 놓치지 마세요.

- [IT용 Microsoft Teams Essentials: 보안 및 규정](https://youtu.be/91lHNKVVvQ4) 준수(12:42분)
- [보안 및 규정](https://www.youtube.com/watch?v=Km4T4hMM__k) 준수를 위한 Microsoft Teams 컨트롤(10:54분)

> [!IMPORTANT]
> Microsoft 365 또는 Office 365 고객은 데이터를 소유하고 제어합니다. Microsoft는 구독한 서비스를 제공하는 것 이외에는 데이터를 사용하지 않습니다. 서비스 공급자는 전자 메일, 문서 또는 팀에서 광고 또는 서비스 관련이 없는 목적으로 검색하지 않습니다. Microsoft는 업로드된 콘텐츠에 액세스할 수 없습니다. Microsoft 365의 OneDrive 및 SharePoint와 마찬가지로 고객 데이터는 테넌트 내에 있습니다. Microsoft 보안 센터에서 신뢰 및 보안 관련 정보에 대한 자세한 정보를 확인할 [수 있습니다.](https://microsoft.com/trustcenter) Teams는 Microsoft 보안 센터와 동일한 지침과 원칙을 따르고 있습니다.

## <a name="security"></a>보안

Teams는 팀 전체 및 조직 전체의 2단계 인증, Active Directory를 통한 Single Sign-On, 전송 중 및 미사용 데이터 암호화를 적용합니다. 파일은 SharePoint에 저장되고 SharePoint 암호화를 통해 백업됩니다. 노트는 OneNote에 저장되고 OneNote 암호화를 통해 백업됩니다. OneNote 데이터는 팀 SharePoint 사이트에 저장됩니다. 위키 탭은 노트를 찍는 데도 사용할 수 있으며, 해당 콘텐츠는 팀 SharePoint 사이트 내에 저장됩니다.

ID [모델 및 인증을](identify-models-authentication.md) 읽고 인증 및 [](sign-in-teams.md) Teams에 대한 자세한 정보를 얻을 수 있으며 최신 인증이 작동하는 방식은 특히 최신 인증에 도움이 됩니다.

Teams는 SharePoint, OneNote, Exchange 등에서 작동하기 때문에 Microsoft 365 또는 Office 365 전체에서 보안을 관리하는 데 편해야 합니다. 자세한 내용은 보안 강화를 위해 [Microsoft 365 또는 Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)조직을 구성하는 방법을 읽어보아야 합니다.

> [!NOTE]
> 현재 개인 [채널은](private-channels.md) 제한된 보안 및 규정 준수 기능을 지원하고 있습니다. 비공개 채널에서 보안 및 규정 준수 기능의 전체 집합에 대한 지원이 곧 제공될 예정입니다.

### <a name="advanced-threat-protection-atp"></a>ATP(Advanced Threat Protection)

ATP(Advanced Threat Protection)는 콘텐츠 관리를 위해 Teams와 통합되는 SharePoint 및 OneDrive 응용 프로그램과 함께 Microsoft Teams에서 사용할 수 있습니다. ATP를 사용하면 이러한 애플리케이션의 콘텐츠가 본질적으로 악의적인지 판단하고 사용자 액세스로부터 이 콘텐츠를 차단할 수 있습니다.

감지 후 영향을 받는 콘텐츠를 관리하는 방식은 Microsoft 365 또는 Office 365에서 선택한 설정에 따라 다를 수 있습니다. ATP 구성과 관련한 모든 응용 프로그램을 고려하는 것이 좋습니다. 자세한 내용을 읽으 위해 [SharePoint, OneDrive 및 Microsoft Teams용 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 문서에는 시작하는 방법에 대한 자세한 정보가 있습니다.

### <a name="safe-links"></a>안전 링크

현재 Microsoft Teams에서는 ATP(Advanced Threat Protection) 안전 링크를 사용할 수 없는 [](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) 반면, 이제는 TAP(기술 채택 프로그램)을 통해 공개 미리 보기로 제공되어 있으며 일반 공급에 대한 릴리스 날짜가 설정되지 않은 경우 해당 시간이 도착하면 이 문서를 업데이트할 것입니다. 그 동안 Microsoft 365 또는 Office 365 안전 링크에 대한 자세한 내용은 ATP 안전 링크를 [검토하세요.](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) ATP 안전 링크는 [ATP 계획 1 및 ATP 계획 2에서 사용할 수 있습니다.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>안전한 첨부 파일

안전한 첨부 파일은 악의적인 첨부 파일을 확인하고 검색하여 사용자 보안을 강화하도록 설계된 기능입니다. 전역 또는 보안 관리자는 [](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) 이러한 의심되는 악성 첨부 파일을 처리하여 사용자에게 전송, 클릭 및 작업하지 못하게 하는 정책을 만들 수 있습니다. 안전한 첨부 파일 보호는 SharePoint, OneDrive 및 Microsoft Teams에서 사용할 수 있으며, Microsoft 365 또는 Office 365 Advanced Threat Protection 계획 [1과 2에는](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) 이 기능이 있습니다. 안전한 첨부 파일에 대한 자세한 정보 및 여기에서 조직을 보호하는 방법에 대해 [자세히 읽어보세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="how-conditional-access-policies-work-for-teams"></a>Teams의 조건부 액세스 정책 작동 방식

Microsoft Teams는 모임, 일정, 상호 채팅, 파일 공유와 같은 핵심 생산성 시나리오를 위해 Exchange Online, SharePoint 및 비즈니스용 Skype Online에 크게 의존합니다. 이러한 클라우드 앱에 대해 설정된 조건부 액세스 정책은 사용자가 모든 클라이언트에서 Microsoft Teams에 직접 로그인할 때 Microsoft Teams에 적용됩니다.

Microsoft Teams는 Azure Active Directory 조건부 액세스 정책에서 클라우드 앱으로 별도로 지원됩니다. Microsoft Teams 클라우드 앱에 대해 설정된 조건부 액세스 정책은 사용자가 로그인할 때 Microsoft Teams에 적용됩니다. 그러나 Exchange Online 및 SharePoint와 같은 다른 앱에서 올바른 정책이 없는 경우 사용자는 해당 리소스에 직접 액세스할 수 있습니다. Azure Portal에서 조건부 액세스 정책을 설정하는 자세한 내용은 Azure Active Directory 빠른 [시작으로 이동하세요.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Windows 및 Mac용 Microsoft Teams 데스크톱 클라이언트는 최신 인증을 지원합니다. 최신 인증을 통해 Azure ADAL(Active Directory 인증 라이브러리)을 기반으로 로그인하여 플랫폼에서 Microsoft Office 애플리케이션을 만들 수 있습니다.

Microsoft Teams 데스크톱 애플리케이션은 AppLocker를 지원합니다.  AppLocker의 전제 조건에 대한 자세한 내용은 다음을 참조하세요. [AppLocker를](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)사용하기 위한 요구 사항.

## <a name="compliance"></a>규정 준수

Teams에는 채널, 채팅 및 첨부 파일에 대한 통신 규정 준수, 보존 정책, DLP(데이터 손실 방지), eDiscovery 및 채널에 대한 eDiscovery 및 법적 보존, 채팅 및 파일, 감사 로그 검색뿐만 아니라 Microsoft Intune을 사용하여 모바일 애플리케이션 관리를 비롯한 규정 준수 영역을 지원하기 위한 다양한 정보가 있습니다. 아래 모든 항목에 대한 정보를 제공했습니다. [Microsoft 365](https://compliance.microsoft.com) 준수 센터로 이동하여 이러한 설정을 관리할 수 있습니다.

### <a name="information-barriers"></a>정보 장벽

정보 장벽은 Teams 관리자가 사용자 또는 그룹이 서로 통신하지 못하게 하는 정책(비즈니스 요구가 없는 경우 또는 이를 차단하는 규정 이유가 없는 경우)을 수행하기 위해 Teams 관리자가 적용한 정책입니다. 또한 아래 설명과 같은 내용과 관련된 정책을 설정할 수 있습니다. 이러한 정책은 1:1 채팅, 그룹 채팅 또는 팀 수준에서 사용자에게 영향을 줄 수 있습니다.

이 항목에 대한 자세한 내용은 [Microsoft Teams의 정보 장벽으로 이동하세요.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>통신 규정 준수

Microsoft 365의 통신 규정 준수를 사용하면 Microsoft Teams 통신에서 내부 및 규정 표준과 관련된 부적당 언어, 중요한 정보 및 정보를 검사하도록 구성할 수 있는 범위 내 정책에 사용자를 추가할 수 있습니다. 공용 및 개인 Teams 채널, 개별 채팅 및 첨부 파일 모두에서 채팅 통신 및 연결된 첨부 파일을 스캔하여 조직의 통신 위험을 최소화할 수 있습니다. 부적절한 Teams 통신을 감지하고, 캡처하고, 조치를 취하는 데 도움이 되는 정책을 구성하는 방법에 대한 자세한 내용은 [Microsoft 365의](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)통신 규정 준수를 참조하세요.

### <a name="retention-policies"></a>보존 정책

Microsoft Teams의 보존 정책을 사용하면 규정, 법률, 비즈니스 또는 기타 이유로 조직이 유지해야 하는 중요한 데이터를 보존하고 보존되지 않은 콘텐츠 및 통신을 제거할 수 있습니다. 보존 정책을 사용하여 데이터를 특정 기간 동안 보관한 다음 삭제할 수도 있습니다. 자세한 내용은 Microsoft [Teams 문서의 보존 정책을 검토하세요.](retention-policies.md)

## <a name="sensitivity-labels"></a>민감도 레이블

민감도 [레이블을 적용하여](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 팀 내에서 공동 작업하는 동안 생성된 중요한 조직 콘텐츠에 대한 액세스를 보호하고 규제합니다. 예를 들어 팀의 개인 정보(공개 또는 비공개)를 구성하고, 게스트 액세스 및 외부 공유를 제어하고, 관리되지 않는 디바이스의 액세스를 관리하는 레이블을 적용합니다. 자세한 내용은 Microsoft Teams 문서의 [민감도 레이블을 검토하세요.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>DLP(데이터 손실 방지)

Microsoft Teams의 DLP(데이터 손실 방지) 및 Microsoft 365 또는 Office 365용 더 큰 DLP 스토리는 중요한 문서 및 데이터 보호와 관련한 비즈니스 준비를 중심으로 합니다. 메시지 또는 문서의 중요한 정보에 대해 우려하는 경우 DLP 정책은 사용자가 이 중요한 데이터를 잘못된 사용자와 공유하지 않도록 할 수 있습니다.

Teams의 데이터 손실 방지에 대한 자세한 내용은 [Microsoft Teams용 DLP를 검토하세요.](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) O365 DLP 문제의 좋은 문서는 데이터 손실 방지 [개요입니다.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

전자 검색 또는 eDiscovery는 법률 소송 또는 조사에서 프로덕션 요청에 대응하여 ESI(전자적으로 저장된 정보)를 식별, 수집 및 생성하는 전자적 측면입니다. 기능에는 사례 관리, 보존, 검색, 분석 및 Teams 데이터의 내보내기 기능이 포함됩니다. 여기에는 채팅, 메시징 및 파일, 모임 및 통화 요약이 포함됩니다. Teams 모임 및 통화의 경우 모임 및 통화에서 발생된 이벤트의 요약이 만들어지며 eDiscovery에서 사용할 수 있습니다.

보안 센터 및 규정 준수 센터에서 Microsoft 365 또는 Office 365 eDiscovery를 실행하고 Teams 콘텐츠에 대한 규정 준수 콘텐츠 검색을 실행하는 방법에 대한 자세한 내용은 아래 링크로 이동하세요.

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

게스트-게스트 [채팅의 eDiscovery에](eDiscovery-investigation.md)대한 자세한 내용은 Teams 관련 문서를 제공합니다.

고객은 요구 사항에 따라 eDiscovery 또는 [Advanced eDiscovery를](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) 활용할 수 있습니다. 다음 표에서는 두 가지 차이점을 간략하게 설명하고 있습니다.

| |eDiscovery  |고급 eDiscovery  |
|---------|---------|---------|
|사례 관리     |X        |X         |
|Access Control  |X         |X         |
|콘텐츠 검색     |X         | X        |
|보류   |X         | X        |
|내보내기     |X         |X         |
|중복 검색     |-         |X         |
|Machine Learning과의 검색과의 무관성    |-         |X         |
|구조화되지 않은 데이터 분석      |-         |X         |

### <a name="legal-hold"></a>법적 보류

소송 중에는 사용자(보존자) 또는 팀과 연결된 모든 데이터를 변경 불가능한 것으로 보존해야 사례에 대한 증거로 사용할 수 있습니다. 사용자(사용자 사서함) 또는 팀을 법적 보류에 배치하여 이 작업을 할 수 있습니다. 팀 법적 보류의 경우 팀의 사서함은 다음 보류에 넣을 수 있습니다.

- In-Place 보류(대상 쿼리 또는 필터링된 콘텐츠를 통한 사서함 또는 사이트 모음의 하위 집합이 보류) 또는
- 소송 보류(전체 사서함 또는 사이트 모음이 보류된 경우)

두 경우 모두 보류가 설정되면 최종 사용자가 그룹 사서함에 있는 채널 메시지를 삭제하거나 편집하는 경우에도 해당 콘텐츠의 변경 불가능한 복사본이 eDiscovery 검색을 통해 유지 관리되고 사용할 수 있습니다. 법적 보유는 일반적으로 eDiscovery 사례의 컨텍스트 내에서 적용됩니다.

Microsoft 365 준수 [센터의](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 보존 및 보존에 대한 자세한 내용은 보존 정책 개요 문서를 참조하세요. 법적 보유에 대한 Teams 관련 정보를 더 자세히 알아보기 위해 [Microsoft Teams](legal-hold.md) 사용자 또는 팀을 법적 보류 문서에 추가합니다.

### <a name="compliance-content-search"></a>규정 준수 콘텐츠 검색

콘텐츠 검색은 풍부한 필터링 기능을 통해 모든 Teams 데이터를 검색하는 데 사용할 수 있습니다. 결과 데이터는 규정 준수 및 소송 지원을 위해 특정 컨테이너로 내보낼 수 있습니다. eDiscovery 사례를 사용 또는 하지 않고 수행될 수 있습니다. 이를 통해 규정 준수 관리자는 모든 사용자에 걸쳐 Teams 데이터를 수집하고, 추가 처리를 위해 검토 및 내보낼 수 있습니다. Microsoft 365 준수 센터에서 Microsoft Teams 및 기타 Microsoft 365 또는 Office 365 콘텐츠에 대한 규정 준수 콘텐츠 검색을 수행 하는 방법에 대한 자세한 내용은 이 콘텐츠 검색 문서를 참조하세요. [](https://docs.microsoft.com/microsoft-365/compliance/content-search)

> [!TIP]
> 콘텐츠 검색을 사용하면 필요한 경우 채팅 및 채널 메시지, 모임, 통화와 같은 Microsoft Teams 콘텐츠만 필터링할 수 있습니다.

콘텐츠 검색 구성에 대한 Teams 관련 추가 정보를 원하는 경우 Microsoft Teams 문서의 콘텐츠 검색을 [검토하세요.](content-search.md)

### <a name="auditing-and-reporting"></a>감사 및 보고

감사 로그 검색은 Microsoft 365 준수 센터에 바로 연결하며, 무제한 감사 타임라인에서 관리자 사용 및 조사를 위해 워크로드 특정 또는 일반 이벤트 집합을 내보내고 감사 이벤트에 대한 보고뿐만 아니라 경고를 설정하는 기능을 제공합니다. Microsoft 365 준수 센터 내의 모든 감사 로그 데이터에 대한 경고를 설정하고 추가 분석을 위해 이 데이터를 필터링 및 내보낼 수 있습니다. Microsoft 365 또는 Office 365에 대한 감사 로그 검색을 수행 하는 방법에 대한 자세한 내용은 감사 로그 검색 문서를 참조하세요. [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Microsoft 365 준수 센터에서 Microsoft Teams 이벤트를 검색하는 방법을 자세히 알아보기 위해 [검토할](audit-log-events.md) 수 있도록 Teams 문서에서 감사 켜기 기능을 제공합니다.

## <a name="privacy"></a>개인 정보

Microsoft에서 데이터를 보호하는 것이 최우선 순위입니다. 개인 정보 취급 방침에 대한 자세한 내용은 다음을 읽어보아야 합니다.  

- [Microsoft의 개인 정보](https://www.microsoft.com/trust-center/privacy)
- [Microsoft Teams의 개인 정보 및 보안에 대한 Microsoft의 약속](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT 전문가: Microsoft Teams의 개인 정보 및 보안](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>정보 보호 아키텍처

다음 그림은 Teams 파일 및 메시지에 대한 Exchange 및 SharePoint에 Teams 데이터의 수집 흐름을 나타냅니다.

![Exchange 및 SharePoint에 대한 Teams 데이터의 워크플로 다이어그램](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

다음 그림은 Teams 모임의 수집 흐름과 Exchange에 데이터를 호출하는 흐름을 나타냅니다.

![Teams 모임 및 Exchange에 데이터 호출 워크플로 다이어그램](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams 콘텐츠를 검색하는 데 최대 24시간이 지연될 수 있습니다.

## <a name="licensing"></a>라이선싱

정보 보호 기능의 경우 Microsoft 365 구독, Office 365 구독 및 연결된 독립 실행형 라이선스에 따라 사용 가능한 기능 집합이 결정됩니다.

보안 및 규정 준수를 위한 기능을 구현해야 하는 라이선스를 결정하는 데 필요한 정보는 보안 및 규정 준수 기능에 대한 라이선스 요구 사항을 검토하세요. [](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)
> [!NOTE]
> Content Search 및 eDiscovery는 Security & 준수 센터에서 사용할 필요가 없습니다.

## <a name="location-of-data-in-teams"></a>Teams의 데이터 위치

Teams의 데이터는 Microsoft 365 또는 Office 365 조직과 연결된 지리적 영역에 위치합니다. 현재 지원되는 지역은 [Microsoft Teams에서 데이터의 위치를 검토하세요.](location-of-data-in-teams.md)

테넌트에 대한 데이터를 저장하는 지역을 확인하려면 [Microsoft 365](https://portal.office.com/adminportal/home)관리 센터 설정  >    >  **조직 프로필로 이동합니다.** **데이터 위치** 로 스크롤 합니다.

![관리 센터의 Teams를 포함한 데이터 위치 테이블의 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>규정 준수 표준

Teams는 [ISO 27001,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001)ISO [27018,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 및 SOC 2,](https://docs.microsoft.com/microsoft-365/compliance/offering-soc) [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)및 EU 모델 절(EUMC) 표준을 사용 합니다. [](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) Microsoft 규정 준수 프레임워크 내에서 Microsoft는 Microsoft 365 및 Office 365 애플리케이션 및 서비스를 네 가지 범주로 분류합니다. 각 범주는 해당 범주에 나열될 Microsoft 365 또는 Office 365 서비스 또는 관련 Microsoft 서비스에 대해 충족해야 하는 특정 규정 준수 약정으로 정의됩니다.

자세한 내용은 데이터 보호 [리소스에서 찾을 수 있습니다.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams는 Cloud Security Alliance 규정 준수도 지원합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 보안](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 규정 준수](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft 규정 준수 제품](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
