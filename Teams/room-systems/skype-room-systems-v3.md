---
title: Microsoft 팀 대화방 관리 개요
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Microsoft 팀 대화방 관리 개요.
ms.openlocfilehash: 01b2550c1a0ad691acf48c58f6c13a37f2b4b7e6
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "36184280"
---
# <a name="management-overview"></a>관리 개요 

Microsoft 팀 대화방 시스템을 사용자가 사용할 수 있도록 하 고 훌륭한 사용자 환경을 제공 하기 위해 지속적인 유지 관리와 작업을 개발 하 고 실행 하는 것이 중요 합니다. 

## <a name="monitoring"></a>모니터 

Microsoft 팀 대화방 시스템의 모니터링은 다음과 같은 두 가지 주요 활동으로 구성 됩니다.

-  장치, 응용 프로그램 및 주변 장치 모니터링

-  품질 및 안정성 모니터링 (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft 팀 대화방 장치, 응용 프로그램 및 주변 장치 모니터링

사용자가 Microsoft 팀 대화방 단위를 사용할 수 있도록 하려면 단위가 켜져 있고, Microsoft 팀 대화방 응용 프로그램이 올바르게 구성 된 네트워크에 연결 되어 있으며, 제대로 작동 하는 주변 장치에 연결 되어 있어야 합니다. 


Microsoft 팀 공간 응용 프로그램 및 연결 된 주변 장치 상태에 대 한 정보는 Microsoft 팀 대화방 응용 프로그램이 Windows 이벤트 로그에 기록 하 고 [로그 항목을 이해](azure-monitor-manage.md#understand-the-log-entries)하는 데 문서화 되어 있습니다. 

|**설정**|**가능**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Microsoft 팀 회의실을 부팅할 수 있도록 설정  <br/> |
|전원 관리-\> AC, 10 분 후 화면 끄기  <br/> 전원 관리-\> AC, 시스템을 절전 모드로 전환 안 함  <br/> |Microsoft 팀 대화방에서 연결 된 디스플레이를 끄고 자동으로 절전 모드 해제 하도록 설정  <br/> |
|네트 계정/maxpwage: 무제한  <br/> 또는 동등한 방법으로 로컬 계정에서 암호 만료를 비활성화 합니다. 이 작업을 수행 하지 않으면 결국 Skype 계정에 만료 된 비밀 번호에 대 한 로그온 complaining 실패 하 게 됩니다. 이로 인해 컴퓨터의 모든 로컬 계정에 영향을 줄 수 있으므로이를 설정 하지 않으면 상자의 관리 계정도 결국 만료 됩니다.  <br/> |Skype 계정이 항상 로그인 할 수 있도록 합니다.  <br/> |
   
그룹 정책을 사용 하 여 파일을 전송 하는 방법에 대해서는 [파일 항목 구성을](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)설명 합니다.
  
## <a name="remote-management-using-powershell"></a>PowerShell을 사용 하 여 원격 관리
<a name="RemotePS"> </a>

Microsoft Operations Manager Suite를 사용 하 여 Microsoft 팀 회의실 시스템을 모니터링 하는 것이 좋습니다. 모니터링 및 기본 경고를 설정 하는 방법에 대 한 지침은 [Azure Monitor를 사용 하 여 Microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md)를 참조 하세요. 

이 지침을 사용 하 여 간편 하 게 사용할 수 있는 대시보드를 만들어 배포 전반에 걸친 Microsoft 팀 회의실 단위에 대 한 문제를 파악 합니다. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>결정 사항|<ul><li>운영 관리 도구 모음을 사용 하 여 Microsoft 팀 회의실 배포를 모니터링 하 고 있는지 확인 합니다.</li><li>전자 메일 알림에 사용할 대상 메일 그룹을 결정 합니다.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>품질 및 안정성 모니터링 방법을 정의 합니다.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>품질 및 안정성 모니터링 (CQD)

통화 및 모임 품질과 안정성 추세를 모니터링 하 여 중요 한 영역을 식별 하 고 해결을 진행 하는 데 도움이 되도록 배포의 일부로 지속적인 운영 품질 및 안정성 모니터링 절차를 구현 하는 것이 좋습니다. 

빌드 정보를 CQD에 업로드 하면 각 건물 수준에서 통화 품질 및 안정성 추세를 조사 하 여 쉽게 건물을 비교 하 고 특정 문제에 집중할 수 있습니다.

품질 및 안정성 추세를 식별 하 고 해당 문제를 해결할 작업 계획을 만들려면 [경험 치 검토 가이드](https://aka.ms/qerguide) 를 검토 하 고 팔 로우 하는 것이 좋습니다. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Microsoft 팀 대화방 OS 및 Microsoft 팀 대화방 응용 프로그램 업데이트

제품 업데이트 및 개선 기능 혜택을 얻으려면 Microsoft 팀 공간 OS 및 Microsoft 팀 공간 응용 프로그램을 업데이트 하는 것이 좋습니다. 자세한 지침은 [Microsoft 팀 대화방 관리](room-systems-v2-operations.md#software-updates)를 참조 하세요. 

## <a name="windows-updates"></a>Windows 업데이트

Microsoft 팀 대화방은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise (VL)에서 실행 되며 표준 데스크톱으로 동일한 Windows 업데이트 및 OS 빌드를 받습니다. 자세한 내용은 [Windows 업데이트 관리](updates.md) 를 참조 하세요.


## <a name="troubleshooting"></a>해결사

운영 팀과 헬프 데스크에 Microsoft 팀 대화방 문제에 대 한 알림이 표시 되도록 위의 섹션에서 설명한 대로 Operations Management Suite 경고를 설정 하는 것이 좋습니다. PowerShell 원격 관리에 사용할 수 있는 옵션은 PowerShell을 [사용 하 여 원격 관리](room-systems-v2-operations.md#remote-management-using-powershell)에 설명 되어 있습니다. 주변 장치에 대 한 연결이 끊어지면 로컬 "smart 핸 즈"를 사용 하거나 장치를 다시 연결 하는 기능을 지원 해야 할 수 있습니다. 

문제 해결 및 관리 모드에 대 한 자세한 내용은 [Microsoft 팀 대화방 관리](room-systems-v2-operations.md#admin-mode-and-device-management)를 참조 하세요. 


## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 도움말](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)

[Microsoft 팀 대화방 배포](room-systems-v2.md)

[Microsoft 팀 대화방 콘솔 구성](console.md)

[XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리](xml-config-file.md)
