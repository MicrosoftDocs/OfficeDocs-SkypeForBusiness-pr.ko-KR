---
title: Exchange 통합 메시징 및 호스트형 음성 사서함 관리
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: PowerShell을 사용하여 Exchange 및 구독자 액세스 및 호스트된 음성 자동 전화 교환 같은 통합 메시징 기능을 비즈니스용 Skype 있습니다.
ms.openlocfilehash: 1a841b377fbc84d85f085dc9d479fa05cc0b2be4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238741"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Exchange 통합 메시징 및 호스트형 음성 사서함 관리

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

cmdlet 집합을 사용하여 Exchange 통합 메시징 및 호스팅된 음성 비즈니스용 Skype 온라인에서 관리할 수 있습니다.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>통합 Exchange 음성 메일 관리

UM(통합 메시징) 및 호스팅된 음성 Exchange 관리하기 위해 다음 cmdlet을 사용할 수 있습니다.
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **설명**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | UM이 호스팅된 서비스인 경우 자동 전화 교환 및 구독자 액세스 서비스에 사용되는 연락처 개체를 Exchange 관리합니다.  <br/><br/> 비즈니스용 Skype 온라인은 Exchange UM과 함께 작동하여 사용자 및 구독자 자동 전화 교환 음성 관련 기능을 제공합니다. 자동 전화 교환 호출이 자동으로 응답되고 올바른 사용자로 라우팅되는 방법을 제공합니다. 구독자 액세스를 사용하면 사용자가 UM에 Exchange 전자 메일, 음성 메시지, 연락처 및 일정 정보를 검색할 수 있습니다.  <br/><br/> Exchange UM을 호스팅 서비스로 제공하는 경우 Microsoft PowerShell을 사용하여 자동 전화 교환 및 구독자 액세스 서비스에 사용되는 연락처 개체를 만들어야 합니다. 이러한 개체는 **CsExUmContact** cmdlet을 사용하여 만들어 관리됩니다. <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | 조직에서 사용되는 호스팅 음성메일 정책을 관리합니다. 호스트된 음성 Exchange UM 서비스로 라우팅되는 방법을 지정합니다. 이러한 정책은 UM 호스팅 음성 Exchange 사용하도록 설정된 사용자만 영향을 미치게 됩니다.  <br/><br/> 사용자가 호스팅된 음성 메일에 사용하도록 설정되어 있는지 확인하기 위해 PowerShell 프롬프트에서 다음과 유사한 명령을 실행합니다.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
