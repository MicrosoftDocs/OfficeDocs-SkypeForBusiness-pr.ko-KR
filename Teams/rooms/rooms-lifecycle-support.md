---
title: Microsoft Teams 룸 버전 지원
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
ms.localizationpriority: medium
description: 동적 지원 구조 및 해당 단계를 포함하여 Microsoft Teams 룸 수명 주기 지원에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 937c6b43ebdc7c775251f0a7fc576cc11e666a7f
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367500"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 룸 버전 지원
 
앱 Microsoft Teams 룸 저장소를 통해 분기별 업데이트를 Windows 합니다. 긴급한 문제를 해결하기 위해 대역 외 업데이트를 할 수 있습니다. Microsoft Teams 룸 앱은 에버그린 제품 수명 주기를 사용하며, 현재 및 마지막 버전의 앱만 주어진 시간에서 지원됩니다. Microsoft Teams 룸 앱은 룸 사용을 위해 수정된 Teams 데스크톱 앱의 특정 버전을 번들로 제공합니다. 데스크톱 Teams 2주마다 업데이트됩니다. 업데이트 [프로세스에 대해 Teams 자세히 알아보면 됩니다.](../teams-client-update.md) 즉, Teams 룸 현재 1 버전은 데스크톱 앱 업데이트가 Teams 최대 6개일 수 있으므로 항상 최신 버전의 Teams Room 애플리케이션을 업데이트하는 Teams 룸 것이 좋습니다. 

지원 구조는 Teams 룸 동적이며 최신 버전의 가용성에 따라 달라집니다. 최신 버전이 아닌 애플리케이션 버전에서 코드 결함이 발생하는 경우 수정을 받기 위해 최신 버전을 설치해야 합니다.

모든 릴리스는 릴리스 Microsoft Teams 룸 [나열됩니다.](rooms-release-note.md)

> [!IMPORTANT]
> 이전 버전의 방 애플리케이션과 함께 제공된 새 디바이스를 Teams 업데이트를 다운로드하기 전에 계정을 설정한 후 애플리케이션을 수동으로 업데이트하는 Windows 것이 좋습니다. [](manual-update.md) 이렇게 하면 올바른 OS 버전과 Windows 업데이트가 장치에 설치됩니다.  

## <a name="windows-10-release-support"></a>Windows 10 릴리스 지원

Microsoft Teams 룸 채널 서비스 옵션에서 Windows 10 IoT Enterprise Windows 10 Enterprise SKUS를 Semi-Annual 필요합니다. 이러한 Windows 10 버전은 지원되지 않습니다.

- Windows 10 Enterprise LTSB(장기 서비스 분기) / LTSC(장기 서비스 채널) 버전
- Windows 10 IoT(사물 인터넷) Enterprise LTSB/LTSC 버전
- 다른 버전(예: Windows 또는 홈 Windows 10 Pro 버전)

새 Windows 10 기능 업데이트는 디바이스에서 즉시 Microsoft Teams 룸 없습니다. 릴리스 정보 페이지에 게시된 일반 가용성 날짜 이후 최대 [6개월](/windows/release-information/) Windows 10 있습니다. 이 시간은 Windows 10, 디바이스 하드웨어 및 Microsoft Teams 룸 오디오 비디오 주변 장치에 대한 릴리스 호환성의 유효성을 검사하는 데 사용됩니다. 유효성 검사는 각 주요 릴리스의 활성 개발 중에 시작되고 Windows 10. 모든 디바이스 제조업체가 해당 디바이스에 대해 업데이트된 이미지를 작성하고 해당 이미지를 인증하고 테스트하기 위해 Microsoft Teams 추가 시간이 필요합니다. 유효성 검사 기간 동안 Microsoft Teams Room 앱은 비즈니스용 Windows [업데이트](/windows/deployment/update/waas-manage-updates-wufb) 정책을 사용하여 기능 업데이트를 Windows 10 지연합니다. 호환성 문제가 발견 및 해결되면 저장소의 새 앱 릴리스를 통해 그룹 정책을 업데이트하여 Windows 해제됩니다. 앱을 Microsoft Teams 룸 디바이스는 야간 유지 관리 재부팅 중에 Windows 10 릴리스로 자동으로 업데이트됩니다. 업데이트를 수동으로 관리하고자 하는 고객에게 MSI 버전을 사용할 수 있습니다.  

> [!IMPORTANT]
> 유효성 검사 기간 동안 Microsoft Teams 룸 디바이스를 다음 릴리스로 업데이트하지 Windows 10 안 됩니다.  여기에는 그룹 정책을 적용하거나 다른 타사 System Center 관리 서비스를 사용하는 것이 포함됩니다. 이러한 중 어느 것이든 룸 앱에 Microsoft Teams 문제가 발생할 수 있습니다. 또는 디바이스를 사용할 수 없는 경우도 있습니다.  

다음 표에서는 권장되는 Windows 10 지원되는 버전을 보여 Microsoft Teams 룸. 모든 날짜는 ISO 8601 형식인 YYYY-MM-DD로 나열됩니다.

|버전  |가용성 날짜   |Microsoft Teams 룸 상태   |Microsoft Teams 룸 최소 애플리케이션 버전 | 권장 OS 빌드  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |지원되는 <br/>권장|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |건너뜁니다. <br/> 권장되지 &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |지원되는 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |지원되지 않습니다.  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |지원되지 않습니다. <br/>알려진 호환성 &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |지원되지 않습니다.                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |지원되지 않음                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |지원되지 않습니다.                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 버전 2004는 응용 프로그램과의 호환성 문제로 Microsoft Teams 룸 권장되지 않습니다. 이 특정 문제로 인해 Microsoft Teams 룸 다시 시작하지 못하게 됩니다. 

&#x2781; Windows 10 버전 1809는 응용 프로그램과의 호환성 문제로 Microsoft Teams 룸 권장되지 않습니다. 이 특정 문제로 인해 Microsoft Teams 룸 다시 시작하지 못하게 됩니다. 이 문제는 1903 버전 Windows 10 해결되었습니다.  

지원되는 버전을 사용하는 경우 Windows 10 앱에 대한 최신 애플리케이션 업데이트를 Microsoft Teams 룸 있습니다.  


## <a name="related-topics"></a>관련 항목

[Microsoft Teams 룸 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 릴리스 정보](rooms-release-note.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
