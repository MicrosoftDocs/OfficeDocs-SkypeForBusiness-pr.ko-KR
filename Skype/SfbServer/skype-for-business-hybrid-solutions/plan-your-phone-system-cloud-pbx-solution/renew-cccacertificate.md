---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: 이 Renew-CcCACertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신합니다. 이 명령은 클라우드 커넥터 2.0 Update-CcCACertificate 릴리스에서 이 명령으로 변경되었습니다.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824274"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
이 Renew-CcCACertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신합니다. 이 명령은 클라우드 커넥터 2.0 Update-CcCACertificate 릴리스에서 이 명령으로 변경되었습니다.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 루트 CA 인증서를 갱신합니다. 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

클라우드 커넥터 루트 CA 인증서는 인증 기관 서비스가 설치된 날짜로부터 5년 동안 유효합니다.
  
루트 인증서가 만료에 가까운 경우 또는 이미 만료된 경우 Renew-CcCACertificate cmdlet을 실행하여 인증서를 갱신합니다. 루트 인증서가 갱신된 후 AD Server, 중앙 관리 저장소 및 에지 서버는 자동으로 새 인증서를 발급합니다.
  
동일한 PSTN 사이트에 여러 어플라이언스가 있는 경우 동일한 PSTN 사이트의 모든 어플라이언스에서 Renew-CcCACertificate cmdlet을 실행합니다.
  
마지막 Export-CcRootCertificate 실행하여 루트 인증서를 첫 번째 어플라이언스의 로컬 파일로 내보냈다가 내보냈던 인증서를 PSTN 게이트웨이에 복사하여 설치합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Renew-CcCACertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

