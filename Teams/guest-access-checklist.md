---
title: Microsoft 팀 게스트 액세스 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 이 검사 목록을 사용 하 여 Microsoft 팀에서 게스트 액세스를 설정할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833258"
---
<a name="microsoft-teams-guest-access-checklist"></a>Microsoft 팀 게스트 액세스 검사 목록
==========================================

Microsoft 팀에서 게스트 액세스를 설정 하 고 구성 하는 데 도움이 되는 검사 목록을 사용 합니다. 이러한 변경 작업을 수행 하려면 전역 관리자 또는 팀 관리자 여야 합니다.

> [!IMPORTANT]
> 변경 내용이 적용 되려면 24 시간까지 기다려야 할 수 있습니다. 

이 짧은 비디오를 시청 하세요 (5:31 분). 팀을 포함 하 여 Microsoft 365에서 게스트 액세스를 설정 하는 방법을 알아보세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>1 단계: 조직 전체 수준에서 게스트 액세스 켜기 팀

게스트 액세스를 설정 하려면 **Microsoft 팀 관리 센터로**이동 합니다. 

1. 팀 관리 센터에서 **조직 전체 설정** > **게스트 액세스**를 선택 합니다.
2. **Microsoft 팀에서 게스트 액세스 허용** 을 **설정으로 전환 합니다.**

    ![팀 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-set-up-guests-image1.png)

3. 이 페이지에서 게스트에 대 한 **통화**, **모임**및 **메시징** 설정을 설정 하거나 해제 합니다.
4. **저장**을 클릭 합니다.

> [!TIP]
> Azure Active Directory, SharePoint Online 및 Office 365 그룹에서 기본 설정을 사용 하는 경우 게스트 액세스 구성이 완료 될 수 있습니다. 이 경우 나머지 단계를 건너뛸 수 있습니다. 확실 하지 않은 경우 또는 AAD, SharePoint Online 또는 Office 365 그룹에 대 한 사용자 지정 설정을 사용 하는 경우이 검사 목록의 나머지 단계를 계속 진행 합니다.

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>2 단계: Azure AD business 비즈니스에 대 한 설정 구성

팀에서 게스트 액세스를 지 원하는 Azure AD 설정은 다음과 같습니다. 이러한 설정이 구성 되 면 팀에서 게스트를 [추가](add-guests.md) 하 고 [관리할](manage-guests.md) 수 있습니다.

1. 테 넌 트 관리자로 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.
2. **Azure Active Directory** > **사용자** > **사용자 설정을**선택 합니다.
3. **외부 사용자**아래에서 **외부 공동 작업 설정 관리**를 선택 합니다.
   > [!NOTE]
   > **외부 공동 작업 설정은** **조직 관계** 페이지 에서도 사용할 수 있습니다. Azure Active Directory의 **관리**에서 **조직 관계** > **설정**으로 이동 합니다.
4. **외부 공동 작업 설정** 페이지에서 사용 하도록 설정할 정책을 선택 합니다.

    - **게스트 사용자 권한이 제한 됨**:이 정책은 디렉터리의 게스트에 대 한 사용 권한을 결정 합니다. **예** 를 선택 하 여 사용자, 그룹 또는 기타 디렉터리 리소스 열거와 같은 특정 디렉터리 작업에서 게스트를 차단 합니다. 게스트를 사용 하 여 디렉터리 데이터에 대 한 액세스 권한을 다른 사용자와 동일 하 게 지정 하려면 ( **아니요** )를 선택 합니다.
     - **게스트 inviter 역할의 관리자와 사용자는 초대할 수 있습니다**. "게스트 inviter" 역할의 관리자와 사용자가 게스트를 초대 하도록 허용 하려면이 정책을 **Yes**로 설정 합니다.
     - **회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오. 관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오**로 설정할 수 있습니다. **아니오**로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.
     - **게스트 초대**: 게스트가 다른 게스트를 초대할 수 있도록 하려면이 정책을 **Yes**로 설정 합니다.
         > [!IMPORTANT]
         > 현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.
     - **게스트를 위한 전자 메일 1 회 암호 사용 (미리 보기)**: 일회성 암호 기능에 대 한 자세한 내용은 일회용 [암호 기반 전자 메일 인증 (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)을 참조 하세요.
     - **공동 작업 제한 사항**: 특정 도메인에 대 한 초대를 허용 하거나 차단 하는 방법에 대 한 자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)을 참조 하세요.
        > [!NOTE]
        > 공동 작업 제한 사항은 [B2B 외부 공동 작업 사용 및 게스트 초대를 할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)를 참조 하세요.
      
    게스트를 초대할 수 있는 사용자를 제어하는 방법에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업에 대한 초대 위임](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)을 참조합니다.

