---
title: 비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 비즈니스용 Skype 서버에서 E9-1-1에 대해 SLS(보조 위치 원본) 데이터베이스를 Enterprise Voice.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830648"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성
 
비즈니스용 Skype 서버에서 E9-1-1에 대해 SLS(보조 위치 원본) 데이터베이스를 Enterprise Voice. 
  
비즈니스용 Skype 서버는 SLS(보조 위치 원본) 데이터베이스를 안내하는 데 사용할 수 있는 웹 서비스 인터페이스를 제공합니다. SLS 데이터베이스에 연결하는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수해야 합니다. 위치 데이터베이스와 보조 위치 데이터베이스가 모두 구성된 경우 위치 정보 서비스는 먼저 위치 데이터베이스를 쿼리하고 일치하는 위치가 없는 경우 클라이언트에서 SLS 데이터베이스로 위치 요청을 전송합니다. SLS에 위치가 있는 경우 위치 정보 서비스는 해당 위치를 클라이언트로 다시 전송합니다. 
  
### <a name="to-configure-a-secondary-location-database"></a>보조 위치 데이터베이스를 구성하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 다음 cmdlet을 실행하여 보조 위치 데이터베이스의 위치에 대해 URL을 구성합니다. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>참고 항목

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

