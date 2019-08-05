---
title: 비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 비즈니스용 Skype Server Enterprise Voice의 E9-1-1에서 작동 하도록 SNMP 응용 프로그램을 구성 합니다.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197436"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성
 
비즈니스용 Skype Server Enterprise Voice의 E9-1-1에서 작동 하도록 SNMP 응용 프로그램을 구성 합니다. 
  
비즈니스용 Skype 서버에는 위치 정보 서비스를 포트 및 스위치 정보를 사용 하 여 MAC 주소와 일치 하는 SNMP (단순 네트워크 관리 프로토콜) 응용 프로그램에 연결 하는 데 사용할 수 있는 표준 웹 서비스 인터페이스가 포함 되어 있습니다. 
  
SNMP 응용 프로그램이 설치 되어 있고 위치 정보 서비스가 위치 데이터베이스에서 일치 하는 항목을 찾지 못하는 경우 위치 정보 서비스는 클라이언트에서 제공 하는 MAC 주소를 사용 하 여 응용 프로그램을 자동으로 쿼리 합니다. 위치 정보 서비스는 SNMP 응용 프로그램에서 반환 된 포트 및 스위치 정보를 사용 하 여 위치 데이터베이스를 다시 쿼리 합니다.
  
> [!NOTE]
> MAC 주소는 Windows 8을 실행 하는 컴퓨터에서 사용할 수 없습니다. 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP 응용 프로그램 URL을 구성 하려면

1.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. SNMP 응용 프로그램의 URL을 구성 하려면 다음 cmdlet을 실행 합니다. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>참고 항목

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

