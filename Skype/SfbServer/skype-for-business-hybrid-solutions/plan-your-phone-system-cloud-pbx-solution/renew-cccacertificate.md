---
title: 갱신-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: CcCACertificate cmdlet은 거의 만료 되거나 이미 만료 된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신 합니다. 이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcCACertificate로 변경 되었습니다.
ms.openlocfilehash: f1e376b5b944468ec5bf508c6221a099a83d4804
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190680"
---
# <a name="renew-cccacertificate"></a>갱신-CcCACertificate
 
CcCACertificate cmdlet은 거의 만료 되거나 이미 만료 된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신 합니다. 이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcCACertificate로 변경 되었습니다.
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 루트 CA 인증서를 갱신 합니다. 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

클라우드 커넥터 루트 CA 인증서는 인증 기관 서비스를 설치한 날짜 로부터 5 년 동안 유효 합니다.
  
루트 인증서가 거의 만료 되거나 이미 만료 된 경우 갱신 CcCACertificate cmdlet을 실행 하 여 인증서를 갱신 합니다. 루트 인증서가 갱신 된 후 광고 서버, 중앙 관리 저장소 및 Edge 서버에 새 인증서가 자동으로 발급 됩니다.
  
동일한 PSTN 사이트에 여러 기기가 있는 경우 동일한 PSTN 사이트의 모든 기기에서 CcCACertificate cmdlet을 실행 합니다.
  
마지막 단계로 내보내기-CcRootCertificate를 실행 하 여 루트 인증서를 첫 번째 기기의 로컬 파일로 내보낸 다음, 내보낸 인증서를 PSTN 게이트웨이에 복사 하 여 설치 합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcCACertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[다시 설정-CcCACertificate](reset-cccacertificate.md)
  
[갱신-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

