---
title: 오디오 회의 문제 해결 및 알려진 문제
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Microsoft를 전화 접속 회의 공급자, 상태 및 일부 해결 방법을 사용할 때 알려진 문제의 목록을 얻습니다. '
ms.openlocfilehash: 6304de40d7c7cd9f3d798af2050276ee6fe2b104
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578162"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>오디오 회의 문제 해결 및 알려진 문제

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **이 문서는 Microsoft를 오디오 비즈니스용 Skype 공급자로 사용하는 사용자를 위한 문서입니다. ACP(타사 오디오 회의 공급자)를 사용하는 고객에게는 적용되지 않습니다.**
  
## <a name="troubleshooting-and-known-issues"></a>문제 해결 및 알려진 문제 해결

Microsoft를 오디오 회의 공급자로 사용하는 오디오 회의에는 추적되고 적극적으로 조사되는 현재 문제가 있으며 향후 릴리스에서 기능이 업데이트될 때 Microsoft 365.
  
지금은 오디오 회의를 설정하고 조직의 사용자에 대해 작업하는 데 잠재적인 문제를 해결할 때 참조로 비즈니스용 Skype 사용하세요.

|**문제**|**동작/증상**|**알려진 해결 방법**|**확인 날짜**|
|:-----|:-----|:-----|:-----|
|모임이 시작되면 항목 및 종료 알림이 켜지지만 모임이 시작된 직후 해제됩니다.  <br/> |기본적으로 참가자가 두 앱에서 참가하는 모임과 전화 접속 시 비즈니스용 Skype 알림을 사용하지 않도록 설정됩니다. 앱의 Skype 모임 **옵션에서** 공지 사항을 비즈니스용 Skype 있습니다. 모든 참가자가 전화 접속하여 모임에 참가하는 모임의 경우 참가자 등록명단을 사용할 수 없습니다. 모임을 호출하는 참가자만 시작하면 항목 및 종료 알림이 켜지지만 참가자가 앱 앱을 사용하여 참가하는 비즈니스용 Skype 알림은 해제됩니다. 해제되면 알림은 앱의 Skype 모임 옵션을  사용하여 다시 비즈니스용 Skype 수 있습니다. <br/> |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|사용자가 E5 라이선스를 처음 할당하여 프로비전되는 경우 사서함을 사용하도록 설정하지 않은 경우 오디오 회의 시작 전자 메일을 사용자에게 배달하지 않을 수 있습니다.  <br/> |이 경우 언제든지 관리자 센터 또는 PowerShell을 사용하여 오디오 회의를 사용하여 비즈니스용 Skype 수 있습니다.  오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 [을 참조하세요.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **참고:** 오디오 회의 PIN을 사용자에게 다시 보내기 위해 PIN을 다시 설정해야 합니다. 또한 관리 센터에서  오디오 회의를 비즈니스용 Skype PowerShell을 사용하여 수행될 수도 있습니다.          |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|오디오 회의 호출은 사용 현황 보고서에 표시하는 데 최대 24시간이 걸릴 수 있습니다.  <br/> |향후 서비스 업데이트에서 이 영역에 대한 개선을 기대하고 있습니다.  <br/> |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|사용자가 모임을 잠그고 나서 전화 회의 브리지에 비즈니스용 Skype 경우 사용자가 로비에서 대기 중이라 비즈니스용 Skype 앱에 알림이 없습니다.  <br/> |이 기능은 현재 설계에 따라 제공되지만 향후 서비스 업데이트에서 이 기능을 지원하는 데 대한 피드백을 제공했습니다.  <br/> |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|2019년 3월 1일 이전에 오디오 회의 라이선스를 할당한 비즈니스용 Skype 서버(프레미스) 사용자가 모임 초대에 좌표의 다이얼이 표시되지 않을 수 있습니다.  <br/> |오디오 비즈니스용 Skype 서버 사용자 Teams 프로비전은 해당 날짜까지 지원되지 않습니다. 이제 지원되는 모임 우선 [의 구성 요소입니다.](/microsoftteams/meetings-first) 사용자에게 라이선스가 Teams 있어야 합니다.  <br/> |프로비전 파이프라인을 다시 활성화해야 합니다. 사용자의 오디오 회의 라이선스를 제거하고, 몇 시간을 기다렸다가 라이선스를 다시 재할당합니다.  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>관련 항목

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
