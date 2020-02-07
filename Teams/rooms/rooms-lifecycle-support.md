---
title: 버전 지원
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 수명 지원에 대해 설명 합니다.
ms.openlocfilehash: 0f445bf2500a01bf8ffddae569d176229bdcfde5
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825916"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft 팀 대화방 앱 버전 지원
 
Microsoft 팀 대화방 앱은 1 년에 여러 번 업데이트를 받습니다. 각 업데이트는 GA (일반 가용성) 릴리스 날짜에서 12 개월에 지원 됩니다. 전체 12 개월 동안 기술 지원이 제공 됩니다. 그러나 지원 구조는 다음과 같이 최신 버전의 사용 가능성에 따라 달라 지는 다음 두 단계를 포함 하는 동적입니다.

- **서비스 및 중요 업데이트 단계** \- 최신 버전의 Microsoft 팀 대화방 앱을 실행 하면 *보안 및 서비스* 업데이트를 포함 하는 정기 업데이트를 받을 수 있습니다.

- **보안 업데이트 상위** \- 버전의 Microsoft 팀 공간 앱이 출시 되는 경우 이전 버전의 앱은 나머지 12 개월 수명 주기 중에서 *보안 업데이트* 를 사용 하는 지원 수준 감소를 제공 합니다.

> [!NOTE]
> 최신 버전은 항상 서비스 및 중요 업데이트 단계에 있습니다. 중요 업데이트를 지 원하는 코드 오류가 발생 하는 경우에는 최신 버전을 설치 하 여 수정 프로그램을 받을 수도 있어야 합니다. 지원 되는 다른 모든 버전은 보안 업데이트를 받을 수만 있습니다.

이후 버전에 대 한 12 개월 수명 주기가 만료 되거나 두 개 이상의 업데이트가 끝난 후에는 모든 지원이 종료 됩니다. 고객은 지원 되는 버전으로 업데이트 해야 합니다.

모든 릴리스는 [Microsoft 팀 대화방 릴리스 노트](rooms-release-note.md)에 나열 되어 있습니다.

## <a name="windows-10-release-support"></a>Windows 10 릴리스 지원

Microsoft 팀 대화방에는 반기 채널 서비스 옵션에서 Windows 10 IoT Enterprise 또는 Windows 10 Enterprise Sku가 필요 합니다. 다음 Windows 10 버전은 지원 되지 않습니다.

- Windows 10 Enterprise 장기 서비스 분기 (LTSB)/장기 서비스 채널 (LTSC) 버전
- Windows 10의 인터넷 (IoT) Enterprise LTSB/LTSC edition
- Windows 10 Pro 또는 Home edition 등의 다른 Windows 버전

Windows 10 기능 업데이트가 Microsoft 팀 대화방 장치에서 즉시 제공 되거나 업데이트 되지 않습니다. [Windows 10 릴리스 정보](https://docs.microsoft.com/windows/release-information/) 페이지에 게시 된 일반 사용 가능 날짜가 지난 최대 6 개월 후의 의도적인 지연입니다. 지연 시간은 Microsoft 팀 대화방 응용 프로그램, 장치 하드웨어 및 인증 된 오디오 영상 주변 장치에 대 한 Windows 10 릴리스 호환성의 유효성을 검사 하는 데 사용 됩니다. 유효성 검사는 Windows 10의 각 주요 릴리스를 활성 개발 하는 동안 시작 되 고 계속 됩니다. 모든 장치 제조업체가 장치에 대 한 업데이트 된 이미지를 작성 하 고 Microsoft 팀이 해당 이미지를 인증 하 고 테스트 하는지 확인 하기 위해 추가 시간이 필요 합니다. 유효성 검사 기간 동안 Microsoft 팀 대화방 앱은 [비즈니스 그룹 정책에 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 를 사용 하 여 windows 10 기능 업데이트를 지연 합니다. 호환성 문제가 발견 되 고 해결 된 후 Windows 스토어에서 새 앱 릴리스를 통해 그룹 정책 업데이트를 통해 블록이 리프트 됩니다. Microsoft 팀 대화방 앱을 실행 하는 디바이스는 야간 유지 관리를 다시 부팅 하는 동안 적절 한 Windows 10 릴리스로 자동 업데이트 됩니다. 업데이트를 수동으로 관리 하려는 고객을 위해 MSI 버전을 사용할 수 있게 되었습니다.  

> [!IMPORTANT]
> 유효성 검사 기간 동안 Microsoft 팀 대화방 장치는 어떤 방법으로도 Windows 10의 다음 릴리스로 **업데이트 되어서는 안 됩니다.** 여기에는 그룹 정책 재정의 또는 System Center 또는 타사 장치 관리 서비스를 사용 하는 것이 포함 됩니다. 이러한 경우에는 Microsoft 팀 대화방 응용 프로그램에 문제가 발생할 수 있으며 장치를 사용할 수 없는 상태로 남을 수도 있습니다.  

다음 표에는 Microsoft 팀 대화방 지원 여부를 확인 하는 권장 및 지원 되는 버전의 Windows 10이 나와 있습니다. 모든 날짜는 ISO 8601 형식 (YYYY-MM-DD)으로 나열 됩니다.

|버전  |사용 가능 날짜   |Microsoft 팀 대화방 지원 상태   |Microsoft 팀 대화방 최소 응용 프로그램 버전 | 권장 OS 빌드  |
|:---  |:---       |:---                                  |:---     |:---     |
| 1909 |2019-11-12 |현재 유효성 검사 중 <br/>권장 되지 않음|&#x2014; |&#x2014; |
| 1903 |2019-05-21 |지원 되는 &#x2780;, <br/>권장  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |건너뛰면 <br/>권장 하지 않음 &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |지원                             |4.1.22.0 |17134.191|
| 1709 |2018-01-18 |지원되지 않음                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |지원 되지 않음                         |&#x2014; |&#x2014; |
||||||

인텔 그래픽 장치 드라이버 문제로 인해 플렉스 장치에서 Windows 10 1903를 사용 하 여 &#x2780; 수 없습니다. 이러한 장치에는 Windows 10 1903이 제공 되지 않습니다. 사용자는이 장치를 1903로 업그레이드 하 고 그래픽 드라이버 업데이트를 Crestron에서 사용할 때까지 Windows 10 1803에 유지 해야 합니다. 

Windows 10 1809 버전 &#x2781; Microsoft 팀 대화방 응용 프로그램과 호환성 문제가 발생 하 여 사용 하지 않는 것이 좋습니다. 이 특정 문제는 야간 재부팅 후 Microsoft 팀원의 룸 응용 프로그램이 시작 되지 않는 원인이 될 수 있습니다. 이 문제는 Windows 10 1903 버전에서 해결 되었습니다.  

지원 되는 버전의 Windows 10을 사용 하는 경우 항상 Microsoft 팀 대화방 앱에 대 한 최신 응용 프로그램 업데이트를 받게 됩니다.  

## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 팀 대화방 릴리스 정보](rooms-release-note.md)

[Microsoft 팀 회의실 계획](rooms-plan.md)