## <a name="step-3-configure-office-365-groups"></a>3 단계: Office 365 그룹 구성

1. Microsoft 365 관리 센터에서 **설정** > **설정**으로 이동 하 여 **서비스**를 클릭 한 다음 **Office 365 그룹**을 선택 합니다.

     ![스크린샷에는 Office 365 Groups 설정이 나와 있습니다.](media/guest-access-checklist-services-settings.png)
2. **조직 외부 회원 그룹 구성원에 게 그룹 콘텐츠 액세스 허용** 확인란을 선택 했는지 확인 합니다. 이 설정을 선택 하지 않으면 게스트가 그룹 컨텐트에 액세스할 수 없게 됩니다.

    ![스크린샷에는 Office 365 Groups 설정이 나와 있습니다.](media/guest-access-checklist-office365.png)
3. **그룹 소유자가 조직 외부 사람을 그룹에 추가** 확인란을 선택 했는지 확인 합니다. 이 설정을 선택 하지 않으면 팀 소유자가 새 게스트를 추가할 수 없게 됩니다. 게스트 액세스를 지원 하려면 최소한이 설정이 설정 되어 있어야 합니다.

이러한 설정을 구성 하는 방법에 대 한 자세한 지침은 [office 365 그룹에서 게스트 액세스 관리](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) 및 [office 365 그룹의 게스트 액세스 제어](Teams-dependencies.md#control-guest-access-in-office-365-groups)를 참조 하세요.

## <a name="step-4-configure-sharing-in-office-365"></a>4 단계: Office 365에서 공유 구성 

사용자가 게스트를 추가할 수 있는지 확인 합니다. 방법은 다음과 같습니다.

1. Microsoft 365 관리 센터에서 **설정** > **설정**으로 이동 하 여 **보안 & 개인 정보**를 클릭 한 다음 **공유**를 선택 합니다.

     ![스크린샷에서는 서비스 설정의 예를 보여 줍니다.](media/guest-access-checklist-security-privacy-settings.png)
 
2. **사용자가이 조직에 새 게스트를 추가 하도록 허용** 확인란을 선택 하 고 **변경 내용 저장**을 클릭 합니다.

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > 이 설정은 회원 들이 Azure AD의**외부 사용자** **설정** > 에서 설정을 **초대할 수** 있는 것과 같습니다.  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>5 단계: SharePoint에서 공유 설정 확인

1. Microsoft 365 관리 센터에 로그인 합니다.
2. **관리 센터**에서 **SharePoint**를 선택 합니다.
3. 새 SharePoint 관리 센터의 **사이트**에서 **활성 사이트**를 선택 합니다.

    ![SharePoint 관리 센터의 활성 사이트](media/guest-access-checklist-SPOSettings0.png)

3. 사이트를 선택한 다음 **공유**를 클릭 합니다.
4. 이 옵션이 **사용자** 또는 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.

     ![SharePoint Online 설정/해제의 예를 보여 주는 스크린샷](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>6 단계: 게스트 사용자 권한 설정

팀 응용 프로그램 개별 팀 수준에서 게스트가 채널을 만들거나 업데이트 하거나 삭제할 수 있는지 여부를 제어 하는 게스트 권한을 구성 합니다. 팀 관리자는 물론 팀 소유자는 이러한 설정을 구성할 수 있습니다.

![팀/채널 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-TeamsSettings2.png)

게스트 액세스에 대 한 자세한 내용은 [팀에서 게스트 액세스](guest-access.md) 및 Microsoft 팀에 대 한 [게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조 하세요.

## <a name="troubleshooting"></a>해결사

팀에서 게스트 액세스를 설정 하거나 게스트를 추가 하는 데 문제가 있는 경우 다음 리소스를 사용 하 여 도움을 받으세요.

[Microsoft 팀의 게스트 액세스 문제 해결](troubleshoot-guest-access.md)

[팀 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
