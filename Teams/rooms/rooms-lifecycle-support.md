---
title: 버전 지원
ms.author: dstrome
author: dstrome
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
description: 동적 지원 구조 및 해당 단계를 포함하여 Microsoft Teams 회의실에 대한 수명 주기 지원에 대해 자세히 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584f4661a39d21f916b2097c242f71b996c568e6
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662453"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams Rooms 앱 버전 지원
 
Microsoft Teams 회의실 앱은 1년에 몇 번 업데이트를 받을 수 있습니다. 각 업데이트는 GA(일반 공급) 릴리스 날짜로부터 12개월 동안 지원됩니다. 기술 지원은 12개월 전체에 대해 제공됩니다. 그러나 지원 구조는 동적이며, 최신 버전의 가용성에 따라 달라지는 두 가지 단계가 있습니다.

- **서비스 및 중요 업데이트 단계** \- 최신 버전의 Microsoft Teams Rooms 앱을 실행하면 보안 및 서비스 업데이트가 포함된 정기 업데이트를 *받게* 됩니다.

- **보안 업데이트 전용 단계** \- 새 버전의 Microsoft Teams Rooms 앱이 릴리스될 때 이전 버전의 앱에는 12개월의 나머지 12개월 주기에 대한 보안 업데이트로 지원 수준이 감소합니다. 

> [!NOTE]
> 최신 버전은 항상 서비스 및 중요 업데이트 단계에 있습니다. 중요한 업데이트를 경고하는 코드 결함이 발생하는 경우 수정을 받기 위해 최신 버전도 설치해야 합니다. 지원되는 다른 모든 버전은 보안 업데이트를 받을 자격이 있습니다.

버전에 대한 12개월 수명 주기가 만료되거나 이후 두 개 이상의 업데이트가 릴리스된 후 모든 지원이 종료됩니다. 그런 다음 고객은 지원되는 버전으로 업데이트해야 합니다.

모든 릴리스는 Microsoft Teams 회의실 릴리스 [정보에 나열됩니다.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Windows 10 릴리스 지원

Microsoft Teams 회의실에는 채널 서비스 옵션에 따라 Windows 10 IoT Enterprise 또는 Windows 10 Enterprise Semi-Annual 필요합니다. 이러한 다른 Windows 10 버전은 지원되지 않습니다.

- Windows 10 Enterprise LTSB(장기 서비스 분기) /LTSC(장기 서비스 채널) 버전
- Windows 10 IoT(사물 인터넷) Enterprise LTSB/LTSC 버전
- Windows 10 Pro 또는 Home Edition과 같은 다른 Windows 버전

Windows 10 기능 업데이트는 Microsoft Teams 회의실 장치에서 즉시 제공되거나 업데이트되지 않습니다. Windows 10 릴리스 정보 페이지에 게시된 일반 공급 날짜 이후 최대 [6개월의 의도적인 지연입니다.](https://docs.microsoft.com/windows/release-information/) 지연 시간은 Microsoft Teams 회의실 애플리케이션, 장치 하드웨어 및 인증된 오디오 비디오 주변 장치에 대한 Windows 10 릴리스 호환성의 유효성을 검사하는 데 사용됩니다. 유효성 검사는 Windows 10의 각 주요 릴리스를 적극적으로 개발하는 동안 시작되고 계속됩니다. 모든 장치 제조업체가 디바이스에 대해 업데이트된 이미지를 작성하고 Microsoft Teams에서 해당 이미지를 인증하고 테스트하는 데 시간이 더 필요합니다. 유효성 검사 기간 동안 Microsoft Teams Room 앱은  [비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 그룹 정책을 사용하여 Windows 10 기능 업데이트를 지연합니다. 호환성 문제가 발견 및 해결되면 Windows 스토어에서 새 앱 릴리스를 통해 그룹 정책을 업데이트하여 차단이 해제됩니다. Microsoft Teams Rooms 앱을 실행하는 장치는 야간 유지 관리 재부팅 중에 적절한 Windows 10 릴리스로 자동으로 업데이트됩니다. MSI 버전은 업데이트를 수동으로 관리하고자 하는 고객이 사용할 수 있습니다.  

> [!IMPORTANT]
> 유효성 검사 기간 동안 Microsoft  Teams 회의실 장치는 어떤 수단으로든 Windows 10의 다음 릴리스로 업데이트되지 않습니다. 여기에는 그룹 정책을 적용하거나 System Center 또는 기타 타사 디바이스 관리 서비스를 사용하는 것이 포함됩니다. 이러한 문제로 인해 Microsoft Teams Room 응용 프로그램에 문제가 발생하거나 장치를 사용할 수 없는 경우도 있습니다.  

다음 표에서는 Microsoft Teams 회의실을 지원하기 위해 확인된 권장 및 지원되는 Windows 10 버전을 보여줍니다. 모든 날짜는 ISO 8601 형식인 YYYY-MM-DD로 나열됩니다.

|버전  |가용성 날짜   |Microsoft Teams 회의실 지원 상태   |Microsoft Teams Rooms 최소 응용 프로그램 버전 | 권장되는 OS 빌드  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |유효성 검사에서 <br/>아직 지원되지 않습니다.|&#x2014; |19042.572 |
| 2004 |2020-05-27 |건너 <br/> 권장되지 않음|&#x2014; |19041.264 |
| 1909 |2019-11-12 |지원됩니다. <br/>권장 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |지원  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |지원되지 않습니다. <br/>알려진 호환성 문제 &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |지원되지 않습니다.                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |지원되지 않음                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |지원되지 않습니다.                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 버전 1809는 Microsoft Teams 회의실 응용 프로그램과의 호환성 문제로 인해 권장되지 않습니다. 이 특정 문제로 인해 야간 다시 시작 후에 Microsoft Teams Rooms 애플리케이션이 시작되지 않습니다. 이 문제는 Windows 10 버전 1903에서 해결되었습니다.  

&#x2781; Windows 10 버전 2004는 Microsoft Teams Rooms 응용 프로그램과의 호환성 문제로 인해 권장되지 않습니다. 이 특정 문제로 인해 야간 다시 시작 후에 Microsoft Teams Rooms 애플리케이션이 시작되지 않습니다. 

지원되는 버전의 Windows 10을 사용하는 경우 항상 Microsoft Teams 회의실 앱에 대한 최신 응용 프로그램 업데이트를 받을 수 있습니다.  

## <a name="related-topics"></a>관련 항목

[Microsoft Teams 회의실 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 회의실 릴리스 정보](rooms-release-note.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
