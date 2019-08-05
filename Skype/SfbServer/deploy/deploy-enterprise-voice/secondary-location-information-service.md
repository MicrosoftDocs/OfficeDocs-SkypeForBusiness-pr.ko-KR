---
title: 비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 비즈니스용 Skype Server Enterprise Voice에서 E9-1에 대 한 SLS (보조 위치 원본) 데이터베이스를 구성 합니다.
ms.openlocfilehash: 0d637b8b2b61526837be2d56b8654f40bc556064
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191133"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성
 
비즈니스용 Skype Server Enterprise Voice에서 E9-1에 대 한 SLS (보조 위치 원본) 데이터베이스를 구성 합니다. 
  
비즈니스용 Skype Server는 위치 정보 서비스를 보조 위치 원본 (SLS) 데이터베이스에 가리키는 데 사용할 수 있는 웹 서비스 인터페이스를 제공 합니다. SLS 데이터베이스에 연결 하는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수 해야 합니다. 위치 데이터베이스와 보조 위치 데이터베이스가 모두 구성 되어 있는 경우 위치 정보 서비스는 위치 데이터베이스에 먼저 쿼리 하 고 일치 하는 항목이 없으면 클라이언트의 위치 요청을 SLS 데이터베이스에 보냅니다. 위치가 SLS에 있는 경우에는 위치 정보 서비스에서 해당 위치를 다시 클라이언트로 보냅니다. 
  
### <a name="to-configure-a-secondary-location-database"></a>보조 위치 데이터베이스를 구성 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 다음 cmdlet을 실행 하 여 보조 위치 데이터베이스의 위치에 대 한 URL을 구성 합니다. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>참고 항목

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

