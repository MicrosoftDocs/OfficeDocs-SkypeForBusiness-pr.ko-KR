---
title: Microsoft 팀에서 게스트 액세스 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 첫 번째 팀과 채널을 만들고, 초기 사용자를 미리 보고, 사용 및 피드백을 모니터링 하 고, 조직 전체 출시를 계획 하기 위한 리소스를 확보 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4751f274e4bc7a874c1469041787d7d145c11bb8
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637667"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft 팀에서 게스트 액세스 관리
======================================

> [!IMPORTANT]
> 변경 내용이 적용 되려면 몇 시간 정도 기다려야 할 수 있습니다. 

**게스트** 는 모든 Microsoft 365 비즈니스 표준, Office 365 Enterprise, Microsoft 365 비즈니스 기본 및 Office 365 교육 구독에 포함 된 microsoft 팀의 사용자 유형입니다. Microsoft 365 또는 Office 365 라이선스가 추가로 필요 하지 않습니다. [게스트 액세스 라이선스](#guest-access-licensing-limits) 에 대 한 자세한 내용을 확인 하세요.

팀 게스트 액세스는 테 넌 트 수준 설정 이므로 기본적으로 꺼져 있습니다. 게스트 액세스를 설정 하는 방법에 대 한 자세한 내용은 [팀에 대 한 게스트 액세스 설정 또는 해제](set-up-guests.md)또는 [게스트 액세스 검사 목록을](guest-access-checklist.md) 사용 하 여 설치를 안내 합니다.

게스트 액세스를 설정한 후에는 [조직의 팀 관리 설정](enable-features-office-365.md) 에서 설명한 컨트롤을 사용 하 여 게스트에 대 한 설정을 구성 하 고 [새 Microsoft 팀 관리 센터로 전환 하는 동안 팀을 관리할](manage-teams-skypeforbusiness-admin-center.md)수 있습니다.     
    
IT 관리자는 테 넌 트 수준에서 게스트를 추가 하 고, 게스트 사용자 정책 및 사용 권한을 설정 및 관리 하 고, 게스트 사용자 활동에 대 한 보고서를 가져올 수 있습니다. 이러한 컨트롤은 팀 관리 센터에서 사용할 수 있습니다. 게스트 사용자 콘텐츠 및 활동은 Microsoft 365 또는 Office 365의 나머지 부분을 준수 하 고 감사 보호 하 고 있습니다.

팀 소유자는 새 게스트를 초대 하 고 팀 관리 센터의 팀에 기존 디렉터리 게스트 사용자를 추가할 수 있습니다. **팀 팀**관리 페이지에서 게스트 사용자를 식별  >  **Manage teams** 하 고 **조직 전체 설정**  >  **게스트 액세스** 페이지에서 게스트에 대 한 채널 관련 기능을 설정 합니다. 설정에는 다음 그림과 같이 게스트가 채널을 만들고 업데이트 하 고 삭제할 수 있도록 허용 하는 것이 포함 됩니다.

![팀의 게스트 사용 권한 설정](media/manage-guest-access-image1.png)
  
Azure AD (Active Directory) 포털을 사용 하 여 게스트 및 Microsoft 365 또는 Office 365 및 팀 리소스에 대 한 액세스를 관리할 수 있습니다. 팀 게스트 액세스는 Azure AD business (B2B) 공동 작업 기능을 기본 인프라로 사용 하 여 id 속성, 멤버 자격, 다단계 인증 설정 등의 보안 원칙 정보를 저장 합니다. Azure AD B2B에 대 한 자세한 내용은 [AZURE AD b2b 공동 작업 이란 무엇 인가요?](https://go.microsoft.com/fwlink/p/?linkid=853011) [AZURE Active Directory B2B 공동 작업](https://go.microsoft.com/fwlink/p/?linkid=853020)에 대해 자세히 알아보세요.

> [!NOTE]
> Microsoft 팀은 테 넌 트에 대 한 게스트 사용자 추가를 허용 하거나 방지 하기 위해 항상 Azure AD 외부 설정을 따릅니다. 자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.


## <a name="guest-access-licensing-limits"></a>게스트 액세스 라이선스 제한

Teams에서는 추가할 수 있는 게스트 수를 제한하지 않습니다. 그러나 테넌트에 추가할 수 있는 총 게스트 수는 Azure AD 라이선스가 허용하는 항목을 기반으로 합니다. 일반적으로 라이선스가 있는 사용자 당 게스트 수는 5 명입니다. 자세한 내용은 [Azure AD B2B 공동 작업 라이선스](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)를 참조하세요.

이러한 라이선스 제한 사항으로 인해 (사용자의 테 넌 트를 최신으로 유지), 게스트 액세스를 정기적으로 검토 하 여 더 이상 필요 하지 않은 액세스 권한이 있는 사용자를 확인 해야 합니다. Azure AD를 사용 하 여 그룹 구성원 또는 응용 프로그램에 할당 된 사용자에 대 한 액세스 검토를 만들 수 있습니다. 되풀이 되는 access 리뷰를 만들면 시간을 절약할 수 있습니다. 응용 프로그램에 대 한 액세스 권한이 있거나 그룹의 구성원 인 사용자를 정기적으로 검토 해야 하는 경우 이러한 검토의 빈도를 정의할 수 있습니다. 

게스트 액세스 검토를 수행 하거나, 게스트에 게 자신의 구성원을 검토 하도록 요청 하거나, 응용 프로그램 소유자나 비즈니스 의사 결정권자에 게 액세스 검토를 수행 하도록 요청 합니다. Azure 포털을 사용 하 여 게스트 액세스 검토를 수행 합니다. 자세한 내용은 [AZURE AD access 리뷰를 사용 하 여 게스트 액세스 관리](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)를 참조 하세요.

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Azure AD access 리뷰에 대 한 필수 조건

Microsoft Enterprise Mobility + Security, E5에 포함 되어 있는 Azure AD의 Premium P2 버전에서 Access 리뷰를 사용할 수 있습니다. 자세한 내용은 [Azure Active Directory 버전](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)을 참조 하세요. 검토를 만들거나, 검토를 채우거 나, 액세스를 확인 하 여이 기능과 상호 작용 하는 각 사용자에 게 라이선스가 있어야 합니다.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>게스트 액세스 설정이 적용 되기까지 지연 되는 시간

Azure Active Directory의 게스트 액세스 설정의 경우 변경 내용이 Microsoft 365 또는 Office 365에 적용 되기까지 몇 시간이 소요 됩니다. 사용자가 팀에 게스트를 추가 하려고 할 때 "관리자에 게 문의" 라는 메시지가 표시 되는 경우 게스트 기능이 설정 되지 않았거나 설정이 아직 유효 하지 않을 수 있습니다. 게스트 액세스 설정 문제에 대 한 도움말은 [팀의 게스트 액세스 문제 해결](troubleshoot-guest-access.md)을 참조 하세요.

  
## <a name="external-access-federation-vs-guest-access"></a>외부 액세스 (페더레이션) 및 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>추가 정보

PowerShell을 사용 하 여 게스트 액세스를 관리 하는 방법에 대 한 자세한 내용은 [powershell을 사용 하 여 팀의 게스트 액세스 제어를](guest-access-powershell.md)참조 하세요.


