---
title: Exchange 및 Microsoft Teams 상호 작용 방법
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 'Microsoft Teams와 다양한 Exchange 설정(예: 팀 만들기 및 참가, 채널 만들기 등)에 대해 자세히 알아보고,'
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e2e6af198c578279e2af8928e8a6ac299f262a5
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661903"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 및 Microsoft Teams 상호 작용 방법

> [!Tip]
> 다음 세션에서 Teams가 AAD(Azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용하는 방법을 [알아보십시오. Microsoft Teams의 기초](https://aka.ms/teams-foundations)

전체 Teams 환경의 경우 모든 사용자가 Exchange Online, SharePoint Online 및 Microsoft 365 그룹 만들기를 사용하도록 설정해야 합니다.

사용자의 Exchange 사서함은 온라인 또는온-프레미스에서 호스팅할 수 있습니다.

Exchange Online 또는 Exchange Dedicated vNext에서 호스팅된 사용자는 Teams의 모든 기능을 사용할 수 있습니다. 팀 및 채널을 만들고 참가하고, 모임을 만들고 보고, 통화 및 채팅하고, 사용자 프로필 사진(웹용 Outlook 사서함 정책에서 허용하는 경우)을 수정하고, 커넥터, 탭 및 봇을 추가 및 구성할 수 있습니다. 사용 가능한 기능의 보다 포괄적인 목록은 아래 표를 참조하세요.

Exchange Online Dedicated(레거시)에 호스트된 사용자는 Microsoft 365 또는 Office 365의 Azure Active Directory에 동기화되어야 합니다. 팀과 채널을 만들고 참가하고, 탭과 봇을 추가 및 구성하고, 채팅 및 통화 기능을 사용할 수 있습니다. 그러나 프로필 사진을 수정하거나, 모임을 관리하거나, Outlook 연락처에 액세스하거나, 커넥터를 관리할 수는 없습니다.

> [!IMPORTANT]
> 2016 이상 버전과의 Exchange 전체 클래식 하이브리드 배포를 Exchange Server 것이 좋습니다. 최신 하이브리드 지원은 약속 있는/약속 있는 것으로 제한되어 있으며 Teams에서 사서함으로의 일정 통합을 제공하지 않습니다. 예를 들어, 하이브리드 배포 설정에 대한 자세한 내용은 하이브리드 Exchange Server [참조하세요.](https://docs.microsoft.com/exchange/exchange-hybrid)

사서함이 호스트된 사용자는 Azure Active Directory와 동기화되어야 합니다. 위의 시나리오에서 모든 기능을 사용할 수 있지만, 또한, 이 섹션에서 호스팅되는 사서함의 요구 사항에 나열된 요구 사항이 충족되는 경우 모임을 관리할 수 [있습니다.](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)

다음 표에서는 Exchange 환경에 따라 기능 가용성에 대한 유용한 빠른 참조를 제공합니다.

**지원되는 작업:**

| 사용자의 사서함은 다음에서 호스팅됩니다.                                        | eDiscovery       | 법적 &nbsp; 보류    | 보존  | 팀 및 채널 mgmt | Teams에서 모임 만들기 및 보기 | 사용자 프로필 사진 수정 | 통화 기록 | 연락처 관리 | Outlook 연락처 액세스 | 음성 메일  | 커넥터 추가 및 구성 | 탭 추가 및 구성 | 봇 추가 및 구성 |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | 예 <sup>1</sup> | 예 <sup>1</sup>   | 예        | 예                   | 예                               | 예<sup>7</sup>             | 예          | 예             | 예 <sup>6</sup>        | 예        | 예                          | 예                    | 예                    |
| **Exchange Online Dedicated vNext**                                 | 예 <sup>1</sup> | 예 <sup>1</sup>   | 예        | 예                   | 예                               | 예<sup>7</sup>             | 예          | 예             | 예 <sup>6</sup>        | 예        | 예                          | 예                    | 예                    |
| **Exchange Online Dedicated – 레거시(Azure** AD에 동기화 필요)  | 예 <sup>1</sup> | 예 <sup>1,2</sup> | 예 <sup>3</sup> | 예                   | 아니요                                | 아니요                          | 예          | 예             | 아니요                      | 예 <sup>4</sup> | 예 <sup>5</sup>                   | 예                    | 예                    |
| **Exchange On-premises(Azure** AD에 동기화) | 예 <sup>1</sup> | 예 <sup>1</sup>   | 예 <sup>3</sup> | 예                   | 예 <sup>8</sup>         | 아니요                          | 예          | 예             | 아니요                      | 예 <sup>4</sup> | 예 <sup>5</sup>                   | 예                    | 예                    |

<sup>모든 호스팅</sup> 옵션에 대해 채널 메시지 규정 준수를 위한 eDiscovery 및 법적 보류 1개가 지원됩니다.

<sup>2</sup> Teams 개인 채팅 메시지는 이 호스팅 옵션에 대한 법적 보류에 대해 아직 지원되지 않습니다.

<sup>3</sup> 보존은 온라인 사용자에 대해 섀도 사서함을 사용하여 메시지를 저장합니다.

<sup>4개</sup> Teams 사용자는 Teams에서 음성 메일을 사용하여 Outlook에서 음성 메일을 받을 수 있지만, Teams 클라이언트 내에서 음성 메일 메시지를 보거나 재생할 수 없습니다.

<sup>5</sup> 팀 소유자 중 한 명이 커넥터를 추가할 수 있는 경우 해당 팀의 다른 모든 사용자가 사서함이 있는 경우라도 커넥터를 추가할 수 있습니다.

<sup>6</sup> 기본 연락처 폴더의 연락처만 다른 연락처 폴더 또는 하위 폴더에 대한 액세스는 지원되지 않습니다.

<sup>7</sup> Teams는 사용자가 프로필 사진을 변경할 수 있는지 여부를 제어하기 위해 테넌트 관리자가 구성한 웹의 [Outlook](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) 사서함 정책 설정을 적용합니다. **정책에서 -SetPhotoEnabled** 설정을 해제한 경우 사용자는 프로필 사진을 추가, 변경 또는 제거할 수 없습니다. 예를 들어 사용자가 조직의 IT 또는 HR 부서에서 승인한 프로필 사진을 업로드하는 경우 아무 작업도 필요하지 않습니다. 그러나 사용자가 부적절한 사진을 업로드하는 경우 조직의 내부 정책에 따라 변경합니다.

<sup>8</sup> 요구 사항에 나열된 요구 [](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) 사항을 충족해야만 모임을 만들고 볼 수 있습니다.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams를 가장 잘하기 위해 필요한 요구 사항

Microsoft Teams는 여러 Microsoft 365 및 Office 365 서비스와 함께 작동하여 사용자에게 풍부한 경험을 제공합니다. 이 환경을 지원하려면 특정 기능 또는 서비스를 사용하도록 설정하고 라이선스를 할당해야 합니다.

- 사용자에게 Exchange Online 라이선스가 할당되어야 합니다.

- SharePoint Online은 팀 대화에서 파일을 공유하고 저장하는 데 필요합니다. Microsoft Teams는 SharePoint On-프레미스를 지원하지 않습니다.

- 채팅에서 파일을 공유하려면 사용자에게 SharePoint Online 라이선스가 할당되어야 합니다. 사용자가 SharePoint Online 라이선스를 할당하고 사용하도록 설정하지 않은 경우 Microsoft 365 또는 Office 365에 비즈니스용 OneDrive 저장소가 없습니다. 파일 공유는 채널에서 계속 작동하지만 사용자는 Microsoft 365 또는 Office 365의 비즈니스용 OneDrive 저장소 없이 채팅에서 파일을 공유할 수 없습니다.

- 사용자가 Microsoft Teams에서 팀을 만들 수 있도록 Microsoft 365 그룹 만들기를 사용하도록 설정해야 합니다.

  > [!IMPORTANT]
  > 사용자를 Teams 전용 모드로 이동한 후 비즈니스용  Skype 클라이언트를 제거하면 Outlook 및 기타 Office 앱에서 현재 상태 작동이 중지될 수 있습니다. 현재 상태는 Teams에서 잘 작동합니다. 이 문제를 해결하려면 Microsoft Teams의 오른쪽 위 모서리에 있는 프로필 사진을 선택한 다음 설정을 **선택합니다.** 응용 프로그램의 **일반** 탭에서 Teams를 Office용 채팅 앱으로 등록(Office 응용 프로그램을 다시  **시작해야 합니다)을 선택합니다.** 이 옵션을 선택한 후 Outlook을 포함한 모든 Office 앱을 닫았다가 다시 열 수 있습니다. Outlook을 열면 현재 상태 정보를 사용할 수 있습니다.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>호스트된 사서함에 대한 모임을 만들고 보기 위한 요구 사항

사서함이 호스트되는 경우 모임을 만들고 확인하려면 다음 요구 사항을 충족해야 합니다.

- Azure Active Directory 동기화 사용자에 필요한 Teams 라이선스를 할당해야 합니다.

- 사용자는 Azure Active Directory에 동기화되어야 합니다. Azure AD Connect를 사용하여 Azure Active Directory와 동기화하는 방법에 대한 자세한 내용은 [하이브리드 ID 설명서를 참조하세요.](https://docs.microsoft.com/azure/active-directory/hybrid/)

- 사서함은 2016년 Exchange Server 업데이트 3 이상에서 호스팅됩니다.

- 자동 검색 및 Exchange 웹 서비스는 외부에서 게시됩니다.

- OAuth 인증은 전체 하이브리드 구성(클래식 또는 최신)을 실행하는 Exchange 하이브리드 구성 마법사를 통해 구성하는 것이 좋습니다. 하이브리드 구성 마법사를 사용할 수 없는 경우 Exchange와 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 [OAuth를 구성합니다.](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  > [!NOTE]
  > Exchange는 EvoSTS라고 하는 Teams 서비스의 OAuth 토큰을 신뢰합니다. 1단계는 충분하지만 EvoSTS만 ACS는 일정에서 약속 있는/약속 있는 보기에 사용됩니다.

- Azure AD Connect의 Exchange 하이브리드 배포 기능에 대한 확인란이 설정됩니다.

- Mac용 일정 앱 지원 및 Teams Outlook Add-In 경우 Exchange 웹 서비스 URL은 Exchange 서비스 주체에 대한 테넌트 Azure AD의 SPNS로 구성되어야 합니다. 이 단계는 하이브리드 구성 마법사 또는 하이브리드 최신 인증에 대한 수동 단계를 [수행합니다.](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)

이러한 사용자에 대해 일정 위임을 사용하도록 설정하려면:

- 또한 비즈니스용 Skype Online과 서비스 간 통합 및 [OAuth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)구성에 설명된 2-3단계를 Exchange Server. 이러한 단계는 Teams 예약 애플리케이션에 대리인 권한을 확인하는 데 필요한 권한을 제공합니다.
 
  > [!NOTE]
  > 2단계에는 위임에 필요하지 않은 ArchiveApplication에 대한 역할 할당이 포함됩니다.

- 다른 사람을 대신하여 모임을 예정할 때 Outlook용 Teams 추가 기능의 경우 Exchange 2013 CU19 이상이 필요합니다. 이는 위임자 사서함에 대한 대리인 권한을 검사하기 위해 서비스에서 사서함의 무단 검색을 지원하기 위한 것입니다. 대리인 및 위임 위치는 Exchange 2013 이상 또는 Exchange Online일 수 있지만 자동 검색은 Exchange 2013 CU19 이상으로 확인되어야 합니다.

## <a name="additional-considerations"></a>추가 고려 사항

조직에서 Microsoft Teams를 구현할 때 다음과 같은 몇 가지 추가적인 생각을 할 수 있습니다.

- Microsoft Teams에서 eDiscovery, 콘텐츠 검색, 보관 및 법적 보관과 같은 보안 및 규정 준수 기능은 Exchange Online 및 SharePoint Online 환경에서 가장 잘 작동합니다. 채널 대화의 경우 메시지는 eDiscovery에서 사용할 수 있는 Exchange Online의 그룹 사서함에 저널됩니다. SharePoint Online 및 비즈니스용 OneDrive(직장 또는 학교 계정 사용)가 조직 및 사용자에 대해 활성화된 경우 Teams 내의 모든 파일에도 이러한 규정 준수 기능을 사용할 수 있습니다.

- 조건부 액세스를 사용하여 Teams 및 Exchange에서 규정 준수 정책의 구성을 제어하고 보호합니다. 자세한 내용은 [Teams에 조건부 액세스 정책이 어떻게 작동하나요?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- 조직에서 모든 모임 토론을 검색할 수 있도록 규정 준수 요구 사항이 있는 경우 이끌이에게 Exchange-프레미스 사서함이 있는 경우 비공개 모임을 사용하지 않도록 설정해야 합니다. 자세한 내용은 비공개 모임 [허용을 참조하세요.](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)

- Exchange 하이브리드 배포에서 채팅 메시지의 콘텐츠는 채팅 참가자에게 클라우드 기반 사서함 또는 클라우드 기반 사서함이 있는지 여부에 관계없이 검색할 수 있습니다. 자세한 내용은 프레미스 사용자에 대한 클라우드 기반 사서함 [검색을 읽어보아야 합니다.](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users) Teams에서 콘텐츠 검색에 대한 자세한 내용은 Microsoft 365 준수 센터에서 콘텐츠 [검색을 읽어 보아야 합니다.](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)

- 현재 상태의 경우 Microsoft Teams는 사서함이 Exchange Online에서 호스팅되는지 또는 아니면온-프레미스에서 호스트되는지 여부를 확인해야 합니다. 그러면 서비스는 사서함에 액세스할 위치를 결정합니다. Teams 서비스가 Exchange Online 서비스에 대한 REST API 호출을 통해 사서함 위치를 확인할 수 있도록 설정하려면 하이브리드 구성 마법사를 사용하여 하이브리드 배포 만들기에 설명된 Exchange 하이브리드 구성 마법사를 실행하여 Exchange 하이브리드 환경을 [배포해야](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid)합니다.

## <a name="troubleshooting"></a>문제 해결

이 항목에 대한 전체 문제 해결 가이드는 Microsoft Teams 문제 해결을 확인하고 상호 작용 문제를 [Exchange Server 합니다.](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)
