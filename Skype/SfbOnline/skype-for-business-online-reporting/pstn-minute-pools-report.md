---
title: PSTN 통화 시간 풀(분) 보고서
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
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
- Reporting
description: 새로운 비즈니스용 Skype 관리 센터 보고서 영역에는 조직의 통화 및 오디오 회의 활동이 표시됩니다. 이를 통해 보고서를 드릴다운하여 각 사용자의 활동에 대한 보다 세분화된 인사이트를 얻을 수 있습니다. 예를 들어 비즈니스용 Skype PSTN 분 풀 보고서를 사용하여 조직 내에서 이번 달에 소비된 시간(분)을 볼 수 있습니다.
ms.openlocfilehash: ac27e88b6e0f4945dde90f5e5f7bade31f20fe6a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776253"
---
# <a name="pstn-minute-pools-report"></a>PSTN 통화 시간 풀(분) 보고서

>[!NOTE]
>이 보고서는 미리 보기 고객에게만 제공됩니다.

새로운 비즈니스용 Skype 관리 센터 **보고서** 영역에는 조직의 통화 및 오디오 회의 활동이 표시됩니다. 이를 통해 보고서를 드릴다운하여 각 사용자의 활동에 대한 보다 세분화된 인사이트를 얻을 수 있습니다. 예를 들어 비즈니스용 **Skype PSTN** 분 풀 보고서를 사용하여 조직 내에서 이번 달에 소비된 시간(분)을 볼 수 있습니다.
  
사용 가능한 추가 [보고서는](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 보고서 개요를 참조하세요.
  
이 보고서는 다른 비즈니스용 Skype 보고서와 함께 조직의 활동에 대한 세부 정보를 제공합니다. 이러한 세부 정보는 조직에 대한 조사, 계획 및 기타 비즈니스 결정을 내리고 통신 크레딧을 설정할 때 매우 [유용합니다.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Microsoft 365 관리 센터에 관리자로 로그온하면 비즈니스용 Skype 보고서를 모두 볼 수 있습니다. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>비즈니스용 Skype PSTN 분 풀 보고서에 도착하는 방법

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

- 관리 센터 >   >  **비즈니스용 Skype 관리 센터 보고서**  >    >  **PSTN 분 풀로 이동하세요.**
    
> [!NOTE]
> 사용 하는 Microsoft 365 또는 Office 365 구독에 따라 여기에 표시된 모든 동일한 세부 정보가 표시 되지 않을 수 있습니다. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>비즈니스용 Skype PSTN 분 풀 보고서 해석

표시되는 각 열을 확인하여 사용자의 비즈니스용 Skype 분 풀을 볼 수 있습니다.
  
보고서의 모양입니다.
  
## 

![비즈니스용 Skype PSTN 분 풀 보고서](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![숫자 1](../images/sfbcallout1.png)<br/>이 표에는 라이선스(기능) 및 사용 위치별 분 풀 분석이 표시됩니다. 
*    **기능은 호출에** 사용되는 라이선스/서비스 계획입니다. 이 보고서에 표시될 수 있는 라이선스/서비스 계획은 다음과 같습니다.
     * MCOPSTN1 - 국내 통화 요금제(미국 3000분/1200분 EU 요금제)
     * MCOPSTN2 - & 국내 풀(미국/캐나다/PR, 1200분 유럽 국가) 및 국제 풀(600분)이 표시됩니다. 국내 -OR- 국제 한도에 도달할 때마다 분 한도에 도달합니다. 
     * MCOPSTN5 - 국내 통화 요금제(120분 통화 요금제)
     * MCOPSTN6 - 국내 통화 요금제(240분 통화 요금제)
     * MCOMEETADD - 오디오 회의
*    **기능 설명은** 호출에 활용되는 라이선스 유형에 대한 설명입니다.
*    **국가 분 풀은** 분 풀을 공유하는 사용자의 라이선스 사용 위치입니다. 
*    **사용된 분은** 매월 사용된 시간(분)입니다.
*    **총 분은** 월에 사용할 수 있는 총 시간(분)입니다. 
*    **사용된 비율은** 월에 사용된 분의 백분율입니다. 
***
![숫자 2](../images/sfbcallout2.png)<br/>열을 끌어 특정 열을 그룹화할 열을 클릭하고 **하나** 이상의 열에 있는 모든 데이터를 그룹화하는 보기를 만들려면 여기에 열 헤더를 끌어서 놓습니다. 
***
![숫자 3](../images/sfbcallout3.png)<br/>Excel로 내보내기 단추를 클릭하거나 탭하여 보고서 데이터를 Excel .csv 파일로 **내보낼 수도** 있습니다. <br/><br/> 이렇게 하면 모든 사용자의 데이터를 내보내고 추가 분석을 위해 간단한 정렬 및 필터링을 할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 테이블 내에서 정렬하고 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬을 위해 데이터를 내보내야 합니다.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>다른 비즈니스용 Skype 보고서를 보고 싶나요?

- [비즈니스용 Skype 활동 보고서](activity-report.md) 사용자가 얼마나 많은 피어 투 피어를 사용하고, 구성하고, 회의 세션에 참여하는지 볼 수 있습니다.
    
- [비즈니스용 Skype 장치 사용 현황 보고서](device-usage-report.md) Windows 기반 운영 체제와 비즈니스용 Skype 앱이 설치되어 있으며 IM 및 모임에 사용하는 모바일 장치를 비롯한 장치를 볼 수 있습니다.
    
- [비즈니스용 Skype 회의 이끌이 활동 보고서](conference-organizer-activity-report.md) IM, 오디오/비디오, 응용 프로그램 공유, 웹, /dial out을 사용하는 회의를 구성하는 사용자 수를 볼 수 있습니다. 제3자 및 /dial out - Microsoft.
    
- [비즈니스용 Skype 회의 참가자 활동 보고서](conference-participant-activity-report.md) 참가하는 IM, 오디오/비디오, 응용 프로그램 공유, 웹 및 전화 걸기 오디오 회의 수를 볼 수 있습니다.
    
- [비즈니스용 Skype 피어 투 피어 활동 보고서](peer-to-peer-activity-report.md) 사용자가 IM, 오디오/비디오, 응용 프로그램 공유 및 파일 전송을 얼마나 많이 사용하고 있는지 볼 수 있습니다.
    
- [비즈니스용 Skype 사용자가 차단한 보고서](users-blocked-report.md) 조직의 사용자가 PSTN 통화를 걸 수 없는 것을 볼 수 있습니다.

- [비즈니스용 Skype 세션 세부 정보 보고서](session-details-report.md) 개별 사용자의 통화 경험에 대한 세부 정보를 볼 수 있습니다.
    
## <a name="related-topics"></a>관련 항목
[관리 센터의 활동 보고서](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
