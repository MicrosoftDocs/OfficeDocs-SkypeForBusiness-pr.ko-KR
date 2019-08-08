---
title: Microsoft 팀 게스트 액세스 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 이 검사 목록을 사용 하 여 Microsoft 팀에서 게스트 액세스를 설정할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8418c9386c635d1fc1662ee6df80dfae21908bd0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244441"
---
<a name="teams-guest-access-checklist"></a>팀 게스트 액세스 검사 목록
==========================================

조직의 기본 설정에 따라 Microsoft 팀에서 게스트 액세스 기능을 사용 하도록 설정 하 고 구성 하는 데 도움이 되는 검사 목록을 사용 합니다.

> [!NOTE] 
> 공동 작업 제한 사항은 [B2B 외부 공동 작업 사용 및 게스트 초대를 할 수 있는 사용자 관리를](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)참조 하세요.

## <a name="understand-the-limitations-for-guests"></a>게스트의 제한 사항 이해

게스트 환경에는 설계상의 제한 사항이 있습니다. 문제가 아닌 항목을 해결 하기 위해 게스트 환경을 이해 하 고 있는지 확인 하세요. 예를 들어 Microsoft 팀의 게스트에는 사용할 수 없는 몇 가지 기능이 나와 있습니다.

- 비즈니스용 OneDrive
- 팀 외부에서 사용자 검색
- 일정, 예약 된 모임 또는 모임 세부 정보
- PSTN
- 조직도
- 팀 만들기 또는 수정
- 팀 찾아보기
- 사용자 간 채팅에 파일 업로드
- 게스트는 사용자의 전체 전자 메일 ID를 알고 있는 경우에도 사용자가 팀 외부에서 검색 하 고 찾을 수 있습니다. 이를 방지 하기 위해 IT 관리자는 게스트를 고유한 가상 GAL으로 제한할 수 있는 [범위 디렉터리 검색](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) 등의 패턴을 사용할 수 있습니다.

자세한 내용은 [게스트 환경](guest-experience.md) 및 [Office 365 그룹의 게스트 액세스에](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)대해 알아보세요.

### <a name="guest-access-vs-external-access-federation"></a>게스트 액세스와 외부 액세스 (페더레이션) 비교

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> 현재 Microsoft 팀은 게스트 inviter 역할을 지원 하지 않습니다. Microsoft 팀에서 작업 하려면 "구성원을 초대할 수 있습니다." 토글을 게스트 액세스에 대해 "예"로 설정 해야 합니다. "구성원이" 초대 가능 "을" 아니요 "로 설정한 다음 Office 365 그룹 및 Microsoft 팀에서 게스트 액세스를 사용 하도록 설정 하면 관리자가 디렉터리에 대 한 게스트 초대를 제어할 수 있습니다. Guest가 디렉터리에 있으면 팀 소유자 인 관리자가 아닌 구성원에 따라 팀에 추가 될 수 있습니다.

## <a name="if-your-guests-are-seeing-license-errors"></a>게스트가 라이센스 오류를 보고 있는 경우

Microsoft 팀의 게스트 액세스는 Azure AD (azure Active Directory) Business to Business (B2B) 및 해당 라이선스 모델을 사용 합니다. 라이선스 오류가 표시 되는 경우 사용자가 조직에 게스트를 초대할 수 있도록 [B2B 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) 을 읽고 조직의 라이선스 요구 사항을 이해 해야 합니다.

몇 가지 주의할 사항이 있습니다.

- 게스트는 조직 외부의 사용자입니다. 직원, 출장 대리점, 출장 업체 등은 게스트로 추가할 수 없습니다. 계열사에도 마찬가지입니다.
- 초청 기관에 대해 게스트 라이선스가 계산 됩니다. 필요한 라이선스 수를 계산할 때이를 고려 합니다.
- 라이선스는 초대 된 게스트가 다른 Office 365 테 넌 트에서 온 것인지 또는 개인 전자 메일 주소를 사용 하는 조직에 게 계산 됩니다.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ 단계 1: Azure AD business 비즈니스에서 설정 구성

1. 테 넌 트 관리자로 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.
2. **Azure Active Directory** > **사용자** > **사용자 설정을**선택 합니다.
3. **외부 사용자**아래에서 **외부 공동 작업 설정 관리**를 선택 합니다.
   > [!NOTE]
   > **외부 공동 작업 설정은** **조직 관계** 페이지 에서도 사용할 수 있습니다. Azure Active Directory의 **관리**에서 **조직 관계** > **설정**으로 이동 합니다.
