---
title: 비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 지역 링크를 만들거나 수정 합니다.
ms.openlocfilehash: 2b2eb99fa59125c93d97b902b6fbaad122ffdcdf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233693"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기
 
비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 지역 링크를 만들거나 수정 합니다. 
  
네트워크 내의 영역은 실제 WAN 연결을 통해 연결 됩니다. 네트워크 지역 링크는 CAC (호출 허용 제어)에 대해 구성 된 두 지역 간에 링크를 만들고 이러한 지역 간의 오디오 및 비디오 트래픽에 대 한 대역폭 제한을 설정 합니다.
  
이 예제 토폴로지에는 북미와 APAC 지역 간의 링크와 EMEA와 APAC 지역 간의 링크가 있습니다. 이러한 지역 링크는 지역 링크 대역폭 정보 표에 설명 된 것 처럼 WAN 대역폭에 의해 제한 됩니다 [예: 비즈니스용 Skype 서버에서 통화 허용 제어에 대 한 요구 사항 수집](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 지역 링크를 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 새-Csnetworkregion 링크 cmdlet을 실행 하 여 지역 링크를 만들고 적절 한 대역폭 정책 프로필을 적용 합니다. 예를 들어 다음을 실행합니다.
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역 링크를 만들려면

1. 비즈니스용 Skype Server 제어판을 엽니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.
    
3. **지역 링크** 탐색 단추를 클릭 합니다.
    
4. **새로 만들기**를 클릭 합니다.
    
5. **새 지역 링크** 페이지에서 **이름을** 클릭 한 다음 네트워크 지역 링크의 이름을 입력 합니다.
    
6. **네트워크 지역 #1**를 클릭 한 다음 목록에서 네트워크 지역 #2 연결할 네트워크 지역을 클릭 합니다.
    
7. **네트워크 지역 #2**클릭 한 다음 목록에서 네트워크 지역 #1 연결할 네트워크 지역을 클릭 합니다.
    
8. 필요에 따라 **대역폭 정책을**클릭 한 다음 네트워크 지역 링크에 적용 하려는 대역폭 정책 프로필을 선택 합니다.
    
    > [!NOTE]
    > 네트워크 지역 링크에 대역폭이 제한 되어 있고 CAC를 사용 하 여 해당 링크의 미디어 트래픽을 제어 하려는 경우에만 대역폭 정책을 적용 합니다. 
  
9. **커밋**을 클릭합니다.
    
10. 토폴로지에 대 한 네트워크 지역 링크 만들기를 마치려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 9 단계를 반복 합니다.
    
## <a name="see-also"></a>참고 항목

[새-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[-Csnetwork국가 링크 제거](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
