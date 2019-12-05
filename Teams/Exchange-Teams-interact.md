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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 622a173985d68260b210d844052d3b08dc5b5b88
ms.sourcegitcommit: b8e16703e4611ca2bde55896ec158b33be4f9ba0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39842430"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 및 Microsoft 팀의 상호 작용 방식

> [!Tip]
> 다음 세션에서 팀이 Azure Active Directory (AAD), Office 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용 하는 방법에 대해 알아보세요. [Microsoft 팀의 기초](https://aka.ms/teams-foundations)

전체 Teams 환경에서 모든 사용자에 대해 Exchange Online, SharePoint Online 및 Office 365 그룹 만들기가 가능하도록 설정해야 합니다.

사용자의 Exchange 사서함을 온라인 또는 온-프레미스로 호스트할 수 있습니다. 그러나 일부 기능을 사용 하려면 Office 365 테 넌 트를 통해 하이브리드 배포를 배치 해야 합니다.

Exchange Online 또는 Exchange 전용 vNext에서 호스팅되는 사용자는 팀의 모든 기능을 사용할 수 있습니다. 팀 및 채널을 만들고, 회의를 만들고, 채팅을 하 고, 사용자 프로필 사진을 수정 하 고, 커넥터, 탭, 인공 지능 추가 및 구성할 수 있습니다.

Exchange Online 전용 (레거시)에서 호스팅되는 사용자는 Office 365의 Azure Active Directory와 동기화 되어야 합니다. 팀과 채널을 만들고 참가 하 고, 탭 및 인공 지능을 추가 및 구성 하 고, 채팅 및 통화 기능을 활용할 수 있습니다. 그러나 프로필 사진을 수정 하거나, 모임을 관리 하거나, outlook 연락처에 액세스 하거나, 연결선을 관리할 수는 없습니다.

온-프레미스에 호스팅되는 사서함이 있는 사용자는 Azure Active Directory와 동기화 되어야 합니다. 위의 시나리오에서 모든 기능을 사용할 수 있지만, 또한 사용자 프로필 사진을 변경 하 고 모임 관리를 위해 Exchange Server 2016 (누적 업데이트 3)을 제공 하 여 온-프레미스로 실행할 수도 있습니다.

다음 표에서는 Exchange 환경을 기반으로 하는 기능 가용성에 대 한 유용한 빠른 참조를 제공 합니다.


**지원 되는 작업:**

| 사용자의 사서함이 호스트 되는 위치: | eDiscovery| 법률&nbsp;보류 | 보관| 팀 및 채널 관리 |모임 만들기 및 보기| 사용자 프로필 사진 수정 | 통화 기록 | 연락처 관리 | Outlook 연락처에 액세스 | 음성 메일 |커넥터 추가 및 구성|탭 추가 및 구성|봇 추가 및 구성| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|예 <sup>2</sup>|예 <sup>2</sup>|예|예|예|예|예|예|예|예|예|예|예|
|**Exchange Online 전용 vNext**|예 <sup>2</sup>|예 <sup>2</sup>|예|예|예|예|예|예|예|예|예|예|예|
|**Exchange Online 전용-레거시** (Azure AD와 동기화 필요)|예 <sup>2</sup>|예 <sup>2, 3</sup>|예 <sup>4|예|아니요|아니요|예|예|아니요|예 <sup>5|예 <sup>6|예|예|
|**Exchange 온-프레미스** (Azure AD와 동기화 필요)|예 <sup>2</sup>| 예 <sup>2, 3</sup> |예 <sup>4|예|Yes (Exchange 2016 CU3 이상 +)|Yes (Exchange 2016 CU3 이상 +)|예|예|아니요|예 <sup>5|예 <sup>6|예|예|

<sup>1</sup> EXCHANGE 2016 cu3 이상 이상 지원 됩니다.  

모든 호스팅 옵션에 대해 채널 메시지의 준수에 대 한 eDiscovery 및 법적 보류가 <sup>2 개</sup> 지원 됩니다.

<sup>3</sup> 팀 개인 채팅 메시지는이 호스팅 옵션의 법률 보존에 대해 아직 지원 되지 않습니다.

<sup>4</sup> 보존은 온라인 사용자가 메시지를 저장할 때 그림자 사서함을 사용 합니다. [Microsoft 팀은 Exchange 하이브리드 환경에서 팀 사용자를 위해 eDiscovery를 지원](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)합니다.

<sup>5 개의</sup> 팀-온-프레미스 Exchange 사서함이 있는 사용자는 Outlook에서 팀과 보이스 메일을 사용할 수 있지만, 음성 메일 메시지는 팀 클라이언트 내에서 보거나 재생할 수 없습니다.

<sup>6</sup> 팀 소유자 중 한 명에 게 커넥터를 추가할 수 있는 경우 해당 팀의 다른 사용자는 자신의 사서함이 온-프레미스 인 경우에도이 작업을 수행할 수 있습니다.


추가 정보:

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft 팀을 최대한 활용 하기 위한 요구 사항

Microsoft 팀은 다양 한 Office 365 서비스를 사용 하 여 사용자에 게 풍부한 환경을 제공 합니다. 이 환경을 지원 하려면 특정 기능 또는 서비스를 사용 하도록 설정 하 고 라이선스를 할당 해야 합니다.

- 팀 대화에서 파일을 공유 하 고 저장 하려면 SharePoint Online이 필요 합니다. Microsoft 팀은 SharePoint 온-프레미스를 지원 하지 않습니다.

- 채팅에서 파일을 공유 하려는 경우 사용자에 게 SharePoint Online 라이선스를 할당 해야 합니다. 사용자가 SharePoint Online 라이선스를 할당 하 고 사용 하도록 설정 하지 않은 경우 Office 365의 비즈니스용 OneDrive 저장소가 없습니다. 파일 공유는 채널에서 계속 작동 하지만, 사용자는 Office 365의 비즈니스용 OneDrive 저장소 없이는 채팅에서 파일을 공유할 수 없습니다.

- Microsoft 팀에서 팀을 만들려면 Office 365 그룹 만들기가 사용 하도록 설정 되어 있어야 합니다.

- Microsoft 팀이 Exchange 온-프레미스에서 작업 하도록 하려면 [exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)에 설명 된 대로 새 Exchange OAuth 인증 프로토콜을 구성 해야 합니다.

> [!NOTE]
>Exchange 온-프레미스 및 팀 통합의 경우 AAD 동기화 된 사용자에 대해 필요한 라이선스를 할당 해야 합니다.

> [!IMPORTANT]
> 사용자를 **팀 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거 하는 경우 Outlook 및 다른 Office 앱에서 현재 상태가 중지 될 수 있습니다. 팀에서 상태는 제대로 작동 합니다. 이 문제를 해결 하려면 Microsoft 팀의 오른쪽 위 모서리에서 프로필 사진을 선택한 다음 **설정을**선택 합니다. **일반** 탭의 **응용 프로그램**에서 **Office 용 채팅 앱으로 팀 등록 (office 응용 프로그램을 다시 시작 해야 함)** 을 선택 합니다. 이 옵션을 선택한 후 Outlook을 포함 하 여 모든 Office 앱을 닫았다가 다시 엽니다. Outlook을 열면 현재 상태 정보를 사용할 수 있게 됩니다.

## <a name="additional-considerations"></a>추가 고려 사항

다음은 조직에서 Microsoft 팀을 구현할 때 고려해 야 할 몇 가지 추가 사항입니다.

- Microsoft 팀에서 eDiscovery, 콘텐츠 검색, 보관, 법률 보호 등의 보안 및 규정 준수 기능이 Exchange Online 및 SharePoint Online 환경에서 가장 잘 작동 합니다. 채널 대화의 경우 메시지가 eDiscovery에 사용할 수 있는 Exchange Online의 그룹 사서함으로 저널링 됩니다. 조직 전체에서 SharePoint Online 및 비즈니스용 OneDrive (회사 또는 학교 계정을 사용)를 사용 하는 경우 팀 내의 모든 파일에 대해 이러한 준수 기능을 사용할 수 있습니다.

- 조건부 액세스를 사용 하 여 팀 및 Exchange에서 준수 정책의 구성을 제어 하 고 보호 합니다. 자세한 내용은 [팀에 대 한 조건부 액세스 정책 작동 방법](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) 보기를 참조 하세요. .

- 조직에 모든 모임 토론을 검색할 수 있는 규정 준수 요구 사항이 있는 경우 이끌이에게 Exchange 온-프레미스 사서함이 있는 경우 개인 모임을 사용 하지 않도록 설정 해야 합니다.

- Exchange 하이브리드 배포의 경우 채팅 참가자가 클라우드 기반 사서함을가지고 있는지 아니면 온-프레미스 사서함을 사용 하 든 관계 없이 채팅 메시지의 콘텐츠를 검색할 수 있습니다. 자세한 내용은 [Office 365에서 온-프레미스 사용자에 대 한 클라우드 기반 사서함 검색](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)을 참조 하세요. 팀에서 콘텐츠를 검색 하는 방법에 대 한 자세한 내용은 [Office 365 보안 & 준수 센터에서 콘텐츠 검색](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)을 참조 하세요.

> [!TIP]
> Azure AD Connect를 사용 하 여 Azure Active Directory와 동기화 하는 방법에 대 한 자세한 내용은 [온-프레미스 id를 Azure Active directory와 통합](https://go.microsoft.com/fwlink/?linkid=854600)을 참조 하세요.
