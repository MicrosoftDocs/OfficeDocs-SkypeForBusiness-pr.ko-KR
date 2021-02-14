---
title: 비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 네트워크 지역 링크를 만들거나 수정합니다.
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822468"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기
 
비즈니스용 Skype 서버에서 통화 Enterprise Voice 제어에 사용되는 네트워크 지역 링크를 만들거나 수정합니다. 
  
네트워크 내의 지역은 실제 WAN 연결을 통해 연결됩니다. 네트워크 지역 링크는 CAC(통화 제어)에 대해 구성된 두 지역 간의 링크를 만들고 이러한 지역 간의 오디오 및 비디오 트래픽에 대한 대역폭 제한을 설정합니다.
  
이 토폴로지 예에는 북미와 APAC 지역 간 링크 및 EMEA와 APAC 지역 간 링크가 포함됩니다. 이러한 각 지역 링크는 예제의 지역 링크 대역폭 정보 표에 설명된 바와 같이 WAN 대역폭에 의해 [제한됩니다.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)비즈니스용 Skype 서버의 통화 제한 제어에 대한 요구 사항 수집
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 지역 링크를 만들 수 있습니다.

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. New-CsNetworkRegionLink cmdlet를 실행하여 지역 링크를 만들고 적합한 대역폭 정책 프로필을 적용합니다. 예를 들어 다음을 실행합니다.
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역 링크를 만들 수 있습니다.

1. 비즈니스용 Skype 서버 제어판을 니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.
    
3. **지역 링크** 탐색 단추를 클릭합니다.
    
4. **새로 만들기** 를 클릭합니다.
    
5. **새 지역 링크** 페이지에서 **이름** 을 클릭하고 네트워크 지역 링크에 대한 이름을 입력합니다.
    
6. **네트워크 지역 #1** 을 클릭하고 목록에서 네트워크 지역 #2에 연결할 네트워크 지역을 클릭합니다.
    
7. **네트워크 지역 #2** 를 클릭하고 목록에서 네트워크 지역 #1에 연결할 네트워크 지역을 클릭합니다.
    
8. (선택 사항) **대역폭 정책** 을 클릭하고 네트워크 지역 링크에 적용할 대역폭 정책 프로필을 선택합니다.
    
    > [!NOTE]
    > 네트워크 지역 링크에 대역폭 제한이 있고 CAC를 사용하여 해당 링크에 대해 미디어 트래픽을 제어할 경우에만 대역폭 정책을 적용합니다. 
  
9. **커밋** 을 클릭합니다.
    
10. 토폴로지에 대한 네트워크 지역 링크 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-9단계를 반복합니다.
    
## <a name="see-also"></a>참고 항목

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
