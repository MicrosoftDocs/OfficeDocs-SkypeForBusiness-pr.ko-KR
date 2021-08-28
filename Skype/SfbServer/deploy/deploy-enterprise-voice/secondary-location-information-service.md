---
title: 다음 위치에서 보조 위치 정보 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: E9-1-1의 SLS(보조 위치 원본) 데이터베이스를 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: b2db211ec9c1bc7d2459ad2dbc8cada4b87afa6e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618114"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>다음 위치에서 보조 위치 정보 비즈니스용 Skype 서버
 
E9-1-1의 SLS(보조 위치 원본) 데이터베이스를 비즈니스용 Skype 서버 Enterprise Voice. 
  
비즈니스용 Skype 서버 SLAS(보조 위치 원본) 데이터베이스를 안내하는 데 사용할 수 있는 웹 서비스 인터페이스를 제공합니다. SLS 데이터베이스에 연결하는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수해야 합니다. 위치 데이터베이스와 보조 위치 데이터베이스가 모두 구성된 경우 위치 정보 서비스는 먼저 위치 데이터베이스를 쿼리하고 일치하는 위치가 없는 경우 클라이언트에서 SLS 데이터베이스로 위치 요청을 전송합니다. SLS에 위치가 있는 경우 위치 정보 서비스는 해당 위치를 클라이언트로 다시 전송합니다. 
  
### <a name="to-configure-a-secondary-location-database"></a>보조 위치 데이터베이스를 구성하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 다음 cmdlet을 실행하여 보조 위치 데이터베이스의 위치에 대해 URL을 구성합니다. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>참고 항목

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)