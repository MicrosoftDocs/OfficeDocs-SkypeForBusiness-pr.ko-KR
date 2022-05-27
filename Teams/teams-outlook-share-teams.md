---
title: Teams 공유
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 사용자가 Outlook 전자 메일 및 전자 메일 첨부 파일을 Teams 채팅 또는 채널로 공유할 수 있는 Teams 공유 기능에 대해 알아봅니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682029"
---
# <a name="share-to-teams-from-outlook"></a>Outlook Teams 공유

Outlook Teams 공유(공유에서 Teams)를 사용하면 Outlook Teams 채팅 또는 채널에 첨부 파일을 포함한 전자 메일을 공유할 수 있습니다.

## <a name="outlook-add-in-for-share-to-teams"></a>공유에서 Teams 추가 기능 Outlook 

Teams 공유 기능을 사용하려면 Outlook 추가 기능이 필요합니다. 이 추가 기능은 사용자가 Teams 웹앱 또는 Teams 데스크톱 클라이언트에 로그온할 때마다 자동으로 설치됩니다.

> [!NOTE]
> Exchange Online Exchange Online 및 [클라이언트 액세스 규칙](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)[의 Outlook 대한 추가](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 기능을 검토하여 Outlook 대한 추가 기능이 제대로 작동하는지 확인해야 합니다. 또한 연결된 환경을 사용하지 않도록 설정하면 Outlook 대한 추가 기능이 제대로 작동하지 않도록 방지할 수 있습니다. 자세한 내용은 [Office 연결된 환경을](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 참조하세요.  

Teams 공유는 사용자가 채널을 전자 메일로 보낼 때와 동일한 전송 메커니즘을 사용합니다. 채팅에 공유하려면 전자 메일(전자 메일 첨부 파일 포함)이 보낸 사람의 OneDrive 복사됩니다. 채널에 공유하기 위해 전자 메일 및 첨부 파일이 SharePoint **전자 메일 메시지** 폴더에 복사됩니다.

Share to Teams Outlook 추가 기능은 Outlook [추가 기능 설명서](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)에 설명된 대로 요구 사항 집합 1.7을 사용합니다. 여기에는 Outlook 추가 기능에 대한 세부 정보, Outlook 추가 기능에 대한 환경 요구 사항 및 요구 사항 집합 1.7에서 지원되는 특정 Outlook 클라이언트가 포함됩니다.

## <a name="enabling-or-disabling-share-to-teams"></a>공유를 사용하도록 설정하거나 사용하지 않도록 설정하여 Teams

Share에서 Teams Outlook 추가 기능은 다음 PowerShell cmdlet을 사용하여 사용자별로 선택적으로 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

> [!NOTE]
> 추가 기능을 사용하지 않도록 설정하는 것은 추가 기능이 설치된 후에만 가능합니다. 테넌트에서 모든 사용자를 사용하지 않도록 설정하려면 스크립트를 주기적으로 실행합니다.

Share에서 Teams 데 사용하는 Outlook 대한 추가 기능을 사용하지 않도록 설정하려면 [여기에 있는 cmdlet](/powershell/module/exchange/disable-app)을 실행합니다.

Share에서 Teams 데 사용하는 Outlook 추가 기능을 사용하도록 설정하려면 [여기에 있는 cmdlet](/powershell/module/exchange/enable-app)을 실행합니다.

## <a name="browsers-and-single-sign-on"></a>브라우저 및 Single Sign-On

웹용 Outlook 및 Outlook 데스크톱 클라이언트 모두에서 Teams 공유는 브라우저 WebView에 의존합니다. 특정 [브라우저를 사용하는](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 클라이언트에 대한 자세한 내용은 Office 추가 기능에서 사용하는 브라우저를 참조하세요. 

> [!IMPORTANT]
> Teams 공유하려면 사용자의 브라우저에 대해 타사 쿠키와 로컬 스토리지 액세스를 모두 사용하도록 설정해야 합니다.

Teams 공유는 SSO(Single Sign-On)를 사용합니다. 즉, Share를 통해 추가 기능을 사용하여 Teams 때 사용자가 자격 증명을 제공할 필요가 없습니다. 웹용 Outlook SSO는 기본적으로 URL을 <https://outlook.office365.com/owa/extSSO.aspx> <https://outlook.office.com/owa/extSSO.aspx> 지원하고 회신합니다. 베니티 도메인의 경우 관리자는 적절한 Azure Active Directory 회신 URL을 추가해야 합니다.
