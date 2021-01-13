---
title: 비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 비즈니스용 Skype 서버 서버에서 E9-1-1과 함께 작동하도록 SNMP 응용 프로그램을 Enterprise Voice.
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804158"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성
 
비즈니스용 Skype 서버 서버에서 E9-1-1과 함께 작동하도록 SNMP 응용 프로그램을 Enterprise Voice. 
  
비즈니스용 Skype 서버에는 위치 정보 서비스를 포트 및 스위치 정보와 일치하는 MAC 주소와 일치하는 SNMP(Simple Network Management Protocol) 응용 프로그램에 연결하는 데 사용할 수 있는 표준 웹 서비스 인터페이스가 포함되어 있습니다. 
  
SNMP 응용 프로그램이 설치되고 위치 정보 서비스에서 위치 데이터베이스에서 일치를 찾지 못하는 경우 위치 정보 서비스는 클라이언트에서 제공한 MAC 주소를 사용하여 응용 프로그램을 자동으로 쿼리합니다. 그런 다음 위치 정보 서비스는 SNMP 응용 프로그램에서 반환된 포트 및 스위치 정보를 사용하여 위치 데이터베이스를 다시 쿼리합니다.
  
> [!NOTE]
> MAC 주소는 Windows 8을 실행하는 컴퓨터에서 사용할 수 없습니다. 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP 응용 프로그램 URL을 구성하려면

1.  비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 다음 cmdlet를 실행하여 SNMP 응용 프로그램에 대한 URL을 구성합니다. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>참고 항목

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

