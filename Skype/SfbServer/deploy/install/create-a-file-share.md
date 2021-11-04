---
title: 파일 공유를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '요약: Windows 설치의 일부로 Windows Server 파일 공유를 만드는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: c14d7a765a4b55e1fe909f33f4e038062427872b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751177"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>파일 공유를 비즈니스용 Skype 서버
 
**요약:** Windows 설치의 일부로 Windows 서버 파일 공유를 만드는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.
  
비즈니스용 Skype 서버 토폴로지 전체의 컴퓨터가 파일을 교환할 수 있도록 파일 공유가 필요합니다. 파일 공유를 만드는 것은 설치 프로세스에서 8단계 중 2단계 중 비즈니스용 Skype 서버. 1~5단계는 순서에 따라 수행하면 됩니다. 그러나 6, 7, 8단계를 순서대로 수행하고 다이어그램에 설명된대로 1~5단계를 수행해야 합니다. 파일 공유에 대한 계획에 대한 자세한 내용은 [2019년](../../../SfBServer2019/plan/system-requirements.md)비즈니스용 Skype 서버 또는 서버 요구 사항에 대한 환경 비즈니스용 Skype 서버 참조하세요. [](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
  
![개요 다이어그램.](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>기본 파일 공유 만들기

이 섹션에서는 기본 서버 파일 공유를 만드는 Windows 설명합니다. 기본 Windows 서버 파일 공유가 지원되는 비즈니스용 Skype 서버. 그러나 고가용성을 명시적으로 제공하지는 않습니다. 고가용성 환경의 경우 DFS(분산 파일 시스템) 파일 공유를 권장합니다. 고가용성 파일 공유 및 DFS에 대한 자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> Windows Server 2012 R2는 Storage Server 플랫폼을 사용하여 SAN(Storage Area Network) 같은 파일 공유 솔루션을 제공하는 데 큰 Windows 있습니다. 기존 SAN 기반 어플라이언스와 비교할 때 Windows Server 2012 R2 저장소 솔루션은 성능에 미치는 영향을 최소화하면서 비용을 절반으로 절감할 수 있습니다. Windows Server 2012 R2의 파일 공유 옵션에 대한 자세한 내용은 [R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)Windows Server 2012 다운로드 가능한 Storage. 
  
파일 공유 만들기를 위한 **비디오 단계를 시청하세요.**
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>기본 파일 공유 만들기

1. 파일 공유를 호스팅할 컴퓨터에 로그온합니다.
    
2. 공유할 폴더를 마우스 오른쪽 단추로 클릭하고 속성을 **선택합니다.**
    
3. 공유 **탭을** 선택하고 고급 **공유를 클릭합니다.**
    
4. 이 **폴더 공유를 클릭합니다.**
    
5. **권한** 을 클릭합니다.
    
6. 파일 공유를 호스팅하는 서버의 로컬 **Administrators** 그룹을 추가하고 허용: 모든 **권한,** 변경 및 읽기 권한을 부여한 다음 확인을 **클릭합니다.**
    
7. **확인을** 다시 클릭하고 네트워크 경로를 확인합니다.
    
8. **완료를** 클릭하여 마법사를 닫습니다.
    
     ![폴더를 공유하기 위한 공유 탭](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>파일 저장소가 DFS 공유에 호스팅된 경우 다음 경고가 수신됩니다.

경고: " "에 대한 공유 권한에 액세스할 수 \\ <domain> \<share> 없습니다.

>이 설정은 파일 서버의 관리자가 아니거나 DFS(분산 파일 시스템) 공유인 경우 예상됩니다. 공유 권한이 이미 구성되어 있는 경우 이 경고는 무시해도 됩니다. 새 공유인 경우 공유 권한을 수동으로 구성하는 데 대한 자세한 내용은 설명서를 참조하십시오.

>DFS 공유에 대한 공유 권한에 액세스할 수 비즈니스용 Skype 서버 공유에 대해 그룹을 명시적으로 설정할 수 없습니다. 비즈니스용 Skype 서버 구성 요소가 적절한 사용 권한을 사용하여 파일 공유에 액세스할 수 있도록 모든 권한이 있는 로컬 관리자 외에 읽기 및 변경 수준 공유 권한으로 다음 RTC 그룹을 추가해야 합니다.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
