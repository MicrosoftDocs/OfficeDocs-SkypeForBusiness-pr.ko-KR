---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 게시-CcAppliance cmdlet는 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져와 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 게시 합니다.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824314"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
게시-CcAppliance cmdlet는 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져와 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 게시 합니다. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져오고 호스트 서버의 클라우드 커넥터 기기에 게시 합니다.
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

고가용성 정보에는 PSTN 사이트의 중재 서버 Fqdn 및 IP 주소가 포함 됩니다. 새 DNS 중재 서버 IP 주소에 대 한 레코드가 광고 서버에 추가 됩니다. 새 토폴로지 항목이 중재 서버 Fqdn과 IP 주소에 대 한 중앙 관리 저장소로 업데이트 됩니다. 
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. 게시-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

