---
title: 비즈니스용 Skype 서버의 설치 선행 준비
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '요약: 비즈니스용 Skype 서버를 설치하기 전에 구성해야 하는 서버 및 서버 역할에 대해 자세히 알아보습니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801718"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>비즈니스용 Skype 서버의 설치 선행 준비
 
**요약:** 비즈니스용 Skype 서버를 설치하기 전에 구성해야 하는 서버 및 서버 역할에 대해 자세히 알아보습니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 [평가판을 다운로드합니다.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
필수 구성표 설치는 토폴로지의 각 서버에 필요한 역할 및 기능을 설치하여 Windows Server를 설정하는 것으로 구성됩니다. 요구 사항은 서버가 토폴로지에서 수행하게 될 역할을 기반으로 합니다. 1~5단계는 순서에 따라 할 수 있습니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로, 6, 7, 8단계를 순서대로 수행해야 합니다. 선행 단계를 설치하는 단계는 8단계 중 1단계입니다.
  
![개요 다이어그램 - 설치 선행 요소.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server 설치

비즈니스용 Skype 서버를 설치하려면 Windows Server 운영 체제와 여러 가지 선행 요구가 필요합니다. 선행 조건 계획에 대한 자세한 내용은 비즈니스용 Skype 서버에 대한 서버 요구 [사항을 참조하세요.](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> 이 절차에서는 Windows Server 2012 R2를 사용합니다. 다른 버전의 Windows Server를 사용하는 경우 절차가 약간 다를 수 있습니다. 
  
> [!IMPORTANT]
> 시작하기 전에 Windows 업데이트를 사용하여 Windows Server를 최신으로 유지해야 합니다. 
  
![Windows Server 최신 버전입니다.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
설치에 대한 비디오 단계를 **시청하세요.**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>프런트 엔드 서버에 필요한 역할 및 기능 설치

서버 관리자를 사용하여 필요한 역할 및 기능을 설치할 수 있습니다. 
    
1. 비즈니스용 Skype 서버의 서버 요구 사항에 나열된 선행 [소프트웨어 기능을 설치합니다.](../../../SfBServer2019/plan/system-requirements.md) 필요한 소프트웨어는 비즈니스용 Skype 서버를 실행할 서버에 있어야 합니다.
    
    > [!CAUTION]
    > Windows Server 2012 R2에서는 기본적으로 필요한 기능에 대한 원본 파일을 모두 설치하지 않습니다. 서버가 인터넷에 연결되어 있지 않은 경우 Windows Server 2012 R2 미디어를 삽입하고  대체 원본 경로 지정을 선택하여 필요한 기능을 설치해야 합니다. 원본 파일은 sources\sxs 디렉터리에 있습니다. 예를 들어 Windows Server 2012 R2 미디어가 D 드라이브에 있는 경우 경로를 으로 설정해야 `d:\sources\sxs` 합니다. Windows 업데이트의 최신 업데이트가 중요합니다. 인터넷에 연결되어 있지 않은 경우 필요한 업데이트에 대한 모든 필수 구성뿐만 아니라 모든 관련 업데이트를 수동으로 설치해야 합니다. 
  
1. 설치가 완료된 것으로 대화 상자에 표시되면 프로세스를 완료하려면 서버를 다시 시작해야 합니다.
    
1. **Windows 업데이트를 다시** 실행하여 설치된 역할 및 서비스에 대한 업데이트가 없는지 확인합니다.
    
1. 이 서버에서 비즈니스용 Skype 서버 제어판을 사용하려면 Silverlight도 설치해야 합니다. Silverlight를 설치하려면 [Microsoft Silverlight를 참조합니다.](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> 프런트 엔드 서버가 아니라 역할을 수행하는 서버(예: Director, 영구 채팅 또는 Edge)의 선행 준비에는 자체적인 선행이 있습니다. 각 서버 유형에 필요한 정확한 필수 조건에 대한 자세한 내용은 비즈니스용 Skype 서버에 대한 서버 요구 [사항을 참조하세요.](../../../SfBServer2019/plan/system-requirements.md) 
  

