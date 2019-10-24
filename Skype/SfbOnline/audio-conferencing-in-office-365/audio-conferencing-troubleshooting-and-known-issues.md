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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft를 전화 접속 회의 공급자, 상태 및 일부 해결 방법으로 사용할 때 발생 하는 알려진 문제점 목록을 확인 하세요. '
ms.openlocfilehash: bfb76c23d3b1235bf67435e0af09ddef2a8852f3
ms.sourcegitcommit: bb8577aca8c7e0673b37634a24bf793c86c0537b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2019
ms.locfileid: "37642699"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>오디오 회의 문제 해결 및 알려진 문제

 **이 문서는 Microsoft를 오디오 회의 공급자로 사용 하는 비즈니스용 Skype 사용자를 위한 것입니다. 타사 ACP (오디오 회의 공급자)를 사용 하는 고객에 게는 적용 되지 않습니다.**
  
## <a name="troubleshooting-and-known-issues"></a>문제 해결 및 알려진 문제

Microsoft를 오디오 회의 공급자로 사용 하는 오디오 회의는 추적 되 고 활발 하 게 조사 되는 최신 문제를가지고 있으며 이후 버전의 Office 365에서 기능이 업데이트 될 때 문제가 발생할 수 있습니다.
  
여기서는 사용자가 조직에서 비즈니스용 Skype를 사용 하 여 오디오 회의를 설정 하 고 작업할 때 발생할 수 있는 문제를 해결할 때이를 참조로 사용 합니다.

|**문제**|**동작/증상**|**알려진 해결 방법**|**검색 날짜**|
|:-----|:-----|:-----|:-----|
|모임이 시작 될 때 입력 및 종료 알림이 켜져 있지만 모임이 시작 되 면 곧 해제 됩니다.  <br/> |기본적으로 참가자가 비즈니스용 Skype 앱과 전화 접속 하는 동안 참가 하는 모임에는 입력 및 종료 알림이 사용 되지 않습니다. 비즈니스용 Skype 앱의 **Skype 모임 옵션** 에서 알림을 사용 하도록 설정할 수 있습니다. 모든 참가자가 참가자에 게 전화를 걸고 참가 하는 모임에는 참가자 명단을 사용할 수 없기 때문에 기본적으로 입력 및 종료 알림이 사용 가능 하 게 설정 됩니다. 모임 참가자가 전화를 거는 경우에만 모임이 시작 되 면 입력 및 종료 알림이 설정 되지만 참가자가 비즈니스용 Skype 앱을 사용 하 여 참가 하는 경우 알림이 해제 됩니다. 이 기능을 끄면 비즈니스용 Skype 앱에서 **Skype 모임 옵션** 을 사용 하 여 알림을 다시 설정할 수 있습니다. <br/> |해결 방법 없음  <br/> |8/30/2017  <br/> |
|처음에 E5 라이선스를 할당 하 여 사용자를 프로 비전 한 경우 사서함을 사용 하도록 설정 하지 않은 경우 오디오 회의 시작 전자 메일이 사용자에 게 전달 되지 않을 수 있습니다.  <br/> |이런 경우 비즈니스용 Skype 관리 센터 또는 PowerShell을 사용 하 여 **오디오 회의** 를 사용 하 여 사용자의 오디오 회의 정보를 언제 든 지 다시 보낼 수 있습니다. [오디오 회의 설정이 변경 되 면 전자 메일 보내기 사용 또는 사용 안 함을](enable-or-disable-sending-emails-when-their-settings-change.md)참조 하세요.  <br/> **참고:** 사용자에 게 오디오 회의 PIN을 다시 보내려면 PIN을 재설정 해야 합니다. 비즈니스용 Skype 관리 센터에서 또는 PowerShell을 사용 하 여 **오디오 회의** 를 사용 하 여이 작업을 수행할 수도 있습니다.          |해결 방법 없음  <br/> |8/30/2017  <br/> |
|오디오 회의 통화가 사용 현황 보고서에 표시 되는 데 최대 24 시간이 소요 될 수 있습니다.  <br/> |향후 서비스 업데이트에서이 지역에 대 한 개선 사항을 확인 하 고 있습니다.  <br/> |해결 방법 없음  <br/> |8/30/2017  <br/> |
|Skype for Business 사용자가 모임을 잠근 후 발신자가 회의 브리지에 전화를 거는 경우 비즈니스용 Skype 앱에 사용자가 대기실에서 대기 중 이라는 알림이 없습니다.  <br/> |이는 현재 디자인에 따라 진행 되 고 있으며 향후 서비스 업데이트에서이 기능을 지 원하는 데 관련 하 여 피드백을 가져왔습니다.  <br/> |해결 방법 없음  <br/> |8/30/2017  <br/> |
|2019 년 3 월 1 일 이전에 오디오 회의 라이선스를 할당 받은 비즈니스용 Skype 서버 (프레미스) 사용자가 모임 초대에 전화 접속 좌표를 표시 하지 않을 수 있습니다.  <br/> |비즈니스용 Skype Server 사용자 프로 비전 오디오 회의는 해당 날짜까지 지원 되지 않습니다. 이제이 기능은 지원 되며 모임 구성 요소 이므로 [먼저](https://docs.microsoft.com/microsoftteams/meetings-first)사용할 수 있습니다. 사용자에 게 팀 라이선스가 있어야 합니다.  <br/> |프로 비전 파이프라인을 재 활성화 해야 합니다. 사용자의 오디오 회의 라이선스를 제거 하 고 몇 시간이 지난 후 라이선스를 다시 할당 합니다.  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>관련 항목

[Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
