---
title: Microsoft Teams 룸 앱 버전 지원
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 동적 지원 구조 및 해당 단계를 포함하여 Microsoft Teams 룸 수명 주기 지원에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 509f4da415d7a7bd583442f21bd46efc52c9984f
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706655"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 룸 앱 버전 지원
 
Microsoft Teams 룸 앱은 Windows 스토어를 통해 업데이트를 받습니다. 앱은 상록 제품 수명 주기를 사용하며 현재 및 다음 최신 버전의 앱만 지정된 시간에 지원됩니다. 앱은 회의실 사용을 위해 수정된 특정 버전의 Teams 데스크톱 앱을 번들로 묶습니다. Teams 데스크톱 앱은 2주마다 업데이트되지만 Teams 룸 앱은 덜 자주 업데이트됩니다. 즉, Teams 룸 앱 현재-1 버전은 최대 6개의 Teams 데스크톱 앱 업데이트 뒤에 있을 수 있으므로 Teams 룸 앱을 항상 최신 버전으로 업데이트하는 것이 좋습니다. [Teams 업데이트 프로세스](../teams-client-update.md)에 대해 자세히 알아봅니다.

Teams 룸 대한 지원 구조는 동적이며 최신 버전의 가용성에 따라 달라집니다. 최신 버전이 아닌 애플리케이션 버전에서 코드 결함이 발생하는 경우 수정 사항을 받으려면 최신 버전을 설치해야 합니다.

모든 릴리스는 [Microsoft Teams 룸 릴리스 정보에](rooms-release-note.md) 나열됩니다.

> [!IMPORTANT]
> 이전 버전의 Teams 룸 애플리케이션과 함께 제공되는 새 디바이스를 설치하는 경우 Windows 업데이트를 다운로드하기 전에 계정을 설정한 후 [애플리케이션을 수동으로 업데이트](manual-update.md) 하는 것이 좋습니다. 이렇게 하면 올바른 OS 버전과 Windows 업데이트가 디바이스에 설치됩니다.  

## <a name="windows-10-release-support"></a>Windows 10 릴리스 지원

Microsoft Teams 룸 Semi-Annual 채널 서비스 옵션에서 Windows 10 IoT Enterprise 또는 Windows 10 Enterprise SKU가 필요합니다. 이러한 다른 Windows 10 버전은 지원되지 않습니다.

- Windows 10 Enterprise LTSB(장기 서비스 분기) / LTSC(장기 서비스 채널) 버전
- IoT(사물 인터넷) 엔터프라이즈 LTSB/LTSC 버전 Windows 10
- 다른 Windows 버전(예: Windows 10 Pro 또는 Home Edition)

새로운 Windows 10 기능 업데이트는 Microsoft Teams 룸 디바이스에서 즉시 제공되지 않습니다. Windows 10 [릴리스 정보](/windows/release-information/) 페이지에 게시된 일반 공급 날짜 이후 최대 6개월 이상의 의도적인 지연이 있습니다. 이번에는 Microsoft Teams 룸 앱, 디바이스 하드웨어 및 인증된 오디오 비디오 주변 장치에 대한 Windows 10 릴리스 호환성의 유효성을 검사하는 데 사용됩니다. 유효성 검사는 Windows 10 각 주 릴리스의 활성 개발 중에 시작되고 계속됩니다. 모든 디바이스 제조업체가 디바이스에 대해 업데이트된 이미지를 빌드했는지 확인하고 Microsoft에서 해당 이미지를 인증하고 테스트하려면 추가 시간이 필요합니다. 유효성 검사 기간 동안 Microsoft Teams 룸 앱은 [비즈니스용 Windows 업데이트 그룹 정책을](/windows/deployment/update/waas-manage-updates-wufb) 사용하여 Windows 10 기능 업데이트를 지연합니다. 호환성 문제가 발견되고 해결되면 Windows 스토어의 새 앱 릴리스를 통해 그룹 정책을 업데이트하여 블록이 해제됩니다. Microsoft Teams 룸 앱을 실행하는 디바이스는 야간 유지 관리 재부팅 중에 적절한 Windows 10 릴리스로 자동으로 업데이트됩니다. 수동으로 업데이트를 관리해야 하는 고객이 MSI 버전을 사용할 수 있습니다.  

> [!IMPORTANT]
> 유효성 검사 기간 동안 Microsoft Teams 룸 디바이스는 어떤 수단으로든 Windows 10 다음 릴리스로 업데이트 **해서는** 안 됩니다. 여기에는 그룹 정책을 재정의하거나 System Center 또는 기타 타사 디바이스 관리 서비스를 사용하는 것이 포함됩니다. 이러한 경우 Microsoft Teams 룸 앱에 문제가 발생하거나 디바이스를 사용할 수 없게 될 수 있습니다.  

다음 표에서는 Microsoft Teams 룸 지원하는 것으로 확인된 권장 및 지원되는 Windows 10 버전을 보여줍니다. 모든 날짜는 ISO 8601 형식(YYYY-MM-DD)으로 나열됩니다.

| 버전 | 가용성 날짜 | Microsoft Teams 룸 지원 상태                    | Microsoft Teams 룸 최소 애플리케이션 버전 | 권장 OS 빌드 |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | 지원<br>권장                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | 지원되지 않음                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | 지원                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | 건너뜁니다 <br/> 권장되지 않는 &#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | 지원                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | 지원되지 않음                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | 지원되지 않음, <br/>알려진 호환성 문제 &#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | 지원되지 않음                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | 지원되지 않음                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | 지원되지 않음                                           | &#x2014;                                          | &#x2014;             |

&#x2780; Windows 10 버전 2004는 Microsoft Teams 룸 애플리케이션과의 호환성 문제로 인해 권장되지 않습니다. 이 특정 문제로 인해 야간 다시 부팅 후 Microsoft Teams 룸 애플리케이션이 시작되지 않습니다. 

&#x2781; Windows 10 버전 1809는 Microsoft Teams 룸 애플리케이션과의 호환성 문제로 인해 권장되지 않습니다. 이 특정 문제로 인해 야간 다시 부팅 후 Microsoft Teams 룸 애플리케이션이 시작되지 않습니다. 이 문제는 Windows 10 버전 1903에서 해결되었습니다.  

지원되는 버전의 Windows 10 사용하면 항상 Microsoft Teams 룸 앱에 대한 최신 애플리케이션 업데이트를 받게 됩니다.  


## <a name="related-topics"></a>관련 주제

[Microsoft Teams 룸 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[릴리스 정보 Microsoft Teams 룸](rooms-release-note.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
