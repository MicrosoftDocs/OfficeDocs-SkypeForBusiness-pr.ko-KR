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
description: '요약: 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790176"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>비즈니스용 Skype 서버에 관리 도구 설치
 
**요약:** 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)하세요.
  
관리 도구에는 토폴로지 작성기와 제어판이 포함 됩니다. 관리 도구는 토폴로지의 하나 이상의 서버에 설치 되어 있거나 비즈니스용 Skype Server에 대해 지원 되는 Windows OS 버전을 실행 하는 64 비트 관리 워크스테이션에도 있어야 합니다. 1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다. 그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다. 관리 도구 설치 방법은 8 단계입니다.
  
![개요 다이어그램](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>비즈니스용 Skype 서버 관리 도구 설치

비즈니스용 Skype Server의 설치 미디어는 유연한 환경을 제공 합니다. 처음 setup.exe를 실행할 때는 비즈니스용 Skype 서버 배포 마법사와 비즈니스용 Skype 서버 관리 셸이 설치 되어 있습니다. 핵심 구성 요소 라는 두 도구를 사용 하 여 설치 프로세스를 계속할 수 있지만, 전체 비즈니스용 Skype Server 환경에 대 한 기본 기능을 제공 하지는 않습니다. 핵심 구성 요소를 설치한 후 배포 마법사가 자동으로 실행 됩니다. **관리 도구 설치** 라는 배포 마법사의 섹션에서는 비즈니스용 Skype 서버 토폴로지 작성기와 비즈니스용 Skype 서버 제어판을 설치 합니다.
  
> [!IMPORTANT]
> 모든 Skype for Business Server 환경에는 관리 도구가 설치 된 서버가 하나 이상 있어야 합니다. 
  
**관리 도구 설치**의 비디오 단계를 시청 합니다.
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>배포 마법사에서 비즈니스용 Skype 서버 관리 도구 설치

1. 비즈니스용 Skype 서버 설치 미디어를 삽입 합니다. 설치 프로그램이 자동으로 시작 되지 않으면 **설정을**두 번 클릭 합니다.
    
2. 설치 미디어를 실행 하려면 Microsoft Visual c + +가 필요 합니다. 설치 여부를 묻는 대화 상자가 팝업 됩니다. **예**를 클릭 합니다.
    
3. 비즈니스용 Skype Server의 새로운 기능인 스마트 설정을 사용 하 여 설치 프로세스 중에 인터넷에 연결 하 여 업데이트를 확인할 수 있습니다. 이렇게 하면 설치 시 제품에 대 한 최신 업데이트가 있는지 확인 하 여 더 나은 환경을 제공 합니다. 설치를 **클릭 하 여 설치를 시작** 합니다.
    
4. 사용권 계약을 신중 하 게 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **확인**을 클릭 합니다.
    
5. 비즈니스용 Skype Server Core 구성 요소가 서버에 설치 됩니다. 
    
    핵심 구성 요소는 그림에 표시 된 대로 다음과 같이 구성 됩니다.
    
    ![앱 화면의 핵심 구성 요소.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **비즈니스용 Skype 서버 배포 마법사** 비즈니스용 Skype 서버의 다양 한 구성 요소를 설치 하기 위한 시작 패드를 제공 하는 배포 프로그램입니다.
    
   - **비즈니스용 Skype 서버 관리 셸** 비즈니스용 Skype 서버 관리를 가능 하 게 하는 미리 구성 된 PowerShell 프로그램입니다.
    
     핵심 구성 요소의 설치가 완료 되 면 그림에 표시 된 대로 비즈니스용 Skype 서버 배포 마법사가 자동으로 실행 됩니다. 
    
     ![비즈니스용 Skype 서버 배포 마법사](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 핵심 구성 요소 외에도, 환경에서 하나 이상의 서버에 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype Server 제어판을 설치 해야 합니다. 배포 마법사에서 **관리 도구 설치** 를 클릭 합니다.
    
7. **다음** 을 클릭 하 여 설치를 시작 합니다.
    
8. 설치가 완료 되 면 **마침을**클릭 합니다. 이제 그림과 같이 관리 도구가 서버에 추가 됩니다.
    
    ![비즈니스용 Skype 서버 관리 도구](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **비즈니스용 Skype 서버 토폴로지 작성기** 토폴로지를 빌드, 배포 및 관리 하는 데 사용 되는 프로그램입니다.
    
   - **비즈니스용 Skype Server 제어판** 설치를 관리 하는 데 사용 되는 프로그램입니다.
    

