---
title: 비즈니스용 Skype 서버 위한 필수 구성 요소 설치
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '요약: 비즈니스용 Skype 서버 설치하기 전에 구성해야 하는 서버 및 서버 역할에 대해 알아봅니다.'
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860739"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>비즈니스용 Skype 서버 위한 필수 구성 요소 설치
 
**요약:** 비즈니스용 Skype 서버 설치하기 전에 구성해야 하는 서버 및 서버 역할에 대해 알아봅니다.
  
필수 구성 요소 설치는 토폴로지의 각 서버에 필요한 역할 및 기능을 설치하여 Windows Server를 설정하는 것으로 구성됩니다. 요구 사항은 서버가 토폴로지에서 수행할 역할을 기반으로 합니다. 1~5단계는 순서대로 수행할 수 있습니다. 그러나 다이어그램에 설명된 대로 6단계, 7, 8단계를 순서대로, 1~5단계 후에 수행해야 합니다. 필수 구성 요소 설치는 8단계 중 1단계입니다.
  
![개요 다이어그램 - 설치 필수 구성 요소입니다.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server 설정

비즈니스용 Skype 서버 설치하려면 Windows Server 운영 체제와 여러 필수 구성 요소가 필요합니다. 필수 구성 요소 계획에 대한 자세한 내용은 [비즈니스용 Skype 서버 대한 서버 요구 사항을](../../../SfBServer2019/plan/system-requirements.md) 참조하세요. 
  
> [!TIP]
> 이 절차에서는 Windows Server 2012 R2를 사용합니다. 다른 버전의 Windows Server를 사용하는 경우 절차는 약간 다를 수 있습니다. 
  
> [!IMPORTANT]
> 시작하기 전에 Windows 업데이트 사용하여 Windows Server가 최신 상태인지 확인합니다. 
  
![Windows Server를 최신 상태로 유지합니다.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
**설치 필수 구성 요소** 에 대한 비디오 단계를 시청하세요.
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>프런트 엔드 서버에 필요한 역할 및 기능 설치

서버 관리자 사용하여 필요한 역할 및 기능을 설치할 수 있습니다. 
    
1. [비즈니스용 Skype 서버 서버 요구 사항에](../../../SfBServer2019/plan/system-requirements.md) 나열된 필수 구성 요소 소프트웨어 기능을 설치합니다. 필요한 소프트웨어는 비즈니스용 Skype 서버 실행할 서버에 있어야 합니다.
    
    > [!CAUTION]
    > Windows Server 2012 R2는 기본적으로 필요한 기능에 대한 모든 원본 파일을 설치하지 않습니다. 서버가 인터넷에 연결되어 있지 않은 경우 필요한 기능을 설치하려면 Windows Server 2012 R2 미디어를 삽입하고 **대체 원본 경로 지정** 을 선택해야 합니다. 원본 파일은 sources\sxs 디렉터리에 있습니다. 예를 들어 Windows Server 2012 R2 미디어가 드라이브 D에 있는 경우 경로를 `d:\sources\sxs`.로 설정합니다. Windows 업데이트 최신 업데이트를 사용하는 것이 중요합니다. 인터넷에 연결되지 않은 경우 필요한 업데이트에 대한 모든 필수 구성 요소뿐만 아니라 모든 관련 업데이트를 수동으로 설치해야 합니다. 
  
1. 대화 상자에서 설치가 완료되었음을 나타내는 경우 프로세스를 완료하려면 서버를 다시 부팅해야 합니다.
    
1. **Windows 업데이트** 다시 실행하여 설치된 역할 및 서비스에 대한 업데이트가 있는지 확인합니다.
    
1. 이 서버에서 비즈니스용 Skype 서버 제어판 사용하는 경우 Silverlight도 설치해야 합니다. Silverlight를 설치하려면 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)를 참조하세요.


> [!IMPORTANT]
> 디렉터, 영구 채팅 또는 Edge 역할과 같은 프런트 엔드 서버 이외의 역할을 수행하는 서버의 필수 구성 요소에는 고유한 필수 구성 요소가 있습니다. 각 서버 유형에 필요한 정확한 필수 구성 요소에 대한 자세한 내용은 [비즈니스용 Skype 서버 대한 서버 요구 사항을](../../../SfBServer2019/plan/system-requirements.md) 참조하세요. 
  

