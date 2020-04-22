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
description: 새로운 비즈니스용 Skype 관리 센터 보고서 영역에 조직의 통화 및 오디오 회의 활동이 표시 됩니다. 이 기능을 사용 하면 보고서를 자세히 분석 하 여 각 사용자의 활동에 대 한 세부적인 통찰력을 제공할 수 있습니다. 예를 들어 비즈니스용 Skype PSTN 시간 수영장 보고서를 사용 하 여 조직 내 현재 달 중 사용 되는 시간 (분)을 확인할 수 있습니다.
ms.openlocfilehash: ac27e88b6e0f4945dde90f5e5f7bade31f20fe6a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776253"
---
# <a name="pstn-minute-pools-report"></a>PSTN 통화 시간 풀(분) 보고서

>[!NOTE]
>이 보고서는 고객 미리 보기에만 사용할 수 있습니다.

새로운 비즈니스용 Skype 관리 센터 **보고서** 영역에 조직의 통화 및 오디오 회의 활동이 표시 됩니다. 이 기능을 사용 하면 보고서를 자세히 분석 하 여 각 사용자의 활동에 대 한 세부적인 통찰력을 제공할 수 있습니다. 예를 들어 **비즈니스용 SKYPE PSTN 시간 수영장** 보고서를 사용 하 여 조직 내 현재 달 중 사용 되는 시간 (분)을 확인할 수 있습니다.
  
사용할 수 있는 보고서에 대 한 자세한 내용은 [보고서 개요](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 를 확인 하세요.
  
이 보고서는 다른 비즈니스용 Skype 보고서와 함께 조직 전체의 활동에 대 한 세부 정보를 제공 합니다. 이러한 세부 정보는 조직에 대 한 기타 비즈니스 의사 결정과 [통신 크레딧을](/microsoftteams/what-are-communications-credits) 설정 하는 데 매우 유용 합니다.
  
> [!NOTE]
> Microsoft 365 관리 센터에 관리자로 로그온 하면 모든 비즈니스용 Skype 보고서를 볼 수 있습니다. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>비즈니스용 Skype PSTN 시간 풀 보고서에 액세스 하는 방법

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

- 관리 센터로 이동 > **관리** > 센터**비즈니스용 Skype 관리 센터** > 에서는**PSTN 분 풀이****보고** > 됩니다.
    
> [!NOTE]
> 사용 중인 Microsoft 365 또는 Office 365 구독에 따라 여기에 표시 된 것과 동일한 모든 정보가 표시 되지 않을 수 있습니다. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>비즈니스용 Skype PSTN 거래 시간 은행 보고서 해석

표시 되는 각 열을 확인 하 여 사용자의 비즈니스용 Skype 시간 풀에 대 한 보기를 가져올 수 있습니다.
  
보고서의 모양은 다음과 같습니다.
  
## 

![비즈니스용 Skype PSTN 분 풀 보고서](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![번호 1](../images/sfbcallout1.png)<br/>이 표에는 라이선스 (기능) 및 사용 위치 별로 분 단위를 분류 하 여 보여 줍니다. 
*    **접근 권한** 값은 통화에 사용 되는 라이선스/서비스 계획입니다. 이 보고서에 표시 될 수 있는 라이선스/서비스 계획은 다음과 같습니다.
     * MCOPSTN1-국내 통화 요금제 (3000-분 미국/1200-분) EU 요금제
     * MCOPSTN2-국내 & 국제 통화 요금제 (3000-1 ~ 미국/캐나다/PR, 1200-분 유럽어 국가) 및 국제 (600-분)이 표시 됩니다. 월 또는 국제 cap에 도달할 때마다 분 대 일이 도달 합니다. 
     * MCOPSTN5-국내 통화 요금제 (120-분 통화 요금제)
     * MCOPSTN6-국내 통화 요금제 (240-분 통화 요금제)
     * MCOMEETADD 오디오 회의
*    **기능 설명은** 통화에 사용 되는 라이선스 종류에 대 한 설명입니다.
*    **국가 분 풀** 은 분 단위를 공유 하는 사용자의 라이선스 사용 위치입니다. 
*    **사용 된 분** 은 매달 사용 되는 시간 (분)입니다.
*    **총 통화** 시간은 해당 월에 사용할 수 있는 총 통화 수입니다. 
*    **사용 된 백분율** 은 해당 월에 사용 되는 분의 백분율입니다. 
***
![번호 2](../images/sfbcallout2.png)<br/>특정 열을 기준으로 그룹화 하려면 열을 클릭 하 여 하나 이상의 열에 있는 모든 데이터를 그룹화 하는 보기를 만들려는 경우 **열 머리글을 여기로 끌어** 놓습니다. 
***
![번호 3](../images/sfbcallout3.png)<br/>**Excel로 내보내기** 단추를 클릭 하거나 탭 하 여 보고서 데이터를 excel .csv 파일로 내보낼 수도 있습니다. <br/><br/> 이렇게 하면 모든 사용자의 데이터가 내보내며 추가 분석을 위해 간단한 정렬 및 필터링이 가능 합니다. 2000 명 미만의 사용자가 있는 경우 보고서 자체의 표 내에서 정렬 및 필터링이 가능 합니다. 2000 명 이상의 사용자가 있는 경우 필터링 및 정렬 하려면 데이터를 내보내야 합니다.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>다른 비즈니스용 Skype 보고서를 보 시겠습니까?

- [비즈니스용 Skype 활동 보고서](activity-report.md) 사용자가 피어 투 피어를 사용 하는 시간과 회의 세션에서 참여 한 시간을 확인할 수 있습니다.
    
- [비즈니스용 Skype 장치 사용 현황 보고서](device-usage-report.md) 비즈니스용 Skype 앱이 설치 되어 있고 메신저 및 모임에 사용 되 고 있는 Windows 기반 운영 체제와 모바일 장치를 포함 하는 장치를 볼 수 있습니다.
    
- [비즈니스용 Skype 컨퍼런스 이끌이 활동 보고서](conference-organizer-activity-report.md) 사용자가 메신저 대화, 오디오/비디오, 응용 프로그램 공유, 웹, 다이얼 아웃, 타사, 제 3 자, 전화 걸기-Microsoft를 사용 하는 회의를 구성 하는 시간을 확인할 수 있습니다.
    
- [비즈니스용 Skype 컨퍼런스 참가자 활동 보고서](conference-participant-activity-report.md) 참가 하 고 있는 메신저, 오디오/비디오, 응용 프로그램 공유, 웹 및 전화 접속 오디오 회의가 얼마나 많은 지 확인할 수 있습니다.
    
- [비즈니스용 Skype 피어 투 피어 활동 보고서](peer-to-peer-activity-report.md) 사용자 들이 메신저 대화, 오디오/비디오, 응용 프로그램 공유, 파일 전송 중 어느 것을 사용 하 고 있는지 확인할 수 있습니다.
    
- [비즈니스용 Skype 사용자 차단 보고서](users-blocked-report.md) 조직의 사용자에 게 PSTN 통화를 차단 하는 것을 볼 수 있습니다.

- [비즈니스용 Skype 세션 정보 보고서](session-details-report.md) 개인 사용자의 통화 환경에 대 한 세부 정보를 확인할 수 있습니다.
    
## <a name="related-topics"></a>관련 항목
[관리 센터의 활동 보고서](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
