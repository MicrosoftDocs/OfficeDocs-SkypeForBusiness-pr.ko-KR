---
title: Exchange와 Microsoft Teams의 상호 작용 방법
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft Teams와 Teams 만들기 및 참여하기, 채널 만들기 등과 같은 다양한 Exchange 설정 사이에 존재하는 기능에 대해 알아보세요.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2088272756886b210ae99b32f8c3148d237b10ccb367702745f0327cc4e2896
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590782"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange와 Microsoft Teams의 상호 작용 방법

> [!Tip]
> Teams에서 AAD(Azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용하는 방법을 알아보려면 [Microsoft Teams의 기초](https://aka.ms/teams-foundations) 세션을 시청하세요.

완전한 Teams 환경을 위해서는 모든 사용자가 Exchange Online, SharePoint Online 및 Microsoft 365 그룹 만들기를 사용할 수 있도록 설정되어야 합니다.

사용자의 Exchange 사서함은 온라인 또는 온-프레미스에 호스트될 수 있습니다.

Exchange Online 또는 Exchange 전용 vNext에서 호스트되는 사용자는 Teams의 모든 기능을 사용할 수 있습니다. 팀과 채널을 만들고 참가하고, 모임을 만들고 보고, 통화 및 채팅을 하고, 사용자 프로필 사진을 수정하고, (웹용 Outlook 사서함 정책이 작업의 수행을 허용 시) 커넥터, 탭, 그리고 봇을 추가하고 구성할 수 있습니다. 사용 가능한 기능의 더욱 포괄적인 목록은 아래 표를 참조하세요.

Exchange Online 전용(레거시)에서 호스트되는 사용자는 Microsoft 365 또는 Office 365에서 Azure Active Directory로 동기화되어야 합니다. 팀과 채널을 만들고 참가하고, 탭과 봇을 추가 및 구성하고 채팅 및 호출 기능을 활용할 수 있습니다. 그러나 프로필 사진 수정, 모임 관리, Outlook 연락처에 액세스 혹은 커넥터를 관리할 수는 없습니다.

> [!IMPORTANT]
> 온-프레미스와 통합하려면 Exchange Server 2016 이상을 포함하여 Exchange 전체 클래식 하이브리드 배포를 보유하는 것이 좋습니다. 예를 들어, 최신 하이브리드 지원은 약속 없음/다른 용무 중으로 제한되고 Teams에서 온-프레미스 사서함으로의 일정 통합을 제공하지 않습니다. 하이브리드 배포를 설정하는 방법에 대한 자세한 내용은 [Exchange Server 하이브리드 배포](/exchange/exchange-hybrid)를 참조하세요.

온-프레미스에 호스트되는 사서함이 있는 사용자는 Azure Active Directory에 동기화되어야 합니다. 이러한 사용자는 위의 시나리오의 모든 기능을 활용할 수 있으며 또한 [온-프레미스에 호스트되는 사서함에 대한 요구 사항](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)섹션에 나열된 요구 사항을 충족하는 경우 모임을 관리할 수 있습니다.

다음 표에서는 Exchange 환경을 기반으로 기능 가용성에 대한 유용한 빠른 참조를 제공합니다.

**지원되는 작업:**

| 사용자의 사서함은 다음에서 호스트됩니다.                                       | eDiscovery         | 법적&nbsp;보존    | 보존        | 팀 및 채널 관리 | Teams에서 모임 만들기 및 보기 | 사용자 프로필 사진 수정 | 통화 기록 | 연락처 관리 | Outlook 연락처 액세스 | 음성 메일        | 커넥터 추가 및 구성 | 탭 추가 및 구성 | 봇 추가 및 구성 |
|--------------------------------------------------------------------|--------------------|--------------------|------------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                | 예 <sup>1</sup>   | 예 <sup>1</sup>   | 예              | 예                   | 예                               | 예<sup>7</sup>             | 예          | 예             | 예 <sup>6</sup>        | 예              | 예                          | 예                    | 예                    |
| **Exchange Online 전용 vNext**                                | 예 <sup>1</sup>   | 예 <sup>1</sup>   | 예              | 예                   | 예                               | 예<sup>7</sup>             | 예          | 예             | 예 <sup>6</sup>        | 예              | 예                          | 예                    | 예                    |
| **Exchange Online 전용 – 레거시**(Azure AD로 동기화가 필요) | 예 <sup>1</sup>   | 예 <sup>1,2</sup> | 예 <sup>3</sup> | 예                   | 아니요                                | 아니요                          | 예          | 예             | 아니요                      | 예 <sup>4</sup> | 예 <sup>5</sup>             | 예                    | 예                    |
| **Exchange 온-프레미스**(Azure AD로 동기화)                        | 예 <sup>1,9</sup> | 예 <sup>1</sup>   | 예 <sup>3</sup> | 예                   | 예 <sup>8</sup>                  | 예<sup>10</sup>            | 예          | 예             | 아니요                      | 예 <sup>4</sup> | 예 <sup>5</sup>             | 예                    | 예                    |

<sup>1</sup> eDiscovery 및 채널 메시지의 규정 준수에 대한 법적 보존은 모든 호스팅 옵션에 대해 지원됩니다.

<sup>2</sup> Teams 개인 채팅 메시지는 이 호스팅 옵션에 대한 법적 보존에 대해 아직 지원되지 않습니다.

<sup>3</sup> 보존은 온라인 사용자에 대한 섀도 사서함을 사용하여 메시지를 저장합니다.

<sup>4</sup> 온-프레미스 Exchange 사서함이 있는 Teams 사용자는 Teams를 사용하여 음성 사서함을 사용하고 Outlook에서 음성 메일을 받을 수 있지만 음성 메일 메시지는 Teams 클라이언트 내에서 보거나 재생할 수 없습니다.

<sup>5</sup> 팀의 소유자 중 한 명이 커넥터를 추가할 수 있는 경우, 해당 팀의 다른 사용자 모두가 사서함이 온-프레미스 상태에 있더라도 이 작업을 수행할 수 있습니다.

<sup>6</sup> 기본 연락처 폴더의 연락처만 있습니다. 다른 연락처 폴더 또는 하위 폴더에 대한 액세스는 지원되지 않습니다.

<sup>7</sup> Teams는 사용자가 자신의 프로필 사진을 변경할 수 있는지 여부를 제어하기 위해 테넌트 관리자가 구성한 [웹용 Outlook의 사서함 정책](/powershell/module/exchange/client-access/set-owamailboxpolicy) 설정을 따릅니다. **정책에서 -SetPhotoEnabled** 설정을 해제한 경우 사용자는 프로필 사진을 추가, 변경 또는 제거할 수 없습니다. 따라서 관리자가 사진을 변경하면 프로필 사진이 팀에 동기화되지 않습니다.

<sup>8</sup> [온-프레미스에서 호스트되는 사서함에 대한 모임을 만들고 보기 위한 요구 사항](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) 섹션에 나열된 요구 사항을 충족해야 합니다.

<sup>9</sup> 최소 Exchange Online 계획 1 라이선스도 필요합니다. 자세한 내용은 프레미스 Teams 채팅 데이터 검색을 [참조하세요.](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)

<sup>10개</sup> On-프레미스 사용자는 웹 사서함 정책의 Teams 으로 설정되어 있는 경우에도 Outlook 프로필 사진을 업데이트할 `SetPhotoEnabled` 수 `false` 있습니다.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams를 최대한 활용하기 위한 요구 사항

Microsoft Teams는 다양한 Microsoft 365 및 Office 365 서비스와 작동하여 사용자에게 풍부한 환경을 제공합니다. 이 환경을 지원하려면 특정 기능이나 서비스를 사용하도록 설정하고 라이선스를 할당해야 합니다.

- 사용자에게 Exchange Online 라이선스를 할당해야 합니다.

- 팀 대화에서 파일을 공유하고 저장하려면 SharePoint Online이 필요합니다. Microsoft Teams는 온-프레미스에서 SharePoint를 지원하지 않습니다.

- 채팅에서 파일을 공유하려는 경우 사용자에게 SharePoint Online 라이선스를 할당해야 합니다. 사용자에게 SharePoint Online 라이선스가 할당되지 않고 사용하도록 설정되어 있지 않은 경우, 사용자는 Microsoft 365 또는 Office 365에 비즈니스용 OneDrive 저장소가 없습니다. 파일 공유는 채널에서 계속 작동하지만, 사용자는 Microsoft 365 또는 Office 365에서 비즈니스용 OneDrive 저장소가 없이는 채팅에서 파일을 공유할 수 없습니다.

- Microsoft Teams에서 팀을 만들려면 사용자가 Microsoft 365 그룹 만들기를 사용하도록 설정되어야 합니다.

  > [!IMPORTANT]
  > 사용자를 **Teams 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거하면 Outlook 및 기타 Office 앱에서 현재 상태가 중지될 수 있습니다. 현재 상태는 Teams에서 제대로 작동합니다. 이 문제를 해결하려면 Microsoft Teams의 오른쪽 위 모서리에 있는 프로필 사진을 선택한 다음 **설정** 을 선택합니다. **응용 프로그램** 의 **일반** 탭에서 **Office용 채팅 앱으로 Teams 등록(Office 응용 프로그램을 다시 시작해야 함)** 을 선택합니다. 이 옵션을 선택한 후 Outlook을 포함하여 모든 Office 앱을 닫았다가 다시 엽니다. Outlook을 열면 현재 상태 정보를 사용할 수 있습니다.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>온-프레미스에서 호스트되는 사서함에 대한 모임 만들기 및 보기 요구 사항

사서함이 온-프레미스에서 호스트되는 경우 모임을 만들고 보려면 다음 요구 사항을 충족해야 합니다.

- 필수 Teams 라이선스를 Azure Active Directory에 동기화된 사용자에게 할당해야 합니다.

- 사용자가 Azure Active Directory에 동기화되어 있어야 합니다. Azure AD Connect를 사용하여 Azure Active Directory와 동기화하는 방법에 대한 자세한 내용은 [하이브리드 ID 설명서](/azure/active-directory/hybrid/)를 참조하세요.

- 사서함은 Exchange Server 2016 누적 업데이트 3 이상에서 호스트됩니다.

- 자동 검색 및 Exchange 웹 서비스는 외부에 게시됩니다.

- OAuth 인증은 전체 하이브리드 구성(클래식 또는 최신)을 실행하는 Exchange 하이브리드 구성 마법사를 통해 구성하는 것이 좋습니다. 하이브리드 구성 마법사를 사용할 수 없는 경우, [Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)에 설명된 대로 OAuth 인증을 구성합니다.

  > [!NOTE]
  > Exchange에서 EvoSTS로 알려진 Teams 서비스에서의 OAuth 토큰을 신뢰합니다. 1단계로 충분하지만 단지 EvoSTS에 한합니다. ACS가 일정에서 약속 없음/다른 용무 중 조회에 사용됩니다.

- Azure AD Connect의 Exchange 하이브리드 배포 기능에 대한 확인란이 설정되어 있습니다. 자세한 내용은 하이브리드 [쓰기 Exchange 참조하세요.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#exchange-hybrid-writeback)

- Mac용 일정 앱 지원 및 Teams Outlook 추가 기능에서 Exchange 웹 서비스 URL은 Exchange 서비스 주체에 대한 테넌트 Azure AD에서 SPN으로 구성되어야 합니다. 이 단계는 하이브리드 구성 마법사를 사용하여 수행하거나 [하이브리드 최신 인증을 위한 수동 단계](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)를 따라 수행합니다.

이러한 사용자에 대해 일정 위임을 사용하려면 다음을 수행합니다.

- 또한 온라인과 온라인 간의 통합 및 [OAuth 구성에 설명된 비즈니스용 Skype 완료해야 Exchange Server.](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) 이러한 단계에서는 Teams 권한을 확인하는 데 필요한 권한을 애플리케이션에 제공합니다.
 
  > [!NOTE]
  > 2단계에는 위임에 필요하지 않은 ArchiveApplication에 대한 역할 할당이 포함됩니다.

- Teams 추가 기능을 Outlook 다른 사람을 대신하여 모임을 Outlook Exchange 2013 CU19 이상에서 2013 CU19 이상을 추가해야 합니다. 이는 서비스에서 사서함의 인증되지 않은 검색을 지원하여 위임자 사서함에 대한 대리인 권한을 검사하는 작업입니다. 대리인 및 위임자 위치는 Exchange 2013 이상 또는 Exchange Online일 수 있지만, 자동 검색은 Exchange 2013 CU19 이상으로 확인해야 합니다.

## <a name="additional-considerations"></a>추가 고려 사항

다음은 조직에서 Microsoft Teams를 구현할 때 고려해야 할 몇 가지 추가 사항입니다.

- Microsoft Teams에서 eDiscovery, 콘텐츠 검색, 보관 및 법률 보존 등의 보안 및 규정 준수 기능은 Exchange Online 및 SharePoint Online 환경에서 가장 잘 작동합니다. 채널 대화의 경우 메시지는 eDiscovery에 사용할 수 있는 Exchange Online의 그룹 사서함에 일지를 합니다. SharePoint Online 및 비즈니스용 OneDrive(회사 또는 학교 계정을 사용)를 조직 전체 및 사용자가 사용하도록 설정한 경우, Teams 내의 모든 파일에 대해 이러한 준수 기능도 사용할 수 있습니다.

- 조건부 액세스를 사용하여 Teams 및 Exchange에서 규정 준수 정책의 구성을 제어하고 보호합니다. 자세한 내용은 [조건부 액세스 정책이 Teams에서 작동하는 방식](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)을 참조하세요.

- 조직에서 모든 모임 토론을 검색할 수 있도록 하는 규정 준수 요구 사항이 있는 경우, 이끌이에게 Exchange 온-프레미스 사서함이 있으면 비공개 모임을 사용하지 않도록 설정해야 합니다. 자세한 내용은 [개인 모임 예약 허용](./meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)을 참조하세요.

- Exchange 하이브리드 배포에서는 채팅 참가자가 클라우드 기반 사서함 혹은 온-프레미스 사서함을 보유했는지에 관계 없이 채팅 메시지의 콘텐츠를 검색할 수 있습니다. 자세한 내용은 [온-프레미스 사용자에 대한 클라우드 기반 사서함 검색](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)을 참조하세요. Teams에서 콘텐츠를 검색하는 방법에 대한 자세한 내용은 [Microsoft 365 규정 준수 센터에서 콘텐츠 검색](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)을 참조하세요.

- 현재 상태를 확인하려면 Microsoft Teams에서 사서함이 Exchange Online 또는 온-프레미스에 호스트되는지 확인해야 합니다. 그런 다음 서비스는 사서함에 액세스하는 위치를 결정합니다. Teams 서비스에서 Exchange Online 서비스에 대한 REST API 호출을 통해 사서함 위치를 확인할 수 있도록 하려면 [하이브리드 구성 마법사를 사용하여 하이브리드 배포 만들기](/exchange/hybrid-deployment/deploy-hybrid)에 설명 된 대로 Exchange 하이브리드 구성 마법사를 실행하여 Exchange 하이브리드 환경을 배포해야 합니다. 

## <a name="troubleshooting"></a>문제 해결

항목에 대한 전체 문제 해결 가이드에 대한 자세한 내용은 반드시 [Microsoft Teams 및 Exchange 서버와의 상호 작용 문제](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)를 확인하세요.