4. **외부 공동 작업 설정** 페이지에서 사용 하도록 설정할 정책을 선택 합니다.

  - **게스트 사용자 권한이 제한 됨**:이 정책은 디렉터리의 게스트에 대 한 사용 권한을 결정 합니다. **예** 를 선택 하 여 사용자, 그룹 또는 기타 디렉터리 리소스 열거와 같은 특정 디렉터리 작업에서 게스트를 차단 합니다. 게스트를 사용 하 여 디렉터리 데이터에 대 한 액세스 권한을 다른 사용자와 동일 하 게 지정 하려면 ( **아니요** )를 선택 합니다.
   - **게스트 inviter 역할의 관리자와 사용자는 초대할 수 있습니다**. "게스트 inviter" 역할의 관리자와 사용자가 게스트를 초대 하도록 허용 하려면이 정책을 **Yes**로 설정 합니다.
   - **구성원 초대 가능**: 해당 디렉터리의 관리자가 아닌 구성원이 게스트를 초대 하도록 허용 하려면이 정책을 **예로**설정 합니다.
   
       > [!NOTE]
       > 구성원을 **No** 에 **초대할 수** 있고 Office 365 그룹 및 Microsoft 팀에서 게스트 액세스를 사용 하도록 설정한 경우 관리자는 디렉터리에 대 한 게스트 초대를 제어할 수 있습니다. Guest가 디렉터리에 있으면 팀 소유자 인 관리자가 아닌 구성원에 따라 팀에 추가 될 수 있습니다. 자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.
   
   - **게스트 초대**: 게스트가 다른 게스트를 초대할 수 있도록 하려면이 정책을 **Yes**로 설정 합니다.
   - **게스트를 위한 전자 메일 1 회 암호 사용 (미리 보기)**: 일회성 암호 기능에 대 한 자세한 내용은 일회용 [암호 기반 전자 메일 인증 (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)을 참조 하세요.
   - **공동 작업 제한 사항**: 특정 도메인에 대 한 초대를 허용 하거나 차단 하는 방법에 대 한 자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)을 참조 하세요.

## <a name="-step-2-configure-office-365-groups"></a>□ 단계 2: Office 365 그룹 구성

1. Microsoft 365 관리 센터에서 **설정** > **서비스 & 추가 기능** > **Office 365 그룹**으로 이동 합니다.
2. 조직에서 그룹 **구성원을 액세스할 수 있도록 그룹 콘텐츠** 를 설정 하도록 허용 **** 해야 합니다. 이 설정이 해제 되어 있으면 게스트는 그룹 콘텐츠에 액세스할 수 없게 됩니다.
3. **그룹 소유자가 조직 외부의 사용자를 그룹에 추가 하도록 허용** 하는 **** 것이 설정 되어 있는지 확인 합니다. 이 설정을 끄면 팀 소유자가 새 게스트를 추가할 수 없게 됩니다. 게스트 액세스를 지원 하려면 최소한이 설정이 설정 되어 있어야 합니다.

     ![스크린샷에서는 Office 365 그룹을 표시 하거나 숨깁니다.](media/guest-access-checklist-office365.png)

이러한 설정을 구성 하는 방법에 대 한 자세한 지침은 [office 365 그룹에서 게스트 액세스 관리](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) 및 [office 365 그룹의 게스트 액세스 제어](Teams-dependencies.md#control-guest-access-in-office-365-groups)를 참조 하세요.
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ 단계 3: 테 넌 트 수준에서 게스트 액세스를 사용 하도록 설정

최소한 microsoft **팀 관리 센터**에서 microsoft 팀에 대 한 게스트 액세스를 설정 해야 합니다. 

1. 팀 관리 센터에서 **조직 전체 설정** > **게스트 액세스**를 선택 합니다.
2. **Microsoft 팀에서 게스트 액세스 허용** 을 설정으로 전환 **** 합니다.

    ![팀 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-set-up-guests-image1.png)

3. 이 페이지에서 필요한 다른 게스트 설정을 구성 합니다.
4. **저장**을 클릭 합니다.

자세한 지침은 [Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조 하세요.


## <a name="--step-4-configure-sharing-in-office-365"></a>□ 단계 4: Office 365에서 공유 구성 

사용자가 게스트를 추가할 수 있는지 확인 합니다. 방법은 다음과 같습니다.

1. Microsoft 365 관리 센터에서 **설정** > **보안 & 개인 정보**로 이동 합니다.

     ![스크린샷에서는 서비스 설정의 예를 보여 줍니다.](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. **공유**에서 **편집**을 선택 합니다.

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. **사용자가이 조직에 새 게스트를 추가할 수 있도록 허용** 을 선택한 다음 **저장**을 클릭 합니다. ****

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> 이 설정은 회원 들이 Azure AD의**외부 사용자** **설정** > 에서 설정을 **초대할 수** 있는 것과 같습니다.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ 단계 5: SharePoint에서 공유 설정 확인

1. Microsoft 365 관리 센터에 로그인 합니다.
2. **관리 센터**를 클릭 한 다음 **SharePoint**를 선택 합니다.
3. SharePoint 관리 센터에서 **공유**를 선택 합니다.
4. **조직 외부 공유 허용 안 함** 옵션이 선택 되어 *있지* 않은지 확인 합니다.
 
     ![스크린샷에는 SparePoint 온라인 설정 토글의 예가 나와 있습니다.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ 단계 6: 채널에 특정 설정 사용 

팀 응용 프로그램 개별 팀 수준에서 게스트가 채널을 만들고 업데이트 하 고 삭제할 수 있도록 게스트 권한을 구성 합니다. 관리자 외에도, 팀 소유자는이 설정을 구성할 수 있습니다.

![팀/채널 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-TeamsSettings2.png)

방법 비디오를 비롯 한 자세한 내용은 [Microsoft 팀의 게스트 액세스](guest-access.md)를 참조 하세요.


## <a name="troubleshooting"></a>해결사

Microsoft 팀에서 게스트를 추가 하는 데 문제가 있는 경우 [게스트 액세스 문제 해결 가이드](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)를 참조 하세요.


