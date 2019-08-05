---
title: 다시 설정-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: CcCACertificate cmdlet은 인증 기관 서비스 광고 서버를 다시 설치 하 여 새 루트 CA 인증서를 만듭니다.
ms.openlocfilehash: 3cac8629a52d915df55408a44d8d31701106a5bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190662"
---
# <a name="reset-cccacertificate"></a>다시 설정-CcCACertificate
 
CcCACertificate cmdlet은 인증 기관 서비스 광고 서버를 다시 설치 하 여 새 루트 CA 인증서를 만듭니다.
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 새 루트 CA 인증서를 만들기 위해 인증 기관 서비스 광고 서버를 다시 설치 합니다.
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

루트 CA 인증서가 손상 되거나 더 이상 안전 하지 않은 경우 루트 ca 인증서와 루트 CA가 발급 한 모든 인증서를 업데이트 해야 합니다. CcCACertificate cmdlet은 모든 인증서를 해지 하 고 인증 기관을 제거 하 고 다시 설치 하 고 이전 인증 기관 서비스와 관련 된 모든 인증서를 정리 합니다. 
  
자세한 내용은 클라우드 커넥터 배포 문제 해결에서 "CMS, 중재 서버 및 Edge 서버에 발급 된 인증 기관 인증서 또는 내부 인증서가 거의 만료 되었거나 손상 되었습니다."를 참조 하세요.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcCACertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[갱신-CcCACertificate](renew-cccacertificate.md) 버전 1.4.2
  
[갱신-CcServerCertificate](renew-ccservercertificate.md) 버전 1.4.2
  
[업데이트-CcCACertificate](update-cccacertificate.md) 버전 2.0 이상
  
[갱신-CcServerCertificate](renew-ccservercertificate.md) 버전 2.0 이상
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

