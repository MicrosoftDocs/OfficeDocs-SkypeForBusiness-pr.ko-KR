---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: 이 Reset-CcCACertificate cmdlet은 인증 기관 서비스 AD 서버를 다시 설치하여 새 루트 CA 인증서를 생성합니다.
ms.openlocfilehash: 21f62724f74504216bcd38f5498b3a7068722512
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624970"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
이 Reset-CcCACertificate cmdlet은 인증 기관 서비스 AD 서버를 다시 설치하여 새 루트 CA 인증서를 생성합니다.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 인증 기관 서비스 AD Server를 다시 설치하여 새 루트 CA 인증서를 생성합니다.
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

루트 CA 인증서가 손상되거나 더 이상 안전하지 못하면 루트 CA 인증서와 루트 CA에서 발급한 모든 인증서를 업데이트해야 합니다. 이 Reset-CcCACertificate cmdlet은 모든 인증서를 해지하고 인증 기관을 제거한 후 다시 설치한 다음 이전 인증 기관 서비스와 관련된 모든 인증서를 정리합니다. 
  
자세한 내용은 클라우드 커넥터 배포 문제 해결에서 "CMS, 중재 서버 및 에지 서버에 발급된 인증 기관 인증서 또는 내부 인증서가 거의 만료되거나 손상된 경우"를 참조하세요.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Reset-CcCACertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) 버전 1.4.2만 해당
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) 버전 1.4.2만 해당
  
[Update-CcCACertificate](update-cccacertificate.md) 버전 2.0 이상
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) 버전 2.0 이상
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

