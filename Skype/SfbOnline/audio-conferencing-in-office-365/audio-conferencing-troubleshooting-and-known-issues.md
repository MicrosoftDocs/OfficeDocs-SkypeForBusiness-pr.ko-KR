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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Microsoft를 전화 접속 회의 공급자로 사용할 때 알려진 문제 목록, 상태 및 일부 해결 방법을 확인할 수 있습니다. '
ms.openlocfilehash: fba5bfff687121c7b1b64c0e51233ccb576497e2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164526"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>오디오 회의 문제 해결 및 알려진 문제

 **이 문서는 Microsoft를 오디오 회의 공급자로 사용하는 비즈니스용 Skype 사용자를 위한 것입니다. 타사 ACP(오디오 회의 공급자)를 사용하는 고객에게는 적용되지 않습니다.**
  
## <a name="troubleshooting-and-known-issues"></a>문제 해결 및 알려진 문제

Microsoft를 오디오 회의 공급자로 사용하는 오디오 회의에는 현재 추적되고 적극적으로 조사되고 있으며 향후 Microsoft 365 릴리스에서 기능이 업데이트될 때 해결될 수 있는 현재 문제가 있습니다.
  
지금은 조직의 비즈니스용 Skype를 사용하는 사용자에 대해 오디오 회의를 설정하고 작업하는 데 잠재적인 문제를 해결할 때 참조로 사용하세요.

|**문제**|**동작/증상**|**알려진 해결 방법**|**확인 날짜**|
|:-----|:-----|:-----|:-----|
|입장 및 퇴장 알림은 모임이 시작되면 켜지지만 모임이 시작된 직후에는 해제됩니다.  <br/> |기본적으로 입장 및 퇴장 알림은 참가자가 비즈니스용 Skype 앱에서 참가하는 모임과 전화를 걸 때 사용할 수 없습니다. 비즈니스용 Skype 앱의 **Skype** 모임 옵션에서 공지 사항을 사용하도록 설정할 수 있습니다. 모든 참가자가 전화 접속하여 모임에 참가하는 모임의 경우 참가자가 참가할 수 없는 경우 입장 및 퇴장 알림이 기본적으로 설정됩니다. 모임이 시작된 경우 입장 및 퇴장 알림이 켜지지만 참가자가 비즈니스용 Skype 앱을 사용하여 참가하면 알림이 해제됩니다. 끄면 비즈니스용 Skype 앱에서 **Skype** 모임 옵션을 사용하여 알림을 다시 사용하도록 설정될 수 있습니다. <br/> |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|E5 라이선스가 할당되어 사용자가 처음으로 프로비전되는 경우 사서함이 활성화되지 않은 경우 오디오 회의 환영 전자 메일이 사용자에게 배달되지 않을 수 있습니다.  <br/> |이 경우 비즈니스용 Skype 관리 센터에서 오디오 회의를 사용하거나  PowerShell을 사용하여 사용자의 오디오 회의 정보를 언제든지 다시할 수 있습니다. 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 [을 참조하세요.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **참고:** 사용자에게 오디오 회의 PIN을 다시 보내기 위해 PIN을 다시 설정해야 합니다. 비즈니스용 Skype 관리  센터에서 오디오 회의를 사용하거나 PowerShell을 사용하여 이 기능을 사용할 수도 있습니다.          |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|오디오 회의 통화는 사용 현황 보고서에 표시하는 데 최대 24시간이 걸릴 수 있습니다.  <br/> |향후 서비스 업데이트에서 이 영역에 대한 개선을 기대합니다.  <br/> |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|비즈니스용 Skype 사용자가 모임을 잠긴 후 발신자 전화 회의 브리지에 전화를 걸면 사용자가 대기실에서 대기 중이라는 알림이 비즈니스용 Skype 앱에 없습니다.  <br/> |이 기능은 현재 설계되어 있지만 향후 서비스 업데이트에서 이 기능을 지원하는 데 대한 피드백을 제공했습니다.  <br/> |해결 방법이 없습니다.  <br/> |8/30/2017  <br/> |
|2019년 3월 1일 이전에 오디오 회의 라이선스를 할당한 비즈니스용 Skype Server(프레미스) 사용자가 모임 초대에 전화 접속 좌표를 표시하지 않을 수 있습니다.  <br/> |Teams 오디오 회의를 위한 비즈니스용 Skype Server 사용자 프로비전은 해당 날짜까지 지원되지 않습니다. 이제 지원됩니다. 모임 [우선의 구성 요소입니다.](https://docs.microsoft.com/microsoftteams/meetings-first) 사용자에게 Teams 라이선스가 있어야 합니다.  <br/> |프로비전 파이프라인을 다시 활성화해야 합니다. 사용자의 오디오 회의 라이선스를 제거하고 몇 시간 동안 기다렸다가 라이선스를 다시 재할당합니다.  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
