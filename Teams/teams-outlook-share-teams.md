---
title: Teams에 공유
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 사용자가 Outlook에서 Teams의 채팅 또는 채널로 전자 메일 및 전자 메일 첨부 파일을 공유할 수 있는 Teams 공유 기능에 대해 자세히 알아보습니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098224"
---
# <a name="share-to-teams-from-outlook"></a>Outlook에서 Teams에 공유

Outlook에서 Teams로 공유(Teams로 공유)를 사용하면 사용자가 Outlook에서부터 Teams의 채팅 또는 채널에 첨부 파일을 포함한 전자 메일을 공유할 수 있습니다.

## <a name="outlook-add-in-for-share-to-teams"></a>Teams에 공유를 위한 Outlook 추가 기능 

Teams에 공유 기능에는 Outlook에 대한 추가 기능이 필요합니다. 이 추가 기능은 사용자가 Teams 웹앱 또는 Teams 데스크톱 클라이언트에 로그온할 때마다 자동으로 설치됩니다.

> [!NOTE]
> [Exchange Online의 Outlook용](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 추가 기능 및 [Exchange Online의](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 클라이언트 액세스 규칙을 검토하여 Outlook용 추가 기능이 올바르게 있는지 확인합니다. 또한 연결된 환경을 사용 안 하게 하면 Outlook의 추가 기능도 제대로 작동하지 않을 수 있습니다. 자세한 [내용은 Office의 연결된](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 환경을 참조하세요.  

Teams에 공유는 사용자가 채널을 전자 메일로 보낼 때와 동일한 전송 메커니즘을 사용 합니다. 채팅에 공유하기 위해 보낸 사람 OneDrive에 전자 메일(전자 메일 첨부 파일 포함)이 복사됩니다. 채널에 공유하기 위해 전자 메일 및 첨부 파일이 SharePoint의 전자 메일 메시지 **폴더에** 복사됩니다.

Teams용 Outlook 추가 기능에서는 Outlook 추가 기능에 대한 세부 정보, Outlook 추가 기능에 대한 환경 요구 사항 및 요구 사항 집합 1.7에서 지원되는 특정 Outlook 클라이언트를 포함하는 Outlook 추가 기능 설명서에 자세히 설명된 요구 사항 집합 1.7을 사용합니다. [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)

## <a name="enabling-or-disabling-share-to-teams"></a>Teams에 공유 사용 또는 사용 안 하게 설정

Teams에 대한 Outlook 추가 기능을 선택적으로 사용하지 않도록 설정하거나 다음 PowerShell cmdlet을 사용하여 사용자당 사용하도록 설정할 수 있습니다.

> [!NOTE]
> 추가 기능을 사용할 수 없습니다. 추가 기능을 설치한 후에만 가능합니다. 테넌트의 모든 사용자에 대해 사용 안 을 적용하고자 하는 경우 주기적으로 스크립트를 실행합니다.

Teams에 공유에서 사용되는 Outlook에 대한 추가 기능을 사용하지 않도록 설정하고 여기에 있는 [cmdlet을 실행합니다.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Teams에 공유에서 사용되는 Outlook에 대한 추가 기능을 사용하도록 설정하려면 여기에서 찾은 [cmdlet을 실행합니다.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>브라우저 및 Single Sign-On

웹용 Outlook 및 Outlook 데스크톱 클라이언트에서 Teams에 공유하는 경우 브라우저 WebView를 사용합니다. 특정 브라우저를 사용하는 [클라이언트에](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 대한 자세한 내용은 Office 추가 기능에서 사용하는 브라우저를 참조하세요. 

> [!IMPORTANT]
> Teams에 공유하려면 타사 쿠키와 로컬 저장소 액세스를 모두 사용자의 브라우저에 사용하도록 설정해야 합니다.

Teams에 공유는 SSO(Single Sign-On)를 사용하기 때문에 사용자가 Teams에 공유를 통해 추가 기능을 사용할 때 자격 증명을 제공할 필요가 없습니다. 웹용 Outlook용 SSO는 기본적으로 https://outlook.office365.com/owa/extSSO.aspx URL을 지원하고 https://outlook.office.com/owa/extSSO.aspx 회신합니다. 베니티 도메인의 경우 관리자는 적절한 Azure Active Directory 회신 URL을 추가해야 합니다.