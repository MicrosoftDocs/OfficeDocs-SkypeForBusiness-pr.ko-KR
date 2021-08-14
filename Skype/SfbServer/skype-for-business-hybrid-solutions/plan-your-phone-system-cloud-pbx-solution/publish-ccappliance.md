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
description: 이 Publish-CcAppliance cmdlet은 온라인 테넌트 구성에서 고가용성 정보를 확인하여 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 게시합니다.
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326184"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
이 Publish-CcAppliance cmdlet은 온라인 테넌트 구성에서 고가용성 정보를 확인하여 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 게시합니다. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 온라인 테넌트 구성에서 고가용성 정보를 확인하여 호스트 서버의 Cloud Connector Appliance에 게시합니다.
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

고가용성 정보에는 PSTN 사이트의 중재 서버 FQDN 및 IP 주소가 포함되어 있습니다. 새 DNS A 레코드는 중재 서버 IP 주소에 대한 AD Server에 추가됩니다. 새 토폴로지 항목은 중재 서버 FQDNS 및 IP 주소에 대한 중앙 관리 저장소로 업데이트됩니다. 
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Publish-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

