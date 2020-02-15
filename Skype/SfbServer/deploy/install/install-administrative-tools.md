---
title: 비즈니스용 Skype 서버에 관리 도구 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '요약: 비즈니스용 Skype 서버를 설치 하는 데 필요한 관리 도구를 설치 하는 방법을 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018269"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>비즈니스용 Skype 서버에 관리 도구 설치
 
**요약:** 비즈니스용 Skype 서버를 설치 하는 데 필요한 관리 도구를 설치 하는 방법을 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요. [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
관리 도구에는 토폴로지 작성기와 제어판이 포함 됩니다. 관리 도구는 토폴로지의 하나 이상의 서버에 설치 해야 하며, Windows OS 버전을 실행 하는 64 비트 관리 워크스테이션은 비즈니스용 Skype 서버에서 지원 됩니다. 순서에 관계 없이 1 ~ 5 단계를 수행할 수 있습니다. 그러나 다이어그램에 나와 있는 것 처럼, 1 ~ 5 단계를 순서 대로 수행 해야 합니다. 관리 도구를 설치 하는 과정은 3 단계입니다.
  
![개요 다이어그램](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>비즈니스용 Skype 서버 관리 도구 설치

비즈니스용 Skype 서버용 설치 미디어는 유연한 환경을 제공 합니다. Setup.exe를 처음 실행할 때는 비즈니스용 Skype 서버 배포 마법사와 비즈니스용 Skype 서버 관리 셸이 설치 된 도구 뿐입니다. 핵심 구성 요소 라고 하는 이러한 두 도구를 사용 하면 설치 프로세스를 계속할 수 있지만 전체 비즈니스용 Skype 서버 환경에 대 한 기본 기능은 제공 되지 않습니다. 핵심 구성 요소를 설치한 후에는 배포 마법사가 자동으로 시작 됩니다. **관리 도구 설치** 라는 배포 마법사 섹션에서는 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype 서버 제어판을 설치 합니다.
  
> [!IMPORTANT]
> 모든 비즈니스용 Skype 서버 환경에는 관리 도구가 설치 된 서버가 하나 이상 있어야 합니다. 
  
**관리 도구 설치**에 대 한 비디오 단계를 시청 하세요.
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>배포 마법사에서 비즈니스용 Skype 서버 관리 도구 설치

1. 비즈니스용 Skype 서버 설치 미디어를 삽입 합니다. 설치 프로그램이 자동으로 시작 되지 않으면 **설치 프로그램**을 두 번 클릭 합니다.
    
2. 설치 미디어를 사용 하려면 Microsoft Visual a + c를 실행 해야 합니다. 설치할 것인지 묻는 대화 상자가 팝업 됩니다. **예**를 클릭합니다.
    
3. 비즈니스용 Skype 서버의 새로운 기능인 Smart Setup을 사용 하 여 설치 프로세스 중에 인터넷에 연결 하 여 업데이트를 확인할 수 있습니다. 이를 통해 설치 시 제품에 대 한 최신 업데이트가 있는지 확인 하는 것이 더 좋습니다. **설치**를 클릭하여 설치를 시작합니다.
    
4. 사용권 계약을 신중 하 게 검토 하 고, 동의 하는 경우 **동의**함을 선택 하 고 **확인**을 클릭 합니다.
    
5. 비즈니스용 Skype 서버 핵심 구성 요소가 서버에 설치 됩니다. 
    
    핵심 구성 요소는 그림과 같이 다음으로 구성 됩니다.
    
    ![앱 화면에 있는 핵심 구성 요소입니다.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **비즈니스용 Skype 서버 배포 마법사** 비즈니스용 Skype 서버의 다양 한 구성 요소를 설치 하기 위한 시작 패드를 제공 하는 배포 프로그램입니다.
    
   - **비즈니스용 Skype 서버 관리 셸** 비즈니스용 Skype 서버를 관리 하는 데 사용할 수 있는 미리 구성 된 PowerShell 프로그램입니다.
    
     핵심 구성 요소 설치가 완료 되 면 그림에 표시 된 것 처럼 비즈니스용 Skype 서버 배포 마법사가 자동으로 시작 됩니다. 
    
     ![비즈니스용 Skype 서버 배포 마법사](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 핵심 구성 요소 외에, 해당 환경의 하나 이상의 서버에 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype 서버 제어판도 설치 해야 합니다. 배포 마법사에서 **관리 도구 설치** 를 클릭 합니다.
    
7. **다음**을 클릭하여 설치를 시작합니다.
    
8. 설치가 완료 되 면 **마침을**클릭 합니다. 이제 그림과 같이 관리 도구가 서버에 추가 됩니다.
    
    ![비즈니스용 Skype 서버 관리 도구](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **비즈니스용 Skype 서버 토폴로지 작성기** 토폴로지를 작성, 배포 및 관리 하는 데 사용 되는 프로그램입니다.
    
   - **비즈니스용 Skype 서버 제어판** 설치를 관리 하는 데 사용 되는 프로그램입니다.
    

