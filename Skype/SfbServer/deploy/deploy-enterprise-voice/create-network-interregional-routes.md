---
title: 2016년 8월에 네트워크 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 2016년 6월 1일부로 전화 Enterprise Voice 사용하는 네트워크 비즈니스용 Skype 서버.
---

# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>2016년 8월에 네트워크 비즈니스용 Skype 서버
 
2016년 6월 1일부로 전화 Enterprise Voice 사용하는 네트워크 비즈니스용 Skype 서버. 
  
네트워크 지역 간 경로는 네트워크 지역 쌍 간의 경로를 정의합니다. 통화 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 간 경로가 필요합니다. 이러한 경로가 있으면 배포 내의 모든 네트워크 지역이 다른 모든 지역에 액세스할 수 있습니다.
  
지역 링크는 지역 간의 연결에 대한 대역폭 제한을 설정하는 반면 지역 간 경로는 연결이 한 지역에서 다른 지역으로 트래버스할 연결된 경로를 결정합니다.
  
토폴로지 예제에서 네트워크 지역 간 경로는 북미/EMEA, EMEA/APAC 및 북미/APAC의 세 지역 쌍 각각에 대해 정의되어야 합니다. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 네트워크 비즈니스용 Skype 서버 경로를 만들 수 있습니다.

1. 비즈니스용 Skype 서버 시작 **: 시작,** 모든 **프로그램, 비즈니스용 Skype** **2015** 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다**.
    
2. **New-CsNetworkInterRegionRoute** cmdlet을 사용하여 필요한 경로를 정의합니다. 예를 들어 다음을 실행합니다.
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 북미/APAC 네트워크 지역 간 경로에는 두 개의 네트워크 지역 링크가 필요하기 때문에 지역 간 직접 네트워크 지역 링크가 없습니다. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 네트워크 비즈니스용 Skype 서버 경로를 만들 수 있습니다.

1. 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.
    
3. **지역 경로** 탐색 단추를 클릭합니다.
    
4. **새로 만들기** 를 클릭합니다.
    
5. 새 **지역 경로 페이지에서** 이름을 클릭한 다음  네트워크 지역 간 경로의 이름을 입력합니다.
    
6. **네트워크 지역 #1** 을 클릭하고 목록에서 네트워크 지역 #2로 라우팅할 네트워크 지역을 클릭합니다.
    
7. **네트워크 지역 #2** 를 클릭하고 목록에서 네트워크 지역 #1로 라우팅할 네트워크 지역을 클릭합니다.
    
8. 네트워크 **지역** 링크 필드  옆에 있는 추가를 클릭한 다음 네트워크 지역 간 경로에 사용할 네트워크 지역 링크를 추가합니다.
    
    > [!NOTE]
    > 두 네트워크 지역에 대한 경로를 만드는데 해당 지역 사이에 직접 네트워크 지역 링크가 없는 경우, 경로를 완료하려면 필요한 모든 링크를 추가해야 합니다. 예를 들어 북미/APAC 네트워크 지역 간 경로에는 두 개의 네트워크 지역 링크가 필요하기 때문에 지역 간 직접 네트워크 지역 링크가 없습니다. 
  
9. **커밋** 을 클릭합니다.
    
10. 토폴로지의 네트워크Regional 경로 만들기를 완료하려면 다른 네트워크 간 경로에 대한 설정을 사용하여 4-9단계를 반복합니다.
    
## <a name="see-also"></a>참고 항목

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)