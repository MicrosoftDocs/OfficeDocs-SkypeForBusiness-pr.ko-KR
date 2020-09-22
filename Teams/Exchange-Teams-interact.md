---
title: Exchange 및 Microsoft 팀의 상호 작용 방식
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft 팀과 팀 만들기 및 참가, 채널 만들기 등의 다양 한 Exchange 기능 간에 어떤 기능이 존재 하는지 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35c020d981fba9827f10753a04b9b5629a9939df
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177208"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 및 Microsoft 팀의 상호 작용 방식

> [!Tip]
> 팀에서 AAD (Azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive를 상호 작용 하는 방법에 대 한 자세한 내용은 [Microsoft 팀의 기초](https://aka.ms/teams-foundations) 를 참고 하세요.

전체 팀 경험을 위해서는 모든 사용자가 Exchange Online, SharePoint Online, Microsoft 365 그룹 만들기를 사용할 수 있어야 합니다.

사용자의 Exchange 사서함을 온라인 또는 온-프레미스로 호스트할 수 있습니다.

Exchange Online 또는 Exchange 전용 vNext에서 호스팅되는 사용자는 팀의 모든 기능을 사용할 수 있습니다. 팀과 채널을 만들고, 모임을 만들고, 보고, 사용자 프로필 사진을 수정할 수 있으며 (웹 사서함 정책의 Outlook에서 수행할 수 있는 경우) 커넥터, 탭, 인공 지능을 추가 하 고 구성 합니다. 사용 가능한 다양 한 기능 목록은 아래 표를 참조 하세요.

Exchange Online 전용 (레거시)에서 호스팅되는 사용자는 Microsoft 365 또는 Office 365의 Azure Active Directory와 동기화 되어야 합니다. 팀과 채널을 만들고 참가 하 고, 탭 및 인공 지능을 추가 및 구성 하 고, 채팅 및 통화 기능을 활용할 수 있습니다. 그러나 프로필 사진을 수정 하거나, 모임을 관리 하거나, outlook 연락처에 액세스 하거나, 커넥터를 관리할 수는 없습니다.

> [!IMPORTANT]
> 온-프레미스와 통합 하려면 Exchange Server 2016 이상에서 Exchange 전체 클래식 하이브리드 배포를 사용 하는 것이 좋습니다. 최신 하이브리드 지원은 약속 있음/없음으로 제한 되며, 예를 들어 팀에서 온-프레미스 사서함으로의 일정 통합을 제공 하지 않습니다. 하이브리드 배포를 설정 하는 방법에 대 한 자세한 내용은 [Exchange Server 하이브리드 배포](https://docs.microsoft.com/exchange/exchange-hybrid)를 참조 하세요.

온-프레미스에 호스팅되는 사서함이 있는 사용자는 Azure Active Directory와 동기화 되어야 합니다. 위에서 설명한 [사서함에 대 한 요구](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) 사항에 나열 된 요구 사항이 충족 되는 경우 위의 시나리오에서 모든 기능을 사용할 수 있지만, 그 외에도 모임을 관리할 수 있습니다.

다음 표에서는 Exchange 환경을 기반으로 하는 기능 가용성에 대 한 유용한 빠른 참조를 제공 합니다.

**지원 되는 작업:**

| 사용자의 사서함이 호스트 되는 위치:                                        | eDiscovery       | 법률 &nbsp; 보류    | 보관  | 팀 및 채널 관리 | 팀에서 모임 만들기 및 보기 | 사용자 프로필 사진 수정 | 통화 기록 | 연락처 관리 | Outlook 연락처에 액세스 | 음성 메일  | 커넥터 추가 및 구성 | 탭 추가 및 구성 | 봇 추가 및 구성 |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | 예 <sup>1</sup> | 예 <sup>1</sup>   | 예        | 예                   | 예                               | 예<sup>7</sup>             | 예          | 예             | 예 <sup>6</sup>        | 예        | 예                          | 예                    | 예                    |
| **Exchange Online 전용 vNext**                                 | 예 <sup>1</sup> | 예 <sup>1</sup>   | 예        | 예                   | 예                               | 예<sup>7</sup>             | 예          | 예             | 예 <sup>6</sup>        | 예        | 예                          | 예                    | 예                    |
| **Exchange Online 전용-레거시** (Azure AD와 동기화 필요)  | 예 <sup>1</sup> | 예 <sup>1, 2</sup> | 예 <sup> 3 | 예                   | 아니요                                | 아니요                          | 예          | 예             | 아니요                      | 예 <sup> 4 | 예 <sup> 5                   | 예                    | 예                    |
| **Exchange 온-프레미스** (Azure AD와 동기화) | 예 <sup>1</sup> | 예 <sup>1</sup>   | 예 <sup>3</sup> | 예                   | 예 <sup>8</sup>         | 아니요                          | 예          | 예             | 아니요                      | 예 <sup> 4 | 예 <sup> 5                   | 예                    | 예                    |

모든 호스팅 옵션에 대해 채널 메시지에 대 한 eDiscovery 및 법적 보류가 <sup>1 개</sup> 지원 됩니다.

<sup>2</sup> 팀 개인 채팅 메시지는이 호스팅 옵션의 법률 보존에 대해 아직 지원 되지 않습니다.

<sup>3</sup> 보존은 온라인 사용자를 위해 섀도 사서함을 사용 하 여 메시지를 저장 합니다.

<sup>4</sup> 온-프레미스 Exchange 사서함이 있는 팀 사용자는 Outlook에서 팀과 보이스 메일을 사용할 수 있지만, 음성 메일 메시지는 팀 클라이언트 내에서 보거나 재생할 수 없습니다.

팀의 소유자 중 한 명에 게 커넥터를 추가할 수 <sup>있는 경우 해당</sup> 팀의 다른 사용자는 해당 사서함이 온-프레미스 인 경우에도이 작업을 수행할 수 있습니다.

<sup>6</sup> 기본 연락처 폴더의 연락처만 다른 연락처 폴더 또는 하위 폴더에 대 한 액세스는 지원 되지 않습니다.

<sup>7</sup> 팀은 테 넌 트 관리자가 구성한 [웹 사서함 정책](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) 설정의 Outlook을 통해 사용자가 프로필 사진을 변경할 수 있는지 여부를 제어 합니다. 정책에서 **-set사진 사용** 설정이 해제 되어 있는 경우 사용자는 프로필 사진을 추가, 변경 또는 제거할 수 없습니다. 예를 들어 사용자가 조직의 IT 또는 HR 부서에서 승인한 프로필 사진을 업로드 하는 경우 아무런 작업도 필요 하지 않습니다. 그러나 사용자가 부적절 한 그림을 업로드 하는 경우 조직의 내부 정책에 따라 변경 합니다.

<sup>8</sup> 온 [-프레미스 섹션으로 호스팅되는 사서함에 대 한 모임을 만들고 보기 위한 요구](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) 사항에 나열 된 요구 사항을 충족 해야 합니다.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft 팀을 최대한 활용 하기 위한 요구 사항

Microsoft 팀은 다양 한 Microsoft 365 및 Office 365 서비스를 사용 하 여 사용자에 게 풍부한 환경을 제공 합니다. 이 환경을 지원 하려면 특정 기능 또는 서비스를 사용 하도록 설정 하 고 라이선스를 할당 해야 합니다.

- 사용자에 게 Exchange Online 라이선스를 할당 해야 합니다.

- 팀 대화에서 파일을 공유 하 고 저장 하려면 SharePoint Online이 필요 합니다. Microsoft 팀은 SharePoint 온-프레미스를 지원 하지 않습니다.

- 채팅에서 파일을 공유 하려는 경우 사용자에 게 SharePoint Online 라이선스를 할당 해야 합니다. 사용자가 SharePoint Online 라이선스를 할당 하 고 사용 하도록 설정 하지 않은 경우 Microsoft 365 또는 Office 365에 비즈니스용 OneDrive 저장소가 없습니다. 파일 공유는 채널에서 계속 작동 하지만, 사용자는 Microsoft 365 또는 Office 365의 비즈니스용 OneDrive 저장소 없이는 채팅에서 파일을 공유할 수 없습니다.

- Microsoft 팀에서 팀을 만들려면 Microsoft 365 그룹 만들기가 사용 하도록 설정 되어 있어야 합니다.

> [!IMPORTANT]
> 사용자를 **팀 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거 하는 경우 Outlook 및 다른 Office 앱에서 현재 상태가 중지 될 수 있습니다. 현재 상태는 Teams에서 잘 작동합니다. 이 문제를 해결 하려면 Microsoft 팀의 오른쪽 위 모서리에서 프로필 사진을 선택한 다음 **설정을**선택 합니다. **일반** 탭의 **응용 프로그램**에서 **Office 용 채팅 앱으로 팀 등록 (office 응용 프로그램을 다시 시작 해야 함)** 을 선택 합니다. 이 옵션을 선택한 후 Outlook을 포함 하 여 모든 Office 앱을 닫았다가 다시 엽니다. Outlook을 열면 현재 상태 정보를 사용할 수 있게 됩니다.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>온-프레미스에 호스팅되는 사서함에 대 한 모임을 만들고 보기 위한 요구 사항

사서함이 온-프레미스로 호스팅되는 경우 모임을 만들고 보려면 다음 요구 사항을 충족 해야 합니다.

- Azure Active Directory 동기화 사용자에 대해 필요한 팀 라이선스를 할당 해야 합니다.

- 사용자는 Azure Active Directory로 동기화 되어야 합니다. Azure AD Connect를 사용 하 여 Azure Active Directory와 동기화 하는 방법에 대 한 자세한 내용은 [하이브리드 id 설명서](https://docs.microsoft.com/azure/active-directory/hybrid/)를 참조 하세요.

- 사서함은 Exchange Server 2016 누적 업데이트 3 이상에서 호스팅됩니다.

- 자동 검색 및 Exchange 웹 서비스는 외부적으로 게시 됩니다.

- OAuth 인증은 Exchange 하이브리드 구성 마법사를 통해 (클래식 또는 최신) 전체 하이브리드 구성을 실행 하 여 구성 됩니다. 하이브리드 구성 마법사를 사용할 수 없는 경우 [exchange 및 Exchange Online 조 직 간의 oauth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)에 설명 된 대로 oauth를 구성 합니다.

 > [!NOTE]
 > Exchange에서 EvoSTS로 알려진 팀 서비스 로부터 OAuth 토큰을 신뢰 합니다. 1 단계는 충분 하지만 EvoSTS만 가능 합니다. ACS는 일정에서 약속 있음/없음 조회에 사용 됩니다.

- Azure AD Connect의 Exchange 하이브리드 배포 기능에 대 한 확인란이 설정 되어 있습니다.

- Mac 용 일정 앱 지원 및 팀 Outlook 추가 기능의 경우 exchange 서비스 사용자를 위해 테 넌 트 Azure AD에서 Exchange 웹 서비스 Url을 Spn으로 구성 해야 합니다. 이 단계는 하이브리드 구성 마법사를 사용 하거나 [하이브리드 최신 인증을 위한 수동 단계](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)를 따라 수행 됩니다.

이러한 사용자에 대해 일정 위임을 사용 하려면 다음을 수행 합니다.

- 또한 [통합 구성 및 비즈니스용 Skype Online 및 Exchange Server 간](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)설정에 설명 된 대로 2-3 단계를 완료 해야 합니다. 이 단계에서는 팀 예약 응용 프로그램에 대리인 권한을 확인 하는 데 필요한 권한을 제공 합니다.
 
 > [!NOTE]
 > 2 단계에는 위임용으로 필요 하지 않은 ArchiveApplication에 대 한 역할 할당이 포함 됩니다.

- 다른 사람을 대신 하 여 모임을 예약할 때 Outlook 용 팀 일정 추가 기능은 Exchange 2013 CU19 이상 이어야 합니다. 이는 서비스에서 사서함에 대 한 인증 되지 않은 검색을 지원 하 여 위임자 사서함에 대 한 대리인 권한을 확인 하는 것입니다. 대리인 및 위임자 위치는 Exchange 2013 이상 또는 Exchange online 일 수 있지만, 다시 검색을 Exchange 2013 CU19 이상으로 확인 해야 합니다.

## <a name="additional-considerations"></a>추가 고려 사항

다음은 조직에서 Microsoft 팀을 구현할 때 고려해 야 할 몇 가지 추가 사항입니다.

- Microsoft 팀에서 eDiscovery, 콘텐츠 검색, 보관, 법률 보호 등의 보안 및 규정 준수 기능이 Exchange Online 및 SharePoint Online 환경에서 가장 잘 작동 합니다. 채널 대화의 경우 메시지가 eDiscovery에 사용할 수 있는 Exchange Online의 그룹 사서함으로 저널링 됩니다. 조직 전체에서 SharePoint Online 및 비즈니스용 OneDrive (회사 또는 학교 계정을 사용)를 사용 하는 경우 팀 내의 모든 파일에 대해 이러한 준수 기능을 사용할 수 있습니다.

- 조건부 액세스를 사용 하 여 팀 및 Exchange에서 준수 정책의 구성을 제어 하 고 보호 합니다. 자세한 내용은 [팀에 대 한 조건부 액세스 정책 작동 방법](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) 보기를 참조 하세요. .

- 조직에 모든 모임 토론을 검색할 수 있는 규정 준수 요구 사항이 있는 경우 이끌이에게 Exchange 온-프레미스 사서함이 있는 경우 개인 모임을 사용 하지 않도록 설정 해야 합니다. 자세한 내용은 [비공개 모임 예약 허용](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)을 참조 하세요.

- Exchange 하이브리드 배포의 경우 채팅 참가자가 클라우드 기반 사서함을가지고 있는지 아니면 온-프레미스 사서함을 사용 하 든 관계 없이 채팅 메시지의 콘텐츠를 검색할 수 있습니다. 자세한 내용은 온 [-프레미스 사용자에 대 한 클라우드 기반 사서함 검색](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)을 참조 하세요. 팀에서 콘텐츠를 검색 하는 방법에 대 한 자세한 내용은 [Microsoft 365 준수 센터에서 콘텐츠 검색](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)을 참조 하세요.

## <a name="troubleshooting"></a>문제 해결

항목에 대 한 전체 문제 해결 가이드는 [Microsoft 팀 및 Exchange Server 조작 문제 해결](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)을 참조 하세요.
