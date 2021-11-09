---
title: 설치를 위한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: '요약: 설치하기 전에 구성해야 하는 서버 및 서버 역할에 대해 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: 97b348cedef3fe460a26c52672fc856a5eeda98e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849411"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>설치를 위한 비즈니스용 Skype 서버
 
**요약:** 설치하기 전에 구성해야 하는 서버 및 서버 역할에 대해 비즈니스용 Skype 서버. Microsoft 평가판 비즈니스용 Skype 서버 [평가판을 다운로드합니다.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
필수 구성 Windows 설치는 토폴로지의 각 서버에 필요한 역할 및 기능을 설치하여 Windows Server를 설정하는 것으로 구성됩니다. 요구 사항은 서버가 토폴로지에서 이행하는 역할을 기반으로 합니다. 1~5단계는 순서에 따라 수행하면 됩니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로 6, 7, 8단계를 순서대로 수행해야 합니다. 선행 단계 설치는 8단계 중 1단계입니다.
  
![개요 다이어그램 - 설치 선행 요소.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>설치 Windows 서버

비즈니스용 Skype 서버 설치하려면 Windows Server 운영 체제 및 여러 가지 선행 요구가 필요합니다. 선행 조건 계획에 대한 자세한 내용은 에 대한 서버 요구 [비즈니스용 Skype 서버.](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> 이 절차에서는 R2 Windows Server 2012 사용합니다. 다른 버전의 Windows Server를 사용하는 경우 절차가 약간 다를 수 있습니다. 
  
> [!IMPORTANT]
> 시작하기 전에 Windows 업데이트를 사용하여 Windows 합니다. 
  
![Windows 최신 서버.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
설치 선행 단계에 대한 비디오 **단계를 시청하세요.**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>프런트 엔드 서버에 필요한 역할 및 기능 설치

서버 관리자를 사용하여 필요한 역할 및 기능을 설치할 수 있습니다. 
    
1. 에 대한 서버 요구 사항에 나열된 소프트웨어의 선행 [비즈니스용 Skype 서버.](../../../SfBServer2019/plan/system-requirements.md) 필요한 소프트웨어는 해당 소프트웨어가 실행되는 서버에 있어야 비즈니스용 Skype 서버.
    
    > [!CAUTION]
    > Windows Server 2012 R2에서는 기본적으로 필요한 기능에 대한 원본 파일을 모두 설치하지 않습니다. 서버가 인터넷에 연결되어 있지 않으면 Windows Server 2012 R2 미디어를 삽입하고 대체  원본 경로 지정을 선택하여 필요한 기능을 설치해야 합니다. 원본 파일은 sources\sxs 디렉터리에 있습니다. 예를 들어 Windows Server 2012 R2 미디어가 D 드라이브에 있는 경우 경로를 로 설정하게 `d:\sources\sxs` 됩니다. 업데이트의 최신 업데이트가 Windows 중요합니다. 인터넷에 연결되어 있지 않은 경우 모든 관련 업데이트와 필수 업데이트를 수동으로 설치해야 합니다. 
  
1. 대화 상자에 설치가 완료된 것으로 표시되면 서버를 다시 시작하여 프로세스를 완료해야 합니다.
    
1. 업데이트 **Windows** 다시 실행하여 설치된 역할 및 서비스에 대한 업데이트가 있는지 확인합니다.
    
1. 이 서버에서 비즈니스용 Skype 서버 제어판을 사용하려면 Silverlight도 설치해야 합니다. Silverlight를 설치하려면 [Microsoft Silverlight를 참조합니다.](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> 프런트 엔드 서버가 아니라 역할을 수행하는 서버(예: Director, 영구 채팅 또는 Edge의 역할)에 대한 선행 준비에는 자체적인 선행이 있습니다. 각 서버 유형에 필요한 정확한 필수 조건에 대한 자세한 내용은 서버 요구 사항을 [비즈니스용 Skype 서버.](../../../SfBServer2019/plan/system-requirements.md) 
  

