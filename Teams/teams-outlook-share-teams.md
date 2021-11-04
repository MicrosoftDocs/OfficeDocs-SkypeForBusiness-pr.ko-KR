---
title: 공유 Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 공유 및 Teams 기능에 대해 자세히 알아보면 사용자가 전자 메일 및 전자 메일 첨부 파일을 Outlook 모든 채팅 또는 채널로 공유할 수 Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd8e31f83927c459f4a188f7316d000c13e5ef91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774268"
---
# <a name="share-to-teams-from-outlook"></a>공유를 Teams Outlook

공유 Teams(Outlook 공유에서 Teams)를 사용하면 사용자가 Outlook 모든 채팅 또는 채널에 첨부 파일을 포함한 전자 메일을 공유할 수 Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook 공유에 대한 추가 Teams 

공유에서 Teams 기능에는 추가 기능이 Outlook. 이 추가 기능은 사용자가 웹앱 또는 Teams 데스크톱 클라이언트에 로그온할 때마다 Teams 설치됩니다.

> [!NOTE]
> 추가 기능을 [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 올바르게 Outlook Exchange Online 및 클라이언트 액세스 Exchange Online [](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 추가 기능을 Outlook 확인합니다. 또한 연결된 환경을 사용 안 하게 하면 추가 기능을 Outlook 방지할 수 있습니다. 자세한 [내용은 Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 연결된 환경을 참조하세요.  

공유 Teams 사용자가 채널을 전자 메일로 보낼 때와 동일한 전송 메커니즘을 사용하세요. 채팅에 공유하기 위해 전자 메일(전자 메일 첨부 파일 포함)을 보낸 사람이 보낸 사람 OneDrive. 채널에 공유하기 위해 전자 메일 및 첨부  파일이 전자 메일 메시지 폴더에 SharePoint.

공유를 위한 Outlook 추가 기능 Teams 요구 사항 집합 1.7을 사용하는 [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)경우 추가 기능 Outlook Outlook 추가 기능에 대한 세부 정보, Outlook 추가 기능의 환경 요구 사항 및 요구 사항 집합 1.7에서 지원되는 특정 Outlook 클라이언트에 대한 세부 정보를 포함하는 추가 기능 설명서에 자세히 설명되어 있습니다.

## <a name="enabling-or-disabling-share-to-teams"></a>공유를 사용하도록 설정하거나 Teams

공유에 Outlook 추가 기능을 Teams 다음 PowerShell cmdlet을 사용하여 사용자당 선택적으로 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

> [!NOTE]
> 추가 기능을 사용할 수 없습니다. 추가 기능을 설치한 후에만 가능합니다. 테넌트의 모든 사용자에 대해 사용 안 을 적용하고자 하는 경우 주기적으로 스크립트를 실행합니다.

공유에서 사용하는 Outlook 추가 기능을 사용하지 않도록 Teams 에서 [찾은 cmdlet을 실행합니다.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Share에서 Outlook 추가 기능을 사용하도록 설정하려면 Teams [cmdlet을 실행합니다.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>브라우저 및 Single Sign-On

공유 Teams 데스크톱 클라이언트와 웹용 Outlook Outlook 모두에서 브라우저 WebView를 사용합니다. 클라이언트가 특정 [브라우저를 사용하는 Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 자세한 내용은 추가 기능에서 사용하는 브라우저를 참조하세요. 

> [!IMPORTANT]
> 공유를 Teams 사용자의 브라우저에 대해 타사 쿠키와 로컬 저장소 액세스를 모두 사용하도록 설정해야 합니다.

공유 Teams SSO(Single Sign-On)를 사용하게 하여 공유를 통해 추가 기능을 사용할 때 사용자가 자격 증명을 제공할 필요가 Teams. SSO는 웹용 Outlook URL을 지원하고 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx 회신합니다. 베니티 도메인의 경우 관리자는 적절한 회신 URL을 Azure Active Directory 필요합니다.