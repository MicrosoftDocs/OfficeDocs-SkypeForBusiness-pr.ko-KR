---
title: Teams에 공유
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 사용자가 Outlook의 전자 메일 및 전자 메일 첨부 파일을 Teams의 채팅 또는 채널로 공유할 수 있는 Teams 공유 기능에 대해 알아봅니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2ac9a38e16000829b391e77dffdd718ed349299
ms.sourcegitcommit: f5546acf02ec644225f6d0fb41f38b1912da6adf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66952762"
---
# <a name="share-to-teams-from-outlook"></a>Outlook에서 Teams에 공유

Outlook에서 Teams로 공유(Teams로 공유)를 사용하면 사용자가 Outlook에서 Teams의 채팅 또는 채널로 첨부 파일을 포함한 전자 메일을 공유할 수 있습니다.

## <a name="outlook-add-in-for-share-to-teams"></a>Teams에 공유용 Outlook 추가 기능 

Teams에 공유 기능을 사용하려면 Outlook용 추가 기능이 필요합니다. 이 추가 기능은 사용자가 Teams 웹앱 또는 Teams 데스크톱 클라이언트에 로그온할 때마다 자동으로 설치됩니다.

> [!NOTE]
> [Exchange Online Outlook용 추가 기능](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 및 [Exchange Online 클라이언트 액세스 규칙을](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 검토하여 Outlook용 추가 기능이 제대로 작동하는지 확인해야 합니다. 또한 연결된 환경을 사용하지 않도록 설정하면 Outlook의 추가 기능이 제대로 작동하지 않도록 방지할 수 있습니다. 자세한 내용은 [Office의 연결된 환경을](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 참조하세요. 공유 사서함은 추가 기능에서 지원되지 않습니다. 

Teams에 공유는 사용자가 채널을 전자 메일로 보낼 때와 동일한 전송 메커니즘을 사용합니다. 채팅에 공유하기 위해 전자 메일(전자 메일 첨부 파일 포함)이 보낸 사람의 OneDrive에 복사됩니다. 채널에 공유하려면 전자 메일 및 첨부 파일이 SharePoint의 **Email 메시지** 폴더에 복사됩니다.

Teams에 대한 Share용 Outlook 추가 기능은 [Outlook 추가 기능에 대한 세부 정보, Outlook 추가 기능에](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 대한 환경 요구 사항 및 요구 사항 집합 1.7에서 지원되는 특정 Outlook 클라이언트를 포함하는 Outlook 추가 기능 설명서에 설명된 대로 요구 사항 집합 1.7을 사용합니다.

## <a name="enabling-or-disabling-share-to-teams"></a>Teams에 공유 사용 또는 사용 안 함

다음 PowerShell cmdlet을 사용하여 사용자별로 Teams에 대한 공유용 Outlook 추가 기능을 선택적으로 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

> [!NOTE]
> 추가 기능을 사용하지 않도록 설정하는 것은 추가 기능이 설치된 후에만 가능합니다. 테넌트에서 모든 사용자를 사용하지 않도록 설정하려면 스크립트를 주기적으로 실행합니다.

Share에서 Teams에 사용하는 Outlook에 대한 추가 기능을 사용하지 않도록 설정하려면 [여기에 있는 cmdlet](/powershell/module/exchange/disable-app)을 실행합니다.

Share to Teams에서 사용하는 Outlook에 대한 추가 기능을 사용하도록 설정하려면 [여기에 있는 cmdlet](/powershell/module/exchange/enable-app)을 실행합니다.

## <a name="browsers-and-single-sign-on"></a>브라우저 및 Single Sign-On

웹용 Outlook 및 Outlook 데스크톱 클라이언트 둘 다에서 Teams에 공유하려면 브라우저 WebView를 사용합니다. 특정 브라우저를 사용하는 클라이언트에 대한 자세한 내용은 [Office 추가 기능에서 사용하는](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 브라우저를 참조하세요. 

> [!IMPORTANT]
> Teams에 공유하려면 사용자의 브라우저에 대해 타사 쿠키와 로컬 스토리지 액세스를 모두 사용하도록 설정해야 합니다.

Teams에 공유는 SSO(Single Sign-On)를 사용합니다. 즉, 사용자가 Teams에 공유를 통해 추가 기능을 사용할 때 자격 증명을 제공할 필요가 없습니다. 웹용 Outlook SSO는 기본적으로 URL을 <https://outlook.office365.com/owa/extSSO.aspx> <https://outlook.office.com/owa/extSSO.aspx> 지원하고 회신합니다. 베니티 도메인의 경우 관리자는 적절한 Azure Active Directory 회신 URL을 추가해야 합니다.
