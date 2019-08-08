---
title: 비즈니스용 Skype Server에 대 한 필수 구성 요소 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '요약: 비즈니스용 Skype 서버를 설치 하기 전에 구성 해야 하는 서버 및 서버 역할에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: 2fbf90a1ee6f517cad2c716e6a50dd814352993e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240909"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>비즈니스용 Skype Server에 대 한 필수 구성 요소 설치
 
**요약:** 비즈니스용 Skype Server를 설치 하기 전에 구성 해야 하는 서버 및 서버 역할에 대해 알아봅니다. [Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요.
  
필수 구성 요소 설치는 토폴로지의 각 서버에 필요한 역할 및 기능을 설치 하 여 Windows Server를 설정 하는 것으로 구성 됩니다. 요구 사항은 서버가 토폴로지에서 처리 하는 역할을 기준으로 합니다. 1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다. 그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다. 필수 구성 요소를 설치 하는 과정은 1 ~ 8 단계입니다.
  
![개요 다이어그램-필수 구성 요소를 설치 합니다.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server 설정

비즈니스용 Skype 서버를 설치 하려면 Windows Server 운영 체제와 여러 필수 구성 요소가 필요 합니다. 필수 구성 요소 계획에 대 한 자세한 내용은 [비즈니스용 Skype server의 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md)을 참조 하세요. 
  
> [!TIP]
> 이 절차에서는 Windows Server 2012 R2를 사용 합니다. 다른 버전의 Windows Server를 사용 하는 경우 절차가 약간 다를 수 있습니다. 
  
> [!IMPORTANT]
> 시작 하기 전에 windows Update를 사용 하 여 Windows Server가 최신 상태 인지 확인 합니다. 
  
![Windows Server를 최신 버전으로 업데이트 합니다.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
**설치 필수 구성 요소**에 대 한 비디오 단계를 시청 하세요.
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>프런트 엔드 서버에 필요한 역할 및 기능 설치

서버 관리자를 사용 하 여 필요한 역할 및 기능을 설치할 수 있습니다. 
    
1. [비즈니스용 Skype 서버에 대 한 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md)에 나열 된 필수 소프트웨어 기능을 설치 합니다. 필수 소프트웨어는 비즈니스용 Skype Server를 실행 하는 서버에 있어야 합니다.
    
    > [!CAUTION]
    > Windows Server 2012 R2는 기본적으로 필요한 기능에 대 한 원본 파일을 모두 설치 하지는 않습니다. 서버가 인터넷에 연결 되어 있지 않은 경우에는 Windows Server 2012 R2 미디어를 삽입 하 고 **대체 원본 경로 지정** 을 선택 하 여 필요한 기능을 설치 해야 합니다. 원본 파일은 \sxs 디렉터리에 있습니다. 예를 들어 Windows Server 2012 R2 미디어가 D 드라이브에 있는 경우 경로를으로 `d:\sources\sxs`설정 합니다. Windows 업데이트의 최신 업데이트를 사용 하는 것이 중요 합니다. 인터넷에 연결 되어 있지 않은 경우에는 필수 업데이트에 모든 필수 업데이트와 함께 수동으로 설치 해야 합니다. 
  
1. 대화 상자에 설치가 완료 되었다는 내용이 표시 되 면 서버를 다시 부팅 하 여 프로세스를 완료 해야 합니다.
    
1. **Windows Update** 를 다시 실행 하 여 설치 된 역할 및 서비스에 대 한 업데이트가 있는지 확인 합니다.
    
1. 이 서버에서 비즈니스용 Skype Server 제어판을 사용 하는 경우에는 Silverlight도 설치 해야 합니다. Silverlight를 설치 하려면 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)를 참조 하세요.


> [!IMPORTANT]
> 프런트 엔드 서버 이외의 역할을 수행 하는 서버에 대 한 필수 구성 요소 (예: 디렉터, 영구 채팅 또는 가장자리의 역할)에는 고유한 필수 구성 요소가 있습니다. 각 서버 유형에 필요한 정확한 필수 구성 요소에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md)을 참조 하세요. 
  

