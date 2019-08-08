---
title: 비즈니스용 Skype 서버에서 네트워크 상호 지역 경로 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 해외 경로를 만들거나 수정 합니다.
ms.openlocfilehash: 6bf455236dc825023cc3c8ce94ee329a464fdde4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233727"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 상호 지역 경로 만들기
 
비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 해외 경로를 만들거나 수정 합니다. 
  
네트워크 상호 지역 경로는 네트워크 지역 쌍 간의 경로를 정의 합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 상호 지역 경로가 필요 합니다. 이렇게 하면 배포 내의 모든 네트워크 영역이 다른 모든 지역에 액세스할 수 있습니다.
  
지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하는 반면, 지역 경로에는 연결이 한 영역에서 다른 지역으로 이동할 연결 경로가 결정 됩니다.
  
예제 토폴로지에서는 네트워크 간 국가별 경로가 세 가지 지역 쌍 (북미/EMEA, EMEA/APAC, 북미/APAC) 각각에 대해 정의 되어야 합니다. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 간 지역 경로를 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. **새-Csnetworkinter지역 경로** cmdlet을 실행 하 여 필요한 경로를 정의 합니다. 예를 들어 다음을 실행합니다.
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 북미/APAC 네트워크 상호 지역 경로에는 두 개의 네트워크 지역 연결이 없기 때문에 연결을 설정 해야 합니다. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 간 지역별 경로를 만들려면

1. 비즈니스용 Skype Server 제어판을 엽니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.
    
3. **지역 경로** 탐색 단추를 클릭 합니다.
    
4. **새로 만들기**를 클릭 합니다.
    
5. **새 영역 경로** 페이지에서 **이름을** 클릭 한 다음 네트워크 간 경로 이름을 입력 합니다.
    
6. **네트워크 지역 #1**를 클릭 한 다음 목록에서 네트워크 지역으로 라우팅하도록 할 네트워크 영역을 클릭 #2 합니다.
    
7. **네트워크 지역 #2**를 클릭 한 다음 목록에서 네트워크 지역으로 라우팅하도록 할 네트워크 영역을 클릭 #1 합니다.
    
8. **네트워크 지역 링크** 필드 옆에 있는 **추가** 를 클릭 한 다음 네트워크 간 경로에 사용 될 네트워크 지역 링크를 추가 합니다.
    
    > [!NOTE]
    > 두 개의 네트워크 지역에 대해 직접 네트워크 지역 링크가 없는 경우 경로를 만들려면 경로를 완료 하는 데 필요한 모든 링크를 추가 해야 합니다. 예를 들어 북미/APAC 네트워크 상호 지역 경로에는 두 개의 네트워크 지역 연결이 없기 때문에 연결을 설정 해야 합니다. 
  
9. **커밋**을 클릭합니다.
    
10. 토폴로지에 대 한 네트워크 간 지역별 경로 만들기를 완료 하려면 다른 네트워크 상호 지역 경로에 대 한 설정을 사용 하 여 4 ~ 9 단계를 반복 합니다.
    
## <a name="see-also"></a>참고 항목

[새-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[제거-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
