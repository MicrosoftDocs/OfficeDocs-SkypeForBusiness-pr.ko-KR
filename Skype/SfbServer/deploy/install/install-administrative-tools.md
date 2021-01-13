---
title: 비즈니스용 Skype 서버에 관리 도구 설치
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치하는 방법을 설명하는 문서입니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812108"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>비즈니스용 Skype 서버에 관리 도구 설치
 
**요약:** 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치하는 방법을 배워야 합니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.
  
관리 도구에는 토폴로지 작성기 및 제어판이 포함됩니다. 관리 도구는 토폴로지의 하나 이상의 서버에 설치하거나 비즈니스용 Skype 서버에 대해 지원되는 Windows OS 버전을 실행하는 64비트 관리 Workstation에 설치해야 합니다. 1~5단계는 순서에 따라 할 수 있습니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로, 6, 7, 8단계를 순서대로 수행해야 합니다. 관리 도구를 설치하는 단계는 8단계 중 3단계입니다.
  
![개요 다이어그램](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>비즈니스용 Skype 서버 관리 도구 설치

비즈니스용 Skype 서버의 설치 미디어는 유연한 환경을 제공합니다. 이 Setup.exe 설치되는 도구는 비즈니스용 Skype 서버 배포 마법사와 비즈니스용 Skype 서버 관리 셸뿐입니다. 핵심 구성 요소라고 하는 이러한 두 도구를 사용하여 설치 프로세스를 계속할 수 있지만 전체 비즈니스용 Skype 서버 환경에 대한 기본 기능은 제공하지 않습니다. 핵심 구성 요소를 설치하면 배포 마법사가 자동으로 시작됩니다. 배포 마법사의 제목이 "관리 도구 **설치"라는** 섹션에서는 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype 서버 제어판을 설치합니다.
  
> [!IMPORTANT]
> 모든 비즈니스용 Skype 서버 환경에는 관리 도구가 설치된 서버가 하나 이상 있어야 합니다. 
  
관리 도구 설치에 대한 **비디오 단계를 시청하세요.**
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>배포 마법사에서 비즈니스용 Skype 서버 관리 도구 설치

1. 비즈니스용 Skype 서버 설치 미디어를 삽입합니다. 설치가 자동으로 시작되지 않는 경우 설치를 두 번 **클릭합니다.**
    
2. 설치 미디어를 실행하려면 Microsoft Visual C++가 필요합니다. 설치할지 묻는 대화 상자가 표시됩니다. **예** 를 클릭합니다.
    
3. 비즈니스용 Skype 서버의 새로운 기능인 스마트 설치를 사용하여 인터넷에 연결하여 설치 프로세스 중에 업데이트를 확인할 수 있습니다. 이렇게 하면 설치 시 제품에 대한 최신 업데이트가 적용된 것이 더 나은 환경을 제공합니다. **설치** 를 클릭하여 설치를 시작합니다.
    
4. 사용권 계약을 신중하게 검토하고, 동의하는 경우 사용권 계약 조건에 동의하는지 선택하고 **확인을** **클릭합니다.**
    
5. 비즈니스용 Skype 서버 핵심 구성 요소가 서버에 설치됩니다. 
    
    핵심 구성 요소는 그림과 같이 다음으로 구성됩니다.
    
    ![앱의 핵심 구성 요소 화면.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **비즈니스용 Skype 서버 배포 마법사** 비즈니스용 Skype 서버의 다양한 구성 요소를 설치하기 위한 시작 패드를 제공하는 배포 프로그램입니다.
    
   - **비즈니스용 Skype 서버 관리 셸** 비즈니스용 Skype 서버를 관리하기 위한 미리 구성한 PowerShell 프로그램입니다.
    
     핵심 구성 요소 설치가 완료되면 그림과 같이 비즈니스용 Skype 서버 배포 마법사가 자동으로 시작됩니다. 
    
     ![비즈니스용 Skype 서버 배포 마법사](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 핵심 구성 요소 외에도 해당 환경의 하나 이상의 서버에 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype 서버 제어판을 설치해야 합니다. 배포 **마법사에서** 관리 도구 설치를 클릭합니다.
    
7. **다음** 을 클릭하여 설치를 시작합니다.
    
8. 설치가 완료되면 **마쳤습니다.** 이제 그림과 같이 관리 도구가 서버에 추가됩니다.
    
    ![비즈니스용 Skype 서버 관리 도구](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **비즈니스용 Skype 서버 토폴로지 작성기** 토폴로지 작성, 배포 및 관리에 사용되는 프로그램
    
   - **비즈니스용 Skype 서버 제어판** 설치를 관리하는 데 사용되는 프로그램입니다.
    

